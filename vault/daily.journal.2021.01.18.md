---
html:
  embed_local_images: true
  embed_svg: true
  offline: true
  toc: true

print_background: false

toc:
  depth_from: 1
  depth_to: 6
  ordered: false

export_on_save:
  html: true


id: 49db2148-3366-4642-a760-892d3bb08ce5
title: '18'
desc: ''
updated: 1611823799711
created: 1610973802298

---
[TOC]



# Monday 18 January


- `13:43` //_Let's start_
- `13:44` Tom Walker soil metabo

- [x] ~~find back the samples coord~~
>> PMA5_35_x

![](/assets/images/2021-01-27-12-43-55.png)

- [x] ~~find back the files~~
Found them. Beware they have been wrongly name PMA5_37_x (thus overlapping with tramadol series). Now definitively renaming them to PMA5_35_x

`for f in *.mzML; do echo mv "$f" "${f/_37_/_35_}"; done`

After installation of mono and the ThermoFileParser we can directly 

`mono ThermoRawFileParser.exe -d=/Users/pma/tmp/bafu_ecometabo/raw -o=/Users/pma/tmp/bafu_ecometabo/converted`


We move all file with a specific pattern to a specific folder (separate pos and neg)

```bash
mkdir neg
mkdir pos
mv *_neg.mzML neg/
mv *.mzML pos/
```


- [x] mzmine treatment


Starting MzMine from the cli

```bash
sh ../../Applications/MZmine-2.53-macOS/startMZmine-macOS
```

Batch file is created [batch_file](../../../tmp/bafu_ecometabo/bafu_ecometabo_batch_mzmine.xml)

It can be edited directly for variables. Work on this.

Exports and launches FBMN
and sirius mgf

🖐️ The gnps metadata file should be named as *.csv else it is not taken by the automatic upload system.
However it must be in fact tab separated. So basically you need to have a tsv file but with the csv extension.



//TODO work on Sirius automation via the cli

# Report

## Overview of the pos profiles

![](/assets/images/2021-01-18-14-44-39.png)


## Metadata file creation 

`ls converted/pos/ > bafu_ecometabo_pos_metadata.csv`

Not optimal. To dig
For mzmine the metadata should be comma separated csv


## PCA 

PMA5_35_07.mzML is a clear outlier. Nothing was injected 

![](/assets/images/2021-01-18-15-04-46.png)

## Metaboanalyst export

This can also be automated however at least 3 replicate / group must be present.
Here I manually removed the BK.

//TODO check for a manner to automated this

![](/assets/images/2021-01-18-16-06-11.png)

![](/assets/images/2021-01-18-16-05-20.png)

![](/assets/images/2021-01-18-16-07-18.png)

Example of automatically generated [report](../../../tmp/bafu_ecometabo/Analysis_Report_bafu_metabo.pdf)



- [x] mn

Was automatically sent by the mzmine batch command.
Job is here https://gnps.ucsd.edu/ProteoSAFe/status.jsp?task=7f1259a161974b9fa4215b1f2a6dca5e

You can check the cscs (spectrally informed distance) interactively over here https://view.qiime2.org/visualization/?type=html&src=https%3A%2F%2Fcors-anywhere.herokuapp.com%2Fhttps%3A%2F%2Fgnps.ucsd.edu%2FProteoSAFe%2FDownloadResultFile%3Ftask%3D7f1259a161974b9fa4215b1f2a6dca5e%26file%3Dqiime2_output%2Fqiime2_emperor.qzv%26block%3Dmain

As seen is the screenshot below there is a nice grouping of the samples.
Lotus and Arrhentherum appear very close in this cscs space.

![](/assets/images/2021-01-20-19-23-12.png)


- [x] annotation

Let's use matchms here.

```bash
python spectral_lib_matcher.py  /Users/pma/tmp/ISDB_DNP_msmatchready.mgf 0.01 0.01 0.2 6 /Users/pma/tmp/bafu_ecometabo/FBMN_bafu_ecometabo_pos/FBMN_bafu_ecometabo_pos_msmatched_ISDB_DNP.out
```



output is there /Users/pma/tmp/bafu_ecometabo/FBMN_bafu_ecometabo_pos/FBMN_bafu_ecometabo_pos_msmatched_ISDB_DNP.out

No we'll try to load this in the python taxo reponderator

[metadata_table](../../../tmp/bafu_ecometabo/GNPS_output/metadata_table/metadata_table-00000.txt)


[repond_table](../../../tmp/bafu_ecometabo/GNPS_output/bafu_ecometabo_spectral_match_results_repond.tsv)


# Molecular Networks

Four views of the common Molecular Network according to peak heights in different samples

Allows to have a quick idea of common/unique compounds families and overall molecular diversity of the samples ...

![Common MN - node size according to Plantago_lanceolata peak heights](/assets/images/2021-01-27-12-04-37.png)

![Common MN - node size according to Arrhenatherum_elatus peak heights](/assets/images/2021-01-27-12-02-15.png)

![Common MN - node size according to Lotus_corniculatus peak heights](/assets/images/2021-01-27-12-04-07.png)

![Common MN - node size according to Soil samples peak heights](/assets/images/2021-01-27-12-03-43.png)



![A cluster of Plantago_lanceolata chracteristic tyrosol derivatives](/assets/images/2021-01-27-11-59-00.png)

![A cluster of glycosylated flavonoids derivatives previously reported in Poaceae](/assets/images/2021-01-27-12-16-04.png)

![Typical isoflavonoids derivatives of Fabaceae, some found in Lotus sp.](/assets/images/2021-01-27-12-18-34.png)

![Structure dereplicated in the soil samples](/assets/images/2021-01-27-12-21-57.png)

![Two molecular families of long chain pyrolidines found in soil sample majoritarly but also in Arrhenatherum_elatus and Lotus_corniculatus, much less in Plantago_lanceolata](/assets/images/2021-01-27-12-34-24.png)



## Summary

## For Tom and Chelsea:

- Good quality of the profiles (only treated pos mode)
- sample prep looks OK and yields rich profiles. 1/10 dry weight/solvant in 100% MeOH, sonicated and centrifuged.
- data treatment in classical MVDA (PCA, HClust) yields clear separation of the 3 samples and the soil.
- CSCS indicate similar clustering than MVDA
- MN yields further info on metabolic richness, and with taxonomically informed metabolite annotation yields well annotated clusters of both taxonomically relevant and structurally consistent annotation. 
    - **Plants:** Overall quality of annotations looks very good.
    - **Soil samples:** harder to say, no way to input taxo information. Much less clusters. Some appear to be consistently annotated but have to make sense of the origin of the compounds. Two clusters appear to be both present in 2 plant samples and the soil)


# Next steps 

##  Questions for Tom
- Do you have more info on the soil samples origin ? Were they taken at the same place than the plants ?
- Were these potentially cultivated soils ?

## Sampling schema

proposed by Tom and resuming the last discussion with him, Chelsea, JL and Julien

As for samples/plots, my understanding is as follows:

* 44 x aggregate sub-plot tissue samples (one per plot, most representative)
* 9 x additional sub-plot tissue samples (three remaining sub-plots from three plots - to check sub-plot variability)
* 44 x sub-plot soil samples (to match to selected sub-plot tissue samples)
* 44 x plot-level soil samples (aggregated sample of all sub-plots to match to other soil measurements)