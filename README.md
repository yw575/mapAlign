# mapAlign
## mapAlign: an effcient approach for mapping and aligning long reads to reference genomes
### Usage:
#### Usage 1: map long reads against a reference genome
##### CMD: mapAlign align threads kmer-size reference-file read-file output-file
* threads : threads number, currently from 1 to 48
* kmer-size: the kmer size, currently from 14 to 16
* reference-file: the input reference file(.fa/.fq/.fasta/.fastq) 
* read-file: the input read file(.fa/.fq/.fasta/.fastq)
* output-file: the file for SAM format output

#### Usage 2: dump a reference genome to a prebuilt index file
#####  CMD: mapAlign idump threads kmer-size reference-file output-file
* threads : threads number, currently from 1 to 48
* kmer-size: the kmer size, currently from 14 to 16
* reference-file: the input reference file(.fa/.fq/.fasta/.fastq)
* output-file: the output file to store the prebuilt index 

#### Usage 3:  map long reads against a prebuilt index file
#####  CMD: mapAlign iload threads kmer-size index-file read-file output-file
* threads : threads number, currently from 1 to 48
* kmer-size: the kmer size, currently from 14 to 16
* index-file: the prebuilt  index file 
* read-file: the input read file(.fa/.fq/.fasta/.fastq)
* output-file: the file for SAM format output

#### Limitations
* The current executable binary is only available for 64 bits linux system(tested on Ubuntu/Debian) 
* Only support fasta/fastq format for read file and reference file, other file formats will be updated later 
* For large reference genome, like human, it is recommended to dump the reference genome to index file first and use the index file for mapping. mapAlign takes more than 32GB memory and about 20 minutes for the dumping process of a human reference genome. Thus, 64GB system memory is preferred.

#### Examples
#####  A small example
```sh
./mapAlign align 1 15 ref_e1.fa read_e1.fa read_e1.sam
```
