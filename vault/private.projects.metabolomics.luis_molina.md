---
id: a5f4841e-0a88-474f-9369-1c6a1cba38e0
title: Luis_molina
desc: ''
updated: 1610631059913
created: 1609678304075
---

# Luis Molina and Lena

The projects aims to explore the metabolomics of dormant and non-dormant Arabidopsis seeds, different ecotypes

Preparing MN upload
3 files uploaded

-rwx------   1 pma  staff  3562351  7 déc 15:52 lena_pos_quant.csv
-rwx------@  1 pma  staff  2894190  7 déc 15:52 lena_pos.mgf
-rw-r--r--@  1 pma  staff     2619  3 jan 13:46 lena_metadata_gnps.tsv

Launched job https://gnps.ucsd.edu/ProteoSAFe/status.jsp?task=e97d9482aa464b699a547ecc7ebfd0a3 at 

        Read length of metadata 61
        Empty line filtered length of metadata 61
        filename header not in metadata file, please refer to documentation - https://ccms-ucsd.github.io/GNPSDocumentation/networking/#metadata 
        Tool execution terminates abnormally with exit code [1]

Problem is apparently because of the metadata file format which requires to have the term filename as header for the files. See doc here 

New job is https://gnps.ucsd.edu/ProteoSAFe/status.jsp?task=fcdc83b1a76c422d9a6d2ea2296d30d7

Qiime emperor plot https://view.qiime2.org/visualization/?type=html&src=https%3A%2F%2Fcors-anywhere.herokuapp.com%2Fhttps%3A%2F%2Fgnps.ucsd.edu%2FProteoSAFe%2FDownloadResultFile%3Ftask%3Dfcdc83b1a76c422d9a6d2ea2296d30d7%26file%3Dqiime2_output%2Fqiime2_emperor.qzv%26block%3Dmain
Indicates that we should remove bk to see something

Two files moved

-rwxr-xr-x 1 allardp utilisateurs du domaine   2789127 Jan  3 16:19 fbmn_lena_metabo_specs_ms.mgf
-rwxr-xr-x 1 allardp utilisateurs du domaine   1589444 Jan  3 16:20 fbmn_lena_metabo_attributes.tsv


# Set the tolerance to be used
TOLERANCE=0.01
# Score threshold
SCORE_THRESHOLD=0.2
# Top K results
TOP_K_RESULTS=50

running ISDB spectral match 

bash run_new_dnp_top50.sh fbmn_lena_metabo_specs_ms.mgf fbmn_lena_metabo_attributes.tsv fbmn_lena_metabo_results_DNP_top50.out

To fetch back data we use rsync
rsync -rvz -e 'ssh' --progress "allardp@x2go.epgl-geneve.org:/home/farma.unige.ch/allardp/Desktop/FARMAnetwork/RECHERCHE/COMMON\ FASIE-FATHO/PMA/Ubuntu_VM_img/ISDB_DNP/results/fbmn_lena_metabo_results_DNP_top50.out" ./ 
Note: double quotes allow to bypass the otherwise problematic \\

Taxo_scorer_evolved didnt work

(check with Adriano)

Used classical script
-rw-r--r--@   1 pma  staff      15942  3 jan 17:54 210103_taxo_classy_lena.Rmd
Output is 
-rw-r--r--   1 pma  staff    2366916  3 jan 17:52 fbmn_lena_metabo_results_DNP_top5_repond.tsv
