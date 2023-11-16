> [!IMPORTANT]
> :warning: We won't have time to discuss the results of this analysis during the (second) lecture

# Multi-gene phylogeny by concatenating alignments

This exercise will help us to compare the results of estimating phylogenies using different genes.
You should estimate the phylogeny of each gene, and after concatenating all of them.

Assuming you aligned each gene, you can concatenate them into a single alignment and estimate an intial NJ tree with 
```bash
for i in bacteria.*fasta; do mafft --auto ${i} > ${i%fasta}aln # last variable has "fasta" replaced by "aln"
seqkit concat bacteria.*aln > concat_right.aln
rapidnj -i fa -t d -n -c 7 concat_right.aln | perl -pe "s/\'//g;"  > concat_right.nj.tre
```
For an alternative to `seqkit concat` you can run `goalign concat -i bacteria.*aln`, and instead of `rapidnj` you can
try one of
```bash
iqtree2 -t PARS --ninit 1000 --allnni -s concat_right.aln --prefix test1 -m HKY
raxml-ng --all --msa concat_right.aln  --model HKY --prefix test2
```

Just out of curiosity (this is WRONG), see what result you would obtain if you first concatenated the unaligned
sequences, and then aligned the resulting chimeric sequences:
```bash
seqkit concat bacteria.*fasta > concat_wrong.fasta
mafft --auto concat_wrong.fasta > concat_wrong.aln
```

Files [fasta_100_sequences.txz](fasta_100_sequences.txz) and [fasta_40_sequences.txz](fasta_40_sequences.txz) contain the unaligned sequences (from 100 and from 40 isolates, respectively).
The file [names_full_taxonomy.tsv](names_full_taxonomy.tsv) contains the GTDB classification for these sequences, in case you want to change the
tip names or colours. 
