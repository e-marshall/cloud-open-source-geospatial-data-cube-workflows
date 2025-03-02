# Getting started

## *How to use this book*

Our goal is for this book to be useful to users across a range of backgrounds and with different needs and interests. It is designed to be a comprehensive walk-through of scientific workflows using earth observation data in Python. At the same time, we recognize some users may be interested in following individual segments and a more modular structure. Read from start to finish or check out the individual sections that interest you. To see which topics are covered in different notebooks, see the overview pages of each tutorial linked below, the [glossary](../pt4/glossary.md) or enter a specific term in the search bar to see the pages where it is used. todo decide about having glossary or not.

:::{admonition} Running tutorial notebooks on your own
Head to the [software](software.md) page for detailed instructions on how to get started running the tutorial notebooks on your own.
:::

## *Data used in this book*

Most of the examples in this book use data accessed programmatically from cloud-object storage. We make subsets of the data available in this book's Github repository to remove the need for computationally-intensive operations in the tutorials. In one example, working with Sentinel-1 data processed by Alaska Satelllite Facility, we start with data downloaded locally. Users who would like to complete this processing step on their own may do so (and access the data [here]()), but a smaller subset of this data is stored in the repository. For more detail on data used in this book see [Tutorial Data](../background/tutorial_data.md).


## *Overview of book*

### {{part1_title}}
Background on data cubes and an introduction to array-based geoscience data and how it is represented in Xarray and Python. This section provides an overview and explanations of topics that will be referenced in the applied tutorials.

### Part 1: {{part2_title}}
A tutorial focusing on [ITS_LIVE](https://its-live.jpl.nasa.gov/), a NASA MEASURES project and publicly accessible dataset stored in an AWS S3 repo as Zarr data cubes. 

### Part 2: {{part3_title}}
This [tutorial](sentinel1_intro.md) focuses on another satellite dataset: Sentinel-1 Radiometric Terrain Corrected imagery. Sentinel-1 is a synthetic aperture radar sensor; SAR data undergoes different types of processing for different scientific applications. Part 3 demonstrates how to access this data from two publicly available, online respositories: Alaska Satellite Facility and Microsoft Planetary Computer. These notebooks demonstrate the different ways to read this data and prepare it for analysis, as well as an initial comparison of the two datasets. 

Each tutorial focuses on a different type of remote sensing dataset and demonstrates how to assess and work through the nuances, details and challenges that can arise from each. A common characteristic of each dataset that is emphasized throughout the notebooks is working with larger-than-memory datasets on the computational resources of a standard laptop. 

### {{part4_title}}

A summary of the lessons learned throughout the tutorials and synthesis of these ideas into suggestions and best practices for developing scientific workflows analyzing n-dimensional earth observation data. 

## *Who is this book for?*

This book is for anyone who is interested in working with earth observation data in Python! Follow along from start to finish for a more comprehensive explanation on what we're doing and why, or drop in to the sections that interest you. We try to provide relevant domain and background information where necessary, and we direct the reader to helpful resources that provide more robust discussions of important concepts when appropriate.

We provide all of the resources necessary to work through the Jupyter Notebooks contained in these tutorials on your own machine. Some experience working with Python will be helpful, however the tutorials are designed to be beginner-friendly.

```{admonition} If you'd like a more thorough background on working with geospatial data in Python 
Check out [An Introduction to Earth and Environmental Data Science](https://earth-env-data-science.github.io/intro.html), which is based on a semester-long Columbia University course titled *Research Computing in Earth Science*.
```

The tutorials in this book include discussion of different types of geospatial data, especially data cubes. We include some background information, however, if these terms are new to you, we recommend checking out the following resources before getting started: 

- [**Intro to raster data**](https://datacarpentry.github.io/organization-geospatial/01-intro-raster-data.html#data-structures-raster-and-vector) - *Data Carpentry*
- [**Intro to vector data**](https://datacarpentry.github.io/organization-geospatial/02-intro-vector-data.html#about-vector-data) - *Data Carpentry*
- [**Data cubes**](https://openeo.org/documentation/1.0/datacubes.html#what-are-datacubes) - *openEO*

## *Learning objectives*

### Data cubes and array data structures
- Understanding fundamental structures of data cubes and how to organize earth observation datasets within this data model
- Using Xarray label-based indexing and selection to manipulate and organize multi-dimensional data objects
- Performing dimensional computations and visualizations with Xarray
- Visualizing and querying vector datasets with GeoPandas
- Using Xvec to create and use vector datasets, combining the functionality of Xarray and GeoPandas 
- Aligning and comparing two objects with different spatial resolutions

### Working with very large data
- How to read very large local data into memory using Gdal VRT 
- Parallelizing local data reads with Xarray `open_mfdataset()`
- Using dask to parallelize workflows in order to work with larger-than-memory data

### Reading and writing data
- Reading raster data from cloud object storage
- Handling geospatial metadata and geospatial operations involving array data using Xarray and Rioxarray
- Understanding STAC metadata specification and how to use it to query and read data from cloud object storage
- Reading and writing Zarr data cubes with Xarray


## *Xarray, Zarr, and the Pangeo software stack*

TODO include Dask in this section?

```{figure} logos/Xarray_Logo_RGB_Final.png
---
scale: 5%
align: right
---
```
**[Xarray](https://docs.xarray.dev/en/stable/#)** is a Python library and open-source project that introduces a data structure with named dimensions, coordinates and attributes that wrap NumPy-like arrays. This allows the co-location of raw data and metadata for complex, n-dimensional datasets in ways that streamline scientific analysis, enabling more consise, readable and intuitive workflows. 

```{figure} zarr_logo.png
---
scale: 50% 
align: right
---
```

**[Zarr](https://zarr.readthedocs.io/en/stable/#)** is a Python library for reading and writing data stored as Zarr groups and arrays. Zarr is built for array-like data and has flexible storage backends making it suitable data stored in local file systems as well as cloud object storage. 

```{figure} logos/pangeo_logo.png
---
scale: 50% 
align: right
---
```
**[Pangeo](https://www.pangeo.io/)** is a community scientists, developers, and practitioners dedicated to promoting open, reproducible, and scalable science. Members of the Pangeo community develop and contribute to open-source software libraries within the geosciences and across scientific domains, including Xarray, Dask, Zarr, and Jupyter.

In addition to these software libraries, the Pangeo community emphasizes the development of educational resources (see [Project Pythia](https://foundations.projectpythia.org/landing-page.html)), regular community [meetings](https://www.pangeo.io/meetings) and [showcase talks](https://www.pangeo.io/showcase), and working groups on specialized topics. 
