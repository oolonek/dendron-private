---
id: b4e81362-89fd-498f-ae7a-96bcbc414e9d
title: Mandelbrot
desc: ''
updated: 1610474076066
created: 1610388155072
---

# Mandelbrot project

https://github.com/mandelbrot-project

## Spectral tmap

By combining spec2vec to transform spectra to words and the tmap vizualisation is is possible to build trees of features.

We can actually inform each of the spectral vectors with whichever word. We tried to add a biological classification allowing to generate bioinformed spectral tmaps

https://github.com/mandelbrot-project/spectral_tmap/commit/b397d93c7ef3bd1935baa1d7a73e522acbd37411


Now I would like to see if we can build tmap over individual mgf files instead of using a previously alligned mgf.
This would solve some problems in the frame of our project such as alignement or batch effects.

2021-01-11 19:20
I will work on the Ecometabolomics toy dataset for this 

https://drive.switch.ch/index.php/apps/files/?dir=/ecometabolomics/sDIV&fileid=2836665756


Find a way to convert msfiles on mac terminal (at least .mzXML to .mgf should be possible). This should help https://github.com/compomics/ThermoRawFileParser

