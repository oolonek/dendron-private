---
id: 1ceddd6b-6dd9-491f-b038-887d842142b7
title: Reports
desc: ''
updated: 1611682333386
created: 1611402281669
---

# 2021-01-23 13:16

Analysis report for Frederique Legendre with Metabomaps.

Gave me two extracts of Sariette and Hysope

![](/assets/images/2021-01-23-15-08-08.png)


Filenames

```bash
➜  Fred_Legendre ll
total 126424
-rwx------  1 pma  staff    21M  1 nov 13:05 201012_PMA5_33_01.mzXML
-rwx------  1 pma  staff    10M  1 nov 13:05 201012_PMA5_33_01_neg.mzXML
-rwx------  1 pma  staff    20M  1 nov 13:05 201012_PMA5_33_02.mzXML
-rwx------  1 pma  staff    10M  1 nov 13:05 201012_PMA5_33_02_neg.mzXML
```

No comparison is needed.
Will work on one at a time.

# Hysope pos

201012_PMA5_33_02.mzXML

## Let's adapt the mzxml template


[hysope_pos_batch_mzmine](../../../tmp/Fred_Legendre/hysope_pos.xml)

'~/tmp/Fred_Legendre/201012_PMA5_33_02.mzXML'

//TODO Script a way to generate the .xml batch templates

Maybe a quick workaround is to create a template file and then do a ctrl+f replace for each of the path_to_basefile strings.


## working on a small xml python based parser

Where did I put it !!!!
Did some stuff with etree ... where  is the shit ?



## MN job 

Launched automatically 

https://gnps.ucsd.edu/ProteoSAFe/status.jsp?task=56d01c6ccfe143eca5252017202c8fef

## matchms to proceed to insilico annotations

`python spectral_lib_matcher.py /Users/pma/Dropbox/Research_UNIGE/git_repos/taxoscorer/data_in/hysope/spectra/specs_ms.mgf /Users/pma/tmp/ISDB_DNP_msmatchready.mgf 0.01 0.01 0.2 6 /Users/pma/Dropbox/Research_UNIGE/git_repos/taxoscorer/data_in/hysope/hysope_pos_matchmsed_ISDB_DNP.tsv`

