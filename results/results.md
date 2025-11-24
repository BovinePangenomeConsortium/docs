## Assemblies

### Raw assembly data

 - [Metadata + QC](https://polybox.ethz.ch/index.php/s/YA5AXSkckinwRqD)
 - [AGC [password protected]](https://polybox.ethz.ch/index.php/s/ELA974zs5HaHX8F)

#### Unpacking the genomes

The genome archive can be unpacked with [agc](https://github.com/refresh-bio/agc), writing out all (compressed) assemblies to a given folder.
Unfortunately, these are gzipped and not bgzipped, so we want to unzip and re-bgzip all assemblies.

```
mkdir -p agc
agc getcol -g 5 -o agc -t 4 -f BPC.agc

for S in agc/*.gz
do
  ungzip $S
  bgzip -@ 2 ${S%.gz}
  samtools faidx $S
done
```

### Centromeres

TODO: rerun and upload

Summarised CSV for repeat content+seq+maps?

### VCFs

TODO: rerun and add

Linear-called VCFs

## Graphs

### Pangene

Each file is gzipped tar, containing the `pangene` .gfa, gene copy number count .tsv, and graph bubble .call files.

 - [Ensembl ARS-UCD2.0 annotation, clustered [password protected]](https://polybox.ethz.ch/index.php/s/sdyGmgr9deyDPff)



### Cactus

