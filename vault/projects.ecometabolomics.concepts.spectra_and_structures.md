---
id: a150e7ae-9b13-4e69-a596-952829bf9b8f
title: Spectra_and_structures
desc: ''
updated: 1601481291785
created: 1601481291785
stub: false
---

# Spectra and molecular structures

## Context (of the paper/doc/note/paragraph)
To compare plants via their metabolomes it is necessary to align their individual constituents which are metabolites. These metabolites are classically called "features". In LCMS-based metabolomics a feature is typically defined by its retention time (on a given chromatographic column), by its intensity and by its MS spectra at different levels. The MS1 level is the m/z ratio of the intact feature, while the MS2 (or MSMS) corresponds to a m/z ratios of the fragments of a feature. Each of these m/z ratios are associated to an intensity which is not always proportional to the amount of the feature but which is rather defined by the chemical groups of the analyte (ionization response). Additionally a chemical structure can be linked to a feature if a metabolite annotation process is carried. 
Some of the features dimensions obtained in LCMS-based metabolomics are highly analytical platform dependant. 
## Need (of the paper/doc/note/paragraph)
In ecometabolomics, it will be necessary to compare large datasets. The size of these dataset will imply long acquisition time within a lab or comparison of dataset acquired across different laboratories.

## Task (of the paper/doc/note/paragraph)
It is thus crucial for "good ecometabolomics practices" to define the pro and cons of the different features dimensions and select the ones which are pertinent for such large scale, multi-matrix, multi lab comparisons.
## Object (of the paper/doc/note/paragraph)
Here we will discuss the importance of the spectral and molecular structure dimensions associated to metabolomics features and propose a rationale for the optimal exploitation in an ecometabolomics perspective.



To tackle the problem of features comparison across metabolomics datasets, dropping the retention time and intensity dimensions appear as an interesting option. These two values, which are the first to be considered to plot a chromatogram, suffer from different weaknesses. Retention time, on one side, is extremely dependant on the gradient and the phase chemistry of the chromatographic column. Apart from a broad polarity range, it does not bring much to the feature classification process. Intensity, on the other hand, is dependant the ionization response of the feature. This means that is not alway quantitative and that, for example minute amount of a given alkaloid (an easily ionized class of compounds in positive ionization mode) could have a higher intensity than larger amounts of an unfunctionalized terpene. To complicate things, intensity is dependant on the MS architecture. These two dimensions (retention time and intensity) are tricky to compare within a metabolomics dataset acquired on a given analytical platform. They are virtually impossible to compare across different labs using different LCMS architectures.
So we are left with two objects: the spectral data and the molecular structures. These two objects also happen to be very information rich compared to retention time and intensity. We will describe each of them in more details and discuss optimal ways for the exploitation.
