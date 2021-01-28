---
id: bf51881f-1334-42da-b762-1ea39617b614
title: Report
desc: ''
updated: 1611682057708
created: 1610631059696
html:
  embed_local_images: true
  embed_svg: true
  offline: true
  toc: true
print_background: false
export_on_save:
  html: true
toc:
  depth_from: 1
  depth_to: 6
  ordered: false
---

[TOC]


# 2021-01-14 Report 

[updated 2021-01-20 08:24]

## Research question and background

![](/assets/images/2021-01-12-19-00-32.png)


## Preliminary results

### LCMS profiling

#### Pos mode, Orbitrap, ddMS2


![](/assets/images/2021-01-12-19-05-46.png)

- First observation : the profile are nicely aligned and we see peeks ! Sample prep is OK.

//DONE ~~Ask Luis and Lena: what is the exact nature of the samples ~~
Made by Thanise, should check her lab-book



### Multivariate data analysis

#### Unsupervised 

##### Ecotype mapping
After alignement we can have a look at the unsupervised analysis.
Here after the removal of three outliers (Col1, Ler27 and WS2AR)
Color code according to Ecotype

![](/assets/images/2021-01-12-19-13-50.png)

We can see a clear grouping according to ecotype on PC1/PC2

##### Treatment mapping (None/AR)

![](/assets/images/2021-01-12-19-17-38.png)

Treatment effects are confounded on PC1/PC2

We decide to check for the treatment effect at each ecotype level

The same is observed on the other components 

![](/assets/images/2021-01-12-19-48-21.png)

##### Treatment mapping (None/AR) for Col

![](/assets/images/2021-01-12-19-22-09.png)


##### Treatment mapping (None/AR) for Cvi

![](/assets/images/2021-01-12-19-23-24.png)


##### Treatment mapping (None/AR) for Ler

![](/assets/images/2021-01-12-19-27-09.png)

##### Treatment mapping (None/AR) for WS

![](/assets/images/2021-01-12-19-31-17.png)

Hard to distinguish overall, even tough it appears that there is clustering for some of the ecotypes.




#### Supervised

In order to check more in details we used supervised analysis to force group discrimination 
We use the exported feature table (/Users/pma/tmp/Lena_metabo_local/lena_pos_ttmt_MA.csv) in Metaboanalyst


_Samples are in columns and features in rows.
The uploaded file is in comma separated values (.csv) format.
The uploaded data file contains 48 (samples) by 3390 (peaks(mz/rt)) data matrix.
Samples are not paired.
2 groups were detected in samples.
Only English letters, numbers, underscore, hyphen and forward slash (/) are allowed.
Other special characters or punctuations (if any) will be stripped off.
Non-numeric values were found and replaced by NA.
70 features with a constant or single value across samples were found and deleted.
A total of 14061 (8.8%) missing values were detected.
_

No normalization.
No scaling.


As you might know, OPLSDA allways works !

![](/assets/images/2021-01-12-19-51-34.png)

Small cluster of interest in the S-Plot indicating up regulated feature in the AR group


![](/assets/images/2021-01-12-19-58-44.png)


#### Volcano plot

![](/assets/images/2021-01-12-20-14-04.png)

We can check here for feature presenting the alternative pattern : over-expression in the None treatment (Freezer). However the signals are not as clear, indeed if you look closely only a subset of the None treated samples express these ions.


#### Heatmap

![](/assets/images/2021-01-14-13-34-35.png)

Detailed view on the top 60 

![](/assets/images/2021-01-14-13-36-50.png)


### Molecular Networks


In order to have some qualitative insights on the feature higlighted by the stats we build a molecular network on the MSMS of the acquired spectra and map the metadata information.

#### MN ecotype mapping
![](/assets/images/2021-01-14-13-55-48.png)

Some families of metabolites are ecotype dependant, other are ubiquitous.

#### MN treatment mapping

![](/assets/images/2021-01-14-14-04-35.png)

4 clusters in blue (No treatment) clearly pop out.

#### MN ecotype + treatment mapping

![](/assets/images/2021-01-14-14-15-53.png)

This last mapping (ecotype + treatment ) indicate that within the 4 previous clusters 2 are Ler related and 2 are Col related.

#### MN individual mapping

🖐️ **We have to be careful here **🖐️

At the last meeting when doing the individual mapping it appears that the clusters of interest we were focussing upon are mostly restricted to a single individual. Ler 27 and Col 1.
This could indicate :
* a high biological variability
* contamination by external analytes

To be assesed in the next metabolomics round


See example below on Cluster 1 mostly constituted by Ler 27.
![](/assets/images/2021-01-20-08-23-15.png)

## Metabolite annotation 


![](/assets/images/2021-01-14-14-45-30.png)

![](/assets/images/2021-01-14-14-46-44.png)

Some biblio on alkanolamides and Arabido.

https://www.pnas.org/content/pnas/103/32/12197.full.pdf



# Next Steps : 

- [ ] ask Luis and Lena the extraction protocol
- [ ] reanalyse a batch of seeds _**together with appropriate extraction blancks** _


![](/assets/images/2021-01-22-10-18-53.png)
