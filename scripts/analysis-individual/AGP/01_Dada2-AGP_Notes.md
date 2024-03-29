# Dataset
American Gut Project (_mSystems_, 2018) - [American Gut: an Open Platform for Citizen Science Microbiome Research][1]

[1]: https://journals.asm.org/doi/full/10.1128/mSystems.00031-18#DC1


## Samples
- **1290 total**
- 645 IBS & 645 HC
IBS and healthy samples were selected out of the pool of >30,000 samples deposited on the SRA. More details on sample selection in the [corresponding R script](00_Metadata-AGP.R)

## Data Quality
- **Technology** - Illumina MiSeq (single-end)
- **Nb of reads per sample** - mean of 30,469 reads per sample (1 - 344,010)
- **Read length** - ~150 bp
- **Quality** - excellent


## Primers
- V4 variable regions (about 250bp)
- FWD - 515F - 5’ - GTGYCAGCMGCCGCGGTAA - 3’
- REV -  806R - 5’ - GGACTACHVGGGTWTCTAAT - 3’
- no primer found (some samples have a few hundreds reads containing the reverse complement of the reverse primer, but that's all)


## Filtering
- **primers removal** - not applied
- **quality filter** - \~93% reads kept per sample. 42 samples did not pass the quality filter.


## Learn error rates
- parametric error model fits data

## Construct ASV table
### a) Infer sequence variants
- 27,989 amplicon sequence variants (ASVs)

### b) Remove chimeras
- 18,659 seq variants (but still >95% reads kept)

### c) Assign taxonomy
Taxonomy assigned with Silva v138.
- Bacteria - 18,361
- Archaea - 48
- Eukaryota - 54

All unassigned phyla were removed (n=1,522), samples below 500 total reads (n=43). The final ASV table contains 17,111 sequence variants.

### d) Remove bloom sequences
As fecal samples were shipped at room temperature, it is recommended to remove bloom sequences (bacteria that grow at room temperature). We followed recommendations from this paper: https://journals.asm.org/doi/10.1128/mSystems.00199-16#B5
After removing bloom sequences, the final phyloseq object contained **1,191 samples** and **17,056 ASVs**.


## Metadata
- age
- BMI
- bowel movement frequency & quality
- gut-related covariates (lactose intolerance, gluten consumption, SIBO, probiotic consumption)
- comorbidities (lung, liver, kidney disease)
- other covariates (exercise & alcohol frequency, country)