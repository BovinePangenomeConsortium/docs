# CHANGELOG 

Tracking changes to the genome archive and associated metadata. 

### 2025-12-10
- [**metadata**] Renamed Bovine to Bovinae and Cattle to BosTaurus
- [**metadata**] Remove duplicate public assembly [`88151D78#0`](https://www.ncbi.nlm.nih.gov/datasets/genome/GCA_047652215.1/) already contributed as `7970EEFD#0`
- [**agc**] Remove that duplicate assembly

### 2025-12-08
- [**metadata**] Fix trailing space on "Bos mutus " for `E9520DBA#0`
- [**metadata**] Change "_n1" to "_representative" for clarity
- [**metadata**] Added Bovine and Bovina subsets; now "All" includes QC-fails [recommended only for QC jobs]

### 2025-11-19
- [**metadata**] Fixed animal ID `7FE8E942` (hap2) → `B7C6E035` (hap2) to properly pair haplotypes

### 2025-11-17
- [**agc**] Changed ARS-UCD1.3 → ARS-UCD2.0 (kept ID `85D7A68E#0`) to include reference Y
- [**metadata**] Updated assembly statistics for ARS-UCD2.0
- [**agc**] Updated panSN naming for genomes with reference annotations (`59F033BE#1`, `7BB17341#1`, `A234D56C#2`)
