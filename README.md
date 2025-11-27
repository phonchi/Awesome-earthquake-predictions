# Awesome-earthquake-predictions
[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)


This repository is a curated list of earthquake prediction models, forecasting tools, and the comprehensive computational ecosystem that supports modern seismology.

The scope covers the full pipeline: **Data Acquisition** -\> **Deep Learning Detection** -\> **Association & Location** -\> **Source Characterization** -\> **Structural Imaging** -\> **Forecasting** -\> **Hazard Assessment**.

The format for the item is `[software link]` - `[Paper link]` (Description / Availability).

-----

# Resources

## General Resources

  * [Awesome Open Geoscience](https://github.com/softwareunderground/awesome-open-geoscience)
    \*([https://github.com/schipp/awesome-seismology](https://github.com/schipp/awesome-seismology))
    \*([https://seismo-live.org/](https://www.google.com/search?q=https://seismo-live.org/)) - Interactive Jupyter notebooks for seismology.

## Tutorials & Learning

\*([https://seismo-learn.org/seismology101/](https://seismo-learn.org/seismology101/))
\*([https://migg-ntu.github.io/SeisTomo\_Tutorials/index.html](https://migg-ntu.github.io/SeisTomo_Tutorials/index.html))
\*([https://github.com/seisbench/seisbench/tree/main/examples](https://github.com/seisbench/seisbench/tree/main/examples)) - Tutorials for applying deep learning to seismic data.

## Datasets

\*([https://github.com/smousavi05/STEAD](https://github.com/smousavi05/STEAD)) -([https://ieeexplore.ieee.org/document/8871127](https://ieeexplore.ieee.org/document/8871127)) (Global waveform dataset for AI).
\*([https://github.com/seismic-instance/INSTANCE](https://www.google.com/search?q=https://github.com/seismic-instance/INSTANCE)) -([https://essd.copernicus.org/articles/13/5509/2021/](https://essd.copernicus.org/articles/13/5509/2021/)) (High-quality dataset with noise and event waveforms).
\*([https://horus.bo.ingv.it/](https://horus.bo.ingv.it/)) - High-quality hypocenter catalog for Italy.

-----

# 1\. Infrastructure & Big Data

*Foundational libraries for handling waveforms, massive parallel processing, and database management.*

  * [`ObsPy`](https://www.google.com/search?q=%5Bhttps://github.com/obspy/obspy%5D\(https://github.com/obspy/obspy\)) -([https://pubs.geoscienceworld.org/ssa/srl/article/81/3/530/143680/ObsPy-A-Python-Toolbox-for-Seismology](https://www.google.com/search?q=https://pubs.geoscienceworld.org/ssa/srl/article/81/3/530/143680/ObsPy-A-Python-Toolbox-for-Seismology)) (The industry standard for reading/writing seismic data).
    \*([https://github.com/mspass-team/mspass](https://github.com/mspass-team/mspass)) -([https://pubs.geoscienceworld.org/ssa/srl/article/93/2A/961/611892/MsPASS-Massively-Parallel-Analysis-System-for](https://www.google.com/search?q=https://pubs.geoscienceworld.org/ssa/srl/article/93/2A/961/611892/MsPASS-Massively-Parallel-Analysis-System-for)) (Big data framework bridging ObsPy with HPC/Cloud using MongoDB and Dask).
  * [`Pyrocko`](https://www.google.com/search?q=%5Bhttps://pyrocko.org/%5D\(https://pyrocko.org/\)) - [**Pyrocko: An open-source seismology toolbox and library**](https://pyrocko.org/) (Advanced waveform analysis, Green's functions, and visualization with Snuffler).
  * [`PyMoab`](https://www.google.com/search?q=%5Bhttps://github.com/pysmo/pysmo%5D\(https://github.com/pysmo/pysmo\)) - (Python interface to the Mesh-Oriented dAtaBase for handling complex mesh data in simulations).

# 2\. Detection & Picking (Deep Learning & Templates)

*Tools for identifying P-wave and S-wave arrivals in noisy data.*

\*([https://github.com/seisbench/seisbench](https://github.com/seisbench/seisbench)) -([https://seismica.library.mcgill.ca/article/view/284](https://www.google.com/search?q=https://seismica.library.mcgill.ca/article/view/284)) (A unified framework hosting models like PhaseNet, EQTransformer, and benchmarking datasets).

  * [`PhaseNet`](https://www.google.com/search?q=%5Bhttps://github.com/AI4EPS/PhaseNet%5D\(https://github.com/AI4EPS/PhaseNet\)) -([https://academic.oup.com/gji/article/216/1/261/5129142](https://academic.oup.com/gji/article/216/1/261/5129142)) (Specializes in precise P/S arrival time picking using U-Net).
    \*([https://github.com/smousavi05/EQTransformer](https://github.com/smousavi05/EQTransformer)) - [**Earthquake transformer: an attentive deep-learning model for simultaneous earthquake detection and phase picking**](https://www.nature.com/articles/s41467-020-17591-w) (Simultaneous detection and picking using attention mechanisms).
  * [`EQcorrscan`](https://www.google.com/search?q=%5Bhttps://github.com/eqcorrscan/EQcorrscan%5D\(https://github.com/eqcorrscan/EQcorrscan\)) -([https://pubs.geoscienceworld.org/ssa/srl/article/89/1/173/525791/EQcorrscan-Repeating-and-Near-Repeating](https://www.google.com/search?q=https://pubs.geoscienceworld.org/ssa/srl/article/89/1/173/525791/EQcorrscan-Repeating-and-Near-Repeating)) (Template matching and subspace detection for finding hidden earthquakes).
    \*([https://github.com/ahotovec/REDPy](https://github.com/ahotovec/REDPy)) -([https://pubs.geoscienceworld.org/ssa/srl/article/87/6/1384/348259/REDPy-A-Python-Client-for-Automated-Detection-and](https://www.google.com/search?q=https://pubs.geoscienceworld.org/ssa/srl/article/87/6/1384/348259/REDPy-A-Python-Client-for-Automated-Detection-and)) (Unsupervised clustering and discovery of repeating earthquake families).

# 3\. Association & Location

*Algorithms to link phases into events and determine hypocenters (Time, Lat, Lon, Depth).*

  * [`GaMMA`](https://www.google.com/search?q=%5Bhttps://github.com/AI4EPS/GaMMA%5D\(https://github.com/AI4EPS/GaMMA\)) -([https://agupubs.onlinelibrary.wiley.com/doi/full/10.1029/2021JB023249](https://agupubs.onlinelibrary.wiley.com/doi/full/10.1029/2021JB023249)) (Probabilistic association, ideal for dense/noisy AI-generated picks).
  * [`PyOcto`](https://www.google.com/search?q=%5Bhttps://github.com/yetinam/pyocto%5D\(https://github.com/yetinam/pyocto\)) - [**PyOcto: A high-throughput seismic phase associator**](https://seismica.library.mcgill.ca/article/view/1130) (Extremely fast associator based on octree search, C++ backend).
  * [`QuakeMigrate`](https://www.google.com/search?q=%5Bhttps://github.com/QuakeMigrate/QuakeMigrate%5D\(https://github.com/QuakeMigrate/QuakeMigrate\)) -([https://eartharxiv.org/repository/view/9745/](https://eartharxiv.org/repository/view/9745/)) (Waveform stacking/migration method, excellent for low SNR environments).
  * [`NonLinLoc`](https://www.google.com/search?q=%5Bhttps://github.com/alomax/NonLinLoc%5D\(https://github.com/alomax/NonLinLoc\)) -([http://alomax.free.fr/nlloc/](http://alomax.free.fr/nlloc/)) (The standard for probabilistic location, producing scatter clouds of uncertainty; Python wrappers available).
    \*([https://www.ldeo.columbia.edu/\~felixw/DD.html](https://www.ldeo.columbia.edu/~felixw/DD.html)) -([https://pubs.geoscienceworld.org/ssa/bssa/article-abstract/90/6/1353/120427/A-Double-Difference-Earthquake-Location-Algorithm](https://www.google.com/search?q=https://pubs.geoscienceworld.org/ssa/bssa/article-abstract/90/6/1353/120427/A-Double-Difference-Earthquake-Location-Algorithm)) (The gold standard for relative relocation to sharpen fault structures).
  * [`GrowClust`](https://www.google.com/search?q=%5Bhttps://github.com/dttrugman/GrowClust%5D\(https://github.com/dttrugman/GrowClust\)) -([https://pubs.geoscienceworld.org/ssa/srl/article/88/2A/379/353686/GrowClust-A-Hierarchical-Clustering-Algorithm-for](https://www.google.com/search?q=https://pubs.geoscienceworld.org/ssa/srl/article/88/2A/379/353686/GrowClust-A-Hierarchical-Clustering-Algorithm-for)) (Efficient relative relocation using cluster analysis).

# 4\. Source Characterization

*Determining "how" the earthquake broke (Focal Mechanisms, Moment Tensors).*

\*([https://github.com/mtuqorg/mtuq](https://github.com/mtuqorg/mtuq)) -([https://pubs.geoscienceworld.org/ssa/srl/article/91/4/2260/583590/A-Python-Based-Software-Package-for-Moment-Tensor](https://www.google.com/search?q=https://pubs.geoscienceworld.org/ssa/srl/article/91/4/2260/583590/A-Python-Based-Software-Package-for-Moment-Tensor)) (Bayesian full moment tensor inversion with uncertainty quantification).

  * [`Grond`](https://www.google.com/search?q=%5Bhttps://pyrocko.org/grond/%5D\(https://pyrocko.org/grond/\)) - [**Grond: A probabilistic earthquake source inversion framework**](https://pyrocko.org/grond/) (Bootstrap-based probabilistic inversion for source parameters, part of Pyrocko).
    \*([https://code.usgs.gov/esc/SKHASH](https://code.usgs.gov/esc/SKHASH)) -([https://pubs.geoscienceworld.org/ssa/srl/article/95/2/955/633457/SKHASH-A-Python-Package-for-Computing-Earthquake](https://www.google.com/search?q=https://pubs.geoscienceworld.org/ssa/srl/article/95/2/955/633457/SKHASH-A-Python-Package-for-Computing-Earthquake)) (Modern Python implementation of the HASH polarity algorithm, supports consensus polarity).
    \*([https://github.com/SeismicSource/sourcespec](https://github.com/SeismicSource/sourcespec)) - (Inversion of P/S displacement spectra for source parameters like corner frequency and stress drop).
    \*([https://github.com/geophysics/MoPaD](https://github.com/geophysics/MoPaD)) -([https://pubs.geoscienceworld.org/ssa/srl/article/83/3/589/349070/MoPaD-Moment-Tensor-Plotting-and-Decomposition-A](https://www.google.com/search?q=https://pubs.geoscienceworld.org/ssa/srl/article/83/3/589/349070/MoPaD-Moment-Tensor-Plotting-and-Decomposition-A)) (The standard tool for decomposing and plotting beachballs).

# 5\. Structural Imaging

*Imaging the earth beneath the stations.*

\*([https://github.com/paudetseis/RfPy](https://github.com/paudetseis/RfPy)) - (Calculates receiver functions using multitaper/Wiener deconvolution).
\*([https://github.com/xumi1993/seispy](https://github.com/xumi1993/seispy)) -([https://pubs.geoscienceworld.org/ssa/srl/article/94/2A/935/619623/Seispy-Python-Module-for-Batch-Calculation-and](https://www.google.com/search?q=https://pubs.geoscienceworld.org/ssa/srl/article/94/2A/935/619623/Seispy-Python-Module-for-Batch-Calculation-and)) (Includes CCP stacking and anisotropy analysis).

# 6\. Statistical Analysis & Catalogs

*Analyzing the resulting earthquake catalogs (b-value, completeness).*

\*([https://github.com/swiss-seismological-service/SeismoStats](https://github.com/swiss-seismological-service/SeismoStats)) -([https://arxiv.org/abs/2511.04521](https://arxiv.org/abs/2511.04521)) (Modern Python replacement for ZMAP; calculates Gutenberg-Richter $a/b$-values and $M_c$).
\*([https://geoscience-community-codes.github.io/GISMO/](https://geoscience-community-codes.github.io/GISMO/)) - (MATLAB toolbox for seismic data analysis and visualization).

# 7\. Forecasting Models

*Algorithms for generating earthquake probabilities (ETAS, Deep Learning).*

\*([https://github.com/keliankaz/recast](https://github.com/keliankaz/recast)) -([https://agupubs.onlinelibrary.wiley.com/doi/full/10.1029/2023GL103982](https://www.google.com/search?q=https://agupubs.onlinelibrary.wiley.com/doi/full/10.1029/2023GL103982)) (Neural Temporal Point Process model surpassing ETAS on large datasets).
\*([https://github.com/Rose-STL-Lab/DeepSTPP](https://github.com/Rose-STL-Lab/DeepSTPP)) -([https://arxiv.org/abs/2205.11663](https://arxiv.org/abs/2205.11663)) (Spatio-temporal forecasting using deep learning).
\*([https://github.com/smancini2/simplETAS/](https://github.com/smancini2/simplETAS/)) -([https://pubs.geoscienceworld.org/ssa/srl/article-abstract/95/1/38/628378/SimplETAS-A-Benchmark-Earthquake-Forecasting-Model](https://www.google.com/search?q=https://pubs.geoscienceworld.org/ssa/srl/article-abstract/95/1/38/628378/SimplETAS-A-Benchmark-Earthquake-Forecasting-Model)) (Standard statistical epidemic-type forecasting).
\*([https://github.com/lmizrahi/etas](https://github.com/lmizrahi/etas)) - (Tools for ETAS parameter estimation).

# 8\. Forecast Testing & Evaluation

*Frameworks for validating predictions against observed data.*

\*([https://github.com/SCECCode/pycsep](https://github.com/SCECCode/pycsep)) -([https://pubs.geoscienceworld.org/ssa/srl/article/93/5/2858/615824/pyCSEP-A-Python-Toolkit-for-Earthquake-Forecast](https://pubs.geoscienceworld.org/ssa/srl/article/93/5/2858/615824/pyCSEP-A-Python-Toolkit-for-Earthquake-Forecast)) (The official toolkit of the CSEP testing centers for rigorous forecast evaluation).

# 9\. Hazard & Risk Assessment

*Tools for translating forecasts into ground motion and risk.*

  * [`OpenQuake Engine`](https://www.google.com/search?q=%5Bhttps://github.com/gem/oq-engine%5D\(https://github.com/gem/oq-engine\)) -([https://www.globalquakemodel.org/openquake](https://www.globalquakemodel.org/openquake)) (Global standard for PSHA and risk calculation).
  * [`nshmp-haz`](https://www.google.com/search?q=%5Bhttps://github.com/usgs/nshmp-haz%5D\(https://github.com/usgs/nshmp-haz\)) - (USGS National Seismic Hazard Model Project code).
    \*([https://github.com/opensha/opensha](https://github.com/opensha/opensha)) - (Java-based framework for seismic hazard analysis).

# 10\. End-to-End Workflows

*Integrated pipelines combining the above tools.*

  * [`QuakeFlow`](https://www.google.com/search?q=%5Bhttps://github.com/AI4EPS/QuakeFlow%5D\(https://github.com/AI4EPS/QuakeFlow\)) -([https://academic.oup.com/gji/article/232/1/684/6694250](https://academic.oup.com/gji/article/232/1/684/6694250)) (Cloud-native pipeline integrating PhaseNet, GaMMA, and relocation).
    \*([https://github.com/projectisp/SurfQuake](https://www.google.com/search?q=https://github.com/projectisp/SurfQuake)) - (Streamlines the workflow from picking to moment tensor inversion with a GUI).
