## Example of the limitation of using only SNPs 

The file `08.full_align.aln` contains the original alignment, and the resulting ML tree `08.full_align.treefile`. 
If you extract the SNPs with `snp-sites 08.full_align.aln > 08.snps_only.aln`, then the resulting alignment will generate trees `08.snps_fconst.treefile` 
or `08.snps_only.treefile`, depending on wether you add the `-fconst` option or not to `iqtree2`.

For the ML trees, I estimated them with `iqtree2 --ninit 1000 -t PARS -m HKY --allnni`. 

See also [the discussion summarised by Phil Ashton, including some commands](https://bitsandbugs.org/2019/11/06/two-easy-ways-to-run-iq-tree-with-the-correct-number-of-constant-sites/).
