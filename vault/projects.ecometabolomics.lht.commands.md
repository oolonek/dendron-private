---
id: 9fe3dee5-82d0-4a4b-804a-68b9b2ac3063
title: Commands
desc: ''
updated: 1603447443886
created: 1603447443886
stub: false
---

Python commands used to sanitize the compadre_gen_chem.csv.gz file


```bash
(chemosan_env) ➜  chemo_sanitizer git:(master) ✗ python src/scripts/chemosanitizer.py ~/Dropbox/LHT-metabolomes/Data/compadre_gen_chem.csv.gz ~/Dropbox/LHT-metabolomes/Data/compadre_gen_chem_sanitized.csv.gz InChI_DNP 12
```

Then in python 

```py
>>> from chemosanitizer.chemosanitizer import gzipper
>>> gzipper('/Users/pma/Dropbox/LHT-metabolomes/Data/compadre_gen_chem_sanitized.csv', '\t', ',')
```

We can now load the dt in datawarrior.

