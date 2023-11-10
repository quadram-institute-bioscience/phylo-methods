## Example of the limitation of using only SNPs 

The file `08.full_align.aln` contains the original alignment, and the resulting ML tree `08.full_align.treefile`. 
If you extract the SNPs with `snp-sites 08.full_align.aln > 08.snps_only.aln`, then the resulting alignment will generate trees `08.snps_fconst.treefile` 
or `08.snps_only.treefile`, depending on wether you add the `-fconst` option or not to `iqtree2`.

For the ML trees, I estimated them with `iqtree2 --ninit 1000 -t PARS -m HKY --allnni`. 

See also [the discussion summarised by Phil Ashton, including some commands](https://bitsandbugs.org/2019/11/06/two-easy-ways-to-run-iq-tree-with-the-correct-number-of-constant-sites/).

### extra file: `09.AUtest.txz`
This file contains the results of running IQTREE to test for the significance of different (optimal) trees according to
each alignment. The command line was something like, for example, 
```
iqtree2 -s ../08.snps_only.aln -z 09.autest.trees -n 0 -zb 50000 -zw -au --prefix 08.snp_fconst_all_models -fconst 216,185,155,100
```
to find the best model, and use this model with the SNPs-only alignment (`-s ../08.snps_only.aln`) and the number of constant sites (`-fconst 216,185,155,100`) to compare all trees included in file 
`09.autest.trees`. 


### extra file: `randomtrees.newick`

These are the three trees used in the distance comparison with the `phangorn` functions implemented in `treedist()`.

