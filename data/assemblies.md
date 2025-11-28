# Assemblies

## Preprocessing scheme

Assemblies that are not Ensembl/RefSeq annotated are cut at gaps back into contigs and then scaffolded against ARS-UCD2.0 to determine chromosome position and orientation.
The assemblies are left at the contig level to avoid an explosion of "N"s in the pangenome graphs.

## Naming scheme

We use a modified version of panSN that seems to be compatible with most downstream tools.
The format is `<Animal ID>#<Haplotype>#<Chromosome>:<start>-<end>`, where the ":start-end" is the extension to panSN as used in `cactus`.
This allows us to track positions of contigs within the reference-scaffolding, making downstream analyses more useful.

 - **Animal ID**: a unique eight digit hexadecimal code assigned to each new contributed animal
 - **Haplotype**: a single digit corresponding to either a primary/collapsed assembly (0) or haplotype-resolved (1 or 2). Conventionally paternal is 1, maternal is 2.
 - **Chromosome**: the name of the genomic sequence, with 1-29, X, Y, MT for cattle, with all other contigs called unplaced
 - **start**/**end**: genomic coordinates that are in the interval [1,length]


## QC

We run several QC steps, like `calN50.js` and `compleasm` to determine metrics intrinsic to the assemblies.
We need to get a rough idea of how well assembled these genomes are, but for many samples we only have the assembly itself, not the raw data.
As such, we have to rely on some proxy metrics.
We use a proxy QV by assessing the ratio of InDels to SNPs from the reference-alignment called variants with `minimap2 -c --cs | paftools.js call`.


## Data entries

  - **Sample information**
   - Animal ID
   - Haplotype
   - Sex
   - Species
   - Subspecies
   - Breed
  - **Consortium information**
   - Public download: sample accession on NCBI etc
   - QC Fail: Reason for exclusion from primary analyses
   - Graphs: Which subcategories the assembly should be used in
  - **Assembly information**
   - genome size
   - N contigs
   - NG50: N50 with respect to ARS-UCD2.0
   - BUSCOs: Using the artiodactyla_odb12 database
   - {SNPs,InDels}: Number of SNPs or InDels called from linear reference alignments
   - {autosomes,X,Y,MT} covered: Fraction of ARS-UCD2.0 chromosomes covered by linear reference alignments