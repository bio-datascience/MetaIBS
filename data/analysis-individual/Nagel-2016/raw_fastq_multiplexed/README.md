# raw_fastq_multiplexed (Nagel)

The raw fastq files were nicely shared by the authors after private inquiry. We demultiplexed samples (2 fastq files in [multiplexed_data](./multiplexed_data/)) from the terminal using [sabre](https://github.com/najoshi/sabre). Based on barcodes, sabre will demultiplex the healthy, IBS, IBD samples (and we remove samples not of interest: healthy/IBS samples positive for blastocystis, IBD samples).

To reproduce the demultiplexing, execute the bash script [bash_script_demultiplex.sh](./bash_script_demultiplex.sh). The output you should see in your terminal is provided below. Otherwise you can directly use the 30 demultiplexed `.fastq` files we have provided in the `data/` directory we shared on our zenodo.

```
(base) enigma@Salomes-MBP raw_fastq_multiplexed % ./bash_script_demultiplex.sh 
installing sabre
Archive:  master.zip
039a55e500ba07b7e6432ea6ec2ddcfb3471d949
   creating: sabre-master/
  inflating: sabre-master/LICENSE    
  inflating: sabre-master/Makefile   
  inflating: sabre-master/README.md  
   creating: sabre-master/src/
  inflating: sabre-master/src/barcode.c  
  inflating: sabre-master/src/demulti_paired.c  
  inflating: sabre-master/src/demulti_single.c  
  inflating: sabre-master/src/kseq.h  
  inflating: sabre-master/src/sabre.c  
  inflating: sabre-master/src/sabre.h  
gcc -Wall -pedantic -DVERSION=1.00 -O3 -c src/barcode.c
gcc -Wall -pedantic -DVERSION=1.00 -O3 -c src/demulti_single.c
src/demulti_single.c:47:6: warning: variable 'debug' set but not used [-Wunused-but-set-variable]
        int debug=0;
            ^
src/demulti_single.c:12:1: warning: unused function 'kseq_rewind' [-Wunused-function]
KSEQ_INIT(gzFile, gzread)
^
src/kseq.h:220:3: note: expanded from macro 'KSEQ_INIT'
  __KSEQ_BASIC(type_t)                                                  \
  ^
src/kseq.h:152:22: note: expanded from macro '__KSEQ_BASIC'
  static inline void kseq_rewind(kseq_t *ks)                            \
                     ^
2 warnings generated.
gcc -Wall -pedantic -DVERSION=1.00 -O3 -c src/demulti_paired.c
src/demulti_paired.c:59:6: warning: variable 'debug' set but not used [-Wunused-but-set-variable]
        int debug=0;
            ^
src/demulti_paired.c:12:1: warning: unused function 'kseq_rewind' [-Wunused-function]
KSEQ_INIT(gzFile, gzread)
^
src/kseq.h:220:3: note: expanded from macro 'KSEQ_INIT'
  __KSEQ_BASIC(type_t)                                                  \
  ^
src/kseq.h:152:22: note: expanded from macro '__KSEQ_BASIC'
  static inline void kseq_rewind(kseq_t *ks)                            \
                     ^
2 warnings generated.
gcc -Wall -pedantic -DVERSION=1.00 -O3 -c src/sabre.c
gcc -Wall -pedantic -DVERSION=1.00 -O3 barcode.o demulti_single.o demulti_paired.o sabre.o -o sabre -lz
demultiplex

Total FastQ records: 3533844

FastQ records for barcode ATCCTTTGGTTC: 47233
FastQ records for barcode AGCGGAGGTTAG: 54943
FastQ records for barcode GTCGTGTAGCCT: 53095
FastQ records for barcode ATCGCACAGTAA: 38837
FastQ records for barcode TGCATACACTGG: 43256
FastQ records for barcode AATTGTGTCGGA: 110335
FastQ records for barcode ACCGGTATGTAC: 46097
FastQ records for barcode TACAGCGCATAC: 51228
FastQ records for barcode ACCAGTGACTCA: 45837
FastQ records for barcode AGTCGAACGAGG: 44707
FastQ records for barcode GATTATCGACGA: 37818
FastQ records for barcode TGTGCGATAACA: 46397
FastQ records for barcode TACCGCTTCTTC: 47303
FastQ records for barcode GCCTAGCCCAAT: 34459
FastQ records for barcode CAACTCCCGTGA: 51522
FastQ records for barcode GCATATGCACTG: 54508
FastQ records for barcode ATGGCTGTCAGT: 48102
FastQ records for barcode CGAGGGAAAGTC: 41331
FastQ records for barcode AGTTACGAGCTA: 53697
FastQ records for barcode AGATTGACCAAC: 49319
FastQ records for barcode ATCACCAGGTGT: 49800
FastQ records for barcode TGGTCAACGATA: 54648
FastQ records for barcode CTCACAACCGTG: 49803
FastQ records for barcode TCCCTTGTCTCC: 42069
FastQ records for barcode ACGAGACTGATT: 53628
FastQ records for barcode GCTGTACGGATT: 53299
FastQ records for barcode TGTAACGCCGAT: 50105
FastQ records for barcode AGCAGAACATCT: 46502
FastQ records for barcode TGGAGTAGGTGG: 46887
FastQ records for barcode TTGGCTCTATTC: 51980
FastQ records for barcode GTATCTGCGCGT: 47489
FastQ records for barcode GTTCTCTTCTCG: 42687
FastQ records for barcode CGAGCAATCCTA: 51269
FastQ records for barcode GCGATATATCGC: 40945
FastQ records for barcode GCAACACCATCC: 41853
FastQ records for barcode CAAACAACAGCT: 49151
FastQ records for barcode CAGCTCATCAGC: 46136
FastQ records for barcode GATCTGCGATCC: 44897
FastQ records for barcode CCAATACGCCTG: 55487
FastQ records for barcode TGCGCTGAATGT: 51271
FastQ records for barcode CGTAAGATGCCT: 47390
FastQ records for barcode GTTGTTCTGGGA: 62113
FastQ records for barcode GCGTTCTAGCTG: 46269
FastQ records for barcode GGACTTCCAGCT: 51482
FastQ records for barcode GATCCCACGTAC: 46541
FastQ records for barcode TAGTATGCGCAA: 48376
FastQ records for barcode GTGGTGGTTTCC: 46860
FastQ records for barcode TAGGCATGCTTG: 47055
FastQ records for barcode ATGGGTTCCGTC: 39340
FastQ records for barcode GGTGACTAGTTC: 50631
FastQ records for barcode GTACGATATGAC: 51703
FastQ records for barcode AGCATGTCCCGT: 45231
FastQ records for barcode ATTCTGCCGAAG: 49881
FastQ records for barcode AACTAGTTCAGG: 52148
FastQ records for barcode AGTCGTGCACAT: 47097
FastQ records for barcode ATGTCACCGCTG: 40562
FastQ records for barcode CTGCTATTCCTC: 44722
FastQ records for barcode GTGTTGTCGTGC: 45513
FastQ records for barcode TATCGACACAAG: 44119
FastQ records for barcode CCACAGATCGAT: 44432
FastQ records for barcode CGTAATTGCCGC: 43336
FastQ records for barcode GATTCCGGCTCA: 47216
FastQ records for barcode TAACGTGTGTGC: 48806
FastQ records for barcode CATTATGGCGTG: 47262
FastQ records for barcode GAATACCAAGTC: 45519
FastQ records for barcode GTAGATCGTGTA: 42641
FastQ records for barcode CAAATTCGGGAT: 38957

FastQ records with no barcode match: 298712

Number of mismatches allowed: 0


Total FastQ records: 2952134

FastQ records for barcode TGTCGCAAATAG: 22642
FastQ records for barcode GTCGACAGAGGA: 40016
FastQ records for barcode CATCCCTCTACT: 41753
FastQ records for barcode CATTCGTGGCGT: 28755
FastQ records for barcode TGTGAATTCGGA: 42852
FastQ records for barcode TCGGAATTAGAC: 44467
FastQ records for barcode GCAACACCATCC: 34712
FastQ records for barcode CTATCTCCTGTC: 40454
FastQ records for barcode GATGTTCGCTAG: 40772
FastQ records for barcode GGCCAGTTCCTA: 42094
FastQ records for barcode TACTACGTGGCC: 44114
FastQ records for barcode GTAGATCGTGTA: 36628
FastQ records for barcode TAACGTGTGTGC: 49236
FastQ records for barcode ATGATGAGCCTC: 36948
FastQ records for barcode CTCACAACCGTG: 46524
FastQ records for barcode GATCTGCGATCC: 39361
FastQ records for barcode CAGCTCATCAGC: 38444
FastQ records for barcode CATTATGGCGTG: 44421
FastQ records for barcode CCAATACGCCTG: 41034
FastQ records for barcode ACTTCCAACTTC: 49219
FastQ records for barcode TAATACGGATCG: 37999
FastQ records for barcode GCGATATATCGC: 30257
FastQ records for barcode GAACACTTTGGA: 43085
FastQ records for barcode GAGCCATCTGTA: 45848
FastQ records for barcode TTGGGTACACGT: 35513
FastQ records for barcode AAGGCGCTCCTT: 38646
FastQ records for barcode CACTACGCTAGA: 9071
FastQ records for barcode TGCAGTCCTCGA: 40577
FastQ records for barcode ACCATAGCTCCG: 44396
FastQ records for barcode TCGACATCTCTT: 45846
FastQ records for barcode ATCCTTTGGTTC: 39829
FastQ records for barcode AGCGGAGGTTAG: 13
FastQ records for barcode GTCGTGTAGCCT: 44725
FastQ records for barcode ATCGCACAGTAA: 42544
FastQ records for barcode TGGTCAACGATA: 42154
FastQ records for barcode ATCACCAGGTGT: 40995
FastQ records for barcode GCTGTACGGATT: 54722
FastQ records for barcode ACGAGACTGATT: 45797
FastQ records for barcode TCCCTTGTCTCC: 77338
FastQ records for barcode ACAATAGACACC: 40217
FastQ records for barcode AGTTGAGGCATT: 40162
FastQ records for barcode TATACCGCTGCG: 33645
FastQ records for barcode AGGCTTACGTGT: 34141
FastQ records for barcode GCTCGAAGATTC: 41716
FastQ records for barcode GTGGAGTCTCAT: 40319
FastQ records for barcode CGGTCAATTGAC: 44579
FastQ records for barcode CGAGCAATCCTA: 45636
FastQ records for barcode TCTCTACCACTC: 21011
FastQ records for barcode AGTCGTGCACAT: 40075
FastQ records for barcode CAAACAACAGCT: 39691
FastQ records for barcode ACCAGTGACTCA: 45945
FastQ records for barcode AGTCGAACGAGG: 34742
FastQ records for barcode ACCGGTATGTAC: 45504
FastQ records for barcode TACAGCGCATAC: 34343
FastQ records for barcode TGCATACACTGG: 36204
FastQ records for barcode AATTGTGTCGGA: 32002
FastQ records for barcode ACTCACAGGAAT: 33833
FastQ records for barcode TTGCGTTAGCAG: 44484
FastQ records for barcode TACGAGCCCTAA: 37778
FastQ records for barcode GTATCTGCGCGT: 39224
FastQ records for barcode CGAGGGAAAGTC: 34377
FastQ records for barcode CAAATTCGGGAT: 33947
FastQ records for barcode AGATTGACCAAC: 41227
FastQ records for barcode AGTTACGAGCTA: 48548
FastQ records for barcode GCATATGCACTG: 42189
FastQ records for barcode CAACTCCCGTGA: 40577
FastQ records for barcode CTCACCTAGGAA: 39036

FastQ records with no barcode match: 303181

Number of mismatches allowed: 0

move fastq files
(base) enigma@Salomes-MBP raw_fastq_multiplexed % 
```