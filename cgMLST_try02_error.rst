
(venv_stec) [tin@n0060 Test_Enterobase2]$ date; time -p python3  ~/gs/tin-gh/EToKi/modules/cgMLST.py     --output TestEN2         --profile ~tin/gs/fc_graham/EnteroBaseSchemeEcoli/profiles.list   GCA_018769425.2_PDT001063331.2_genomic.fna ; echo $? ; date ; uptime
Mon Aug 18 20:16:33 PDT 2025

# there was a long delay before any output was shown, likely 10+ minutes.  there was another instance that seems to be looping on the same node.   (python trace EToKi.py ... Test_EN1 )

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

Traceback (most recent call last):
  File "/global/home/users/tin/gs/tin-gh/EToKi/modules/cgMLST.py", line 192, in <module>
    cgMLST(sys.argv[1:])
  File "/global/home/users/tin/gs/tin-gh/EToKi/modules/cgMLST.py", line 141, in cgMLST
    y = np.apply_along_axis(lambda d: np.unique(d[d > 0]).size, 0, data) * 100. / np.sum(data > 0, 0)
        ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/global/scratch/users/tin/venv_stec/lib/python3.11/site-packages/numpy/lib/_shape_base_impl.py", line 383, in apply_along_axis
    raise ValueError(
ValueError: Cannot apply_along_axis when any iteration dimensions are 0


real 1144.77   # 19+ min
user 927.57
sys 31.81
1
Mon Aug 18 20:35:38 PDT 2025
 20:35:38 up 38 days,  7:57,  8 users,  load average: 3.03, 3.19, 2.94
(venv_stec) [tin@n0060 Test_Enterobase2]$
