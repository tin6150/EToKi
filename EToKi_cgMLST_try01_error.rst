# took a long time to spill out the error message
# it started, then ran into some other error?!

Sun Aug 17 15:14:27 PDT 2025
start EToKi
end at
Sun Aug 17 15:30:07 PDT 2025	# ie ran for ~15 min  (load avg 1)

# dumping screen output ::

(venv_stec) [tin@n0060 Test_Enterobase]$ python3  ~/gs/tin-gh/EToKi/EToKi.py cgMLST --output GCA_018769385.1 --profile ~tin/gs/fc_graham/EnteroBaseSchemeEcoli/profiles.list   GCA_018769385.1_PDT001063311.1_genomic.fna
echo $? ; date

Start with 0 genes in 353863 genomes
====== Iteration 0 ======
Remove genes that present in < 0.5 of genomes
Remove genes that are intact in < 0.5 of genomes.
Remain 0 genes.
Remove genomes that contain < 0.4 of genes.

Remain 353863 genomes.
====== Iteration 1 ======
Remove genes that present in < 0.8 of genomes
Remove genes that are intact in < 0.8 of genomes.
Remain 0 genes.
Remove genomes that contain < 0.6 of genes.

Remain 353863 genomes.
====== Iteration 2 ======
Remove genes that present in < 0.95 of genomes
Remove genes that are intact in < 0.94 of genomes.
Remove genes that are significantly variable (> 3.0 sigma) in a Gaussian process regression. This can take a long time.
usage: EToKi [-h]
             {configure,prepare,assemble,MLSTdb,MLSType,MLSTsum,cgMLST,align,phylo,EBEis,uberBlast,clust,isCRISPOL} ...

options:
  -h, --help            show this help message and exit

sub-commands:
  {configure,prepare,assemble,MLSTdb,MLSType,MLSTsum,cgMLST,align,phylo,EBEis,uberBlast,clust,isCRISPOL}
    configure           install and/or configure 3rd party programs
    prepare             trim, collapse, downsize and rename the short reads.
    assemble            de novo or reference-guided assembly for genomic or metagenomic reads
    MLSTdb              Set up exemplar alleles and database for MLST schemes
    MLSType             MLST nomenclature using a local set of references
    MLSTsum             Summarise MLSType results and assign new allele designations
    cgMLST              Select a list of genes for the cgMLST scheme
    align               align multiple queried genomes to a single reference
    phylo               infer phylogeny and ancestral states from genomic alignments
    EBEis               in silico serotype prediction for Escherichia coli and Shigella spp.
    uberBlast           Use Blastn, uBlastp, minimap2 and/or mmseqs to identify similar sequences
    clust               linear-time clustering of short sequences using mmseqs linclust
    isCRISPOL           in silico prediction of CRISPOL array for Salmonella enterica serovar Typhimurium
(venv_stec) [tin@n0060 Test_Enterobase]$ echo $? ; date
0
Sun Aug 17 15:30:07 PDT 2025


# same error with the 2nd input file, ran for ~15 min (987.75 sec) then output that usage info.
# didn't like something... 
