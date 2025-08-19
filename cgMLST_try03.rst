expect to use ~44 GB RAM  (so base OS at start used 3GB)
no other process running at this time

try #3
start:  10:05pm 8/18

(venv_stec) [tin@n0060 Test_Enterobase2]$ date; free -h ; time -p python3  ~/gs/tin-gh/EToKi/modules/cgMLST.py     --output TestEN2         --profile ~tin/gs/fc_graham/EnteroBaseSchemeEcoli/profiles.list   GCA_018769425.2_PDT001063331.2_genomic.fna ; echo $? ; date ; uptime

Mon Aug 18 22:05:55 PDT 2025
              total        used        free      shared  buff/cache   available
Mem:          251Gi       3.0Gi       236Gi       8.4Gi        11Gi       238Gi
Swap:         8.0Gi          0B       8.0Gi



++

~7 min later see my dbg msg:
====== entering cgMLST fn ====== +Sn50+
	used 32-3=29GB by here.  loading the profile db? 

date; free -h
Mon Aug 18 22:12:43 PDT 2025
              total        used        free      shared  buff/cache   available
Mem:          251Gi        32Gi       205Gi       8.4Gi        13Gi       208Gi
Swap:         8.0Gi          0B       8.0Gi

++


Start with 0 genes in 353863 genomes
====== entering for ite(ration), cuts loop ====== +Sn50+
Mon Aug 18 22:23:42 PDT 2025
====== Iteration 0 ======
Remove genes that present in < 0.5 of genomes
Remove genes that are intact in < 0.5 of genomes.
Remain 0 genes.
Remove genomes that contain < 0.4 of genes.

Remain 353863 genomes.
Mon Aug 18 22:23:42 PDT 2025
====== Iteration 1 ======
Remove genes that present in < 0.8 of genomes
Remove genes that are intact in < 0.8 of genomes.
Remain 0 genes.
Remove genomes that contain < 0.6 of genes.

Remain 353863 genomes.
Mon Aug 18 22:23:42 PDT 2025
====== Iteration 2 ======
Remove genes that present in < 0.95 of genomes
Remove genes that are intact in < 0.94 of genomes.
Remove genes that are significantly variable (> 3.0 sigma) in a Gaussian process regression. This can take a long time.
Traceback (most recent call last):
  File "/global/home/users/tin/gs/tin-gh/EToKi/modules/cgMLST.py", line 200, in <module>
    cgMLST(sys.argv[1:])
  File "/global/home/users/tin/gs/tin-gh/EToKi/modules/cgMLST.py", line 149, in cgMLST
    y = np.apply_along_axis(lambda d: np.unique(d[d >= 0]).size, 0, data) * 100. / np.sum(data > 0, 0)
        ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/global/scratch/users/tin/venv_stec/lib/python3.11/site-packages/numpy/lib/_shape_base_impl.py", line 383, in apply_along_axis
    raise ValueError(
ValueError: Cannot apply_along_axis when any iteration dimensions are 0

real 1084.71	# 18min06 
user 930.50
sys 32.31
1
Mon Aug 18 22:24:00 PDT 2025
 22:24:00 up 38 days,  9:46,  8 users,  load average: 0.80, 0.90, 1.16
(venv_stec) [tin@n0060 Test_Enterobase2]$ 

