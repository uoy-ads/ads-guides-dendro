---
authors:
  - name: null
---

# 2 Creating Dendrochronological Data

## 2.1 Project Planning and Requirements

Project planning requirements will vary dramatically depending on many factors including: the type of object(s); state of preservation; species; size of samples; whether destructive sampling is allowed; financial resources.  What and how to sample should be carefully considered following standard dendrochronological procedures (table 1) while making informed decisions about what metadata to collect.  


```{list-table} Table 1: Examples of national guidelines for dendrochronological analyses. 
:header-rows: 1
* - Country
  - Author
  - Year
  - Title
* - NL
  - Jansma
  - 2002
  - Veldhandleiding dendrochronologisch onderzoek
* - NL
  - Jansma
  - 2006
  - Nederlandse onderzoeksagenda voor archeologie: Dendrochronologie
* - UK
  - Historic England
  - 1998
  - Dendrochronology: Guidelines on producing and interpreting dendrochronological dates
* - IT
  - UNI
  - 2004
  - Cultural heritage - Wooden artefacts - Wood dendrochronological dating guidelines
```

Metadata should follow the Tree Ring Data Standard (TRiDaS) data model which provides the ability to record a wealth of information.  Not all TRiDaS fields will be applicable at any one time, but consider recording as much metadata as possible without adding an undue burden to the project.  If you have very simple research goals you may need very little metadata to achieve your aims, but with the addition of just a few metadata fields, it is likely your dataset will be of much greater use to you and fellow researchers in the future. 

```{figure} ../images/datamodel2.png
:alt: Figure 1

__Figure 1__: Diagram show the general structure of the Tree Ring Data Standard (TRiDaS) data\\model. For further description of the component parts of the model see the glossary.
```

## 2.2 Sources of Data

Dendrochronological data is typically generated either by the measurement of rings using a standard measurement platform (e.g. Velmex, Lintab, Catras, etc.) or via the manual measuring of rings with a hand lens.  Using either method, the resulting data typically ends up in specialist dendrochronological software for analysis.

## 2.3 File Types (whilst creating, working with, and processing data)

There are currently approximately 24 different dendrochronological data formats in use within the dendrochronological community.  While most are adequate for creating and analysing dendrochronological ring-width series, many of these formats are read by just one or two programs making them unsuitable for archival or data sharing.

Probably the most commonly used format worldwide is the Tucson decadal format which has been used since the late 1970s.  It’s a relatively simple ASCII-based format based upon the structure of the punch cards it replaced.  Whilst very common in laboratories around the world, the format has a number of limitations, not least the fact it has almost no capacity to store associated metadata.  Limitations with regards the storage of metadata within the format, and the lack of a formal standardisation procedure have meant that a variety of ad hoc methods have been introduced by users and software developers over the decades. These result in digital ambiguities and incompatibilities. 

Other popular formats, especially in Europe, are Heidelberg and CATRAS. The CATRAS format was designed for the program of the same name [@aniol1983tree; @aniol1987new], while the Heidelberg format was developed for use with TSAP [@rinn2005]. Both formats have some support in some other dendrochronological applications, but this support varies, especially with regards their less popular features. The CATRAS format is an undocumented proprietary binary format and as such we strongly recommend against using it for archiving or data sharing.  In comparison, Heidelberg files are plain-text and the format is relatively well documented.  While still not ideal for archival purposes, Heidelberg files are suitable for short-term storage and sharing of data.

The Tree Ring Data Standard (TRiDaS) was introduced in 2010 as a universal format for describing any sort of tree-ring data or metadata.  We strongly recommend using the TRiDaS format for the long-term storage of dendrochronological data and metadata. One major obstacle to the universal adoption of TRiDaS is the availability of applications and utilities for processing and working with TRiDaS format data.  At the time of writing this guide, the only application suitable for day-to-day collection, analysis and management of native TRiDaS data is Tellervo [@brewer2014data; @brewer2010new].  A number of applications routinely used within the dendrochronological community have their roots back in the 1980s (e.g. COFECHA and DPL).  While these products are venerable, they still perform well and therefore until improvements or replacements can be made available, dendrochronological workflows must adapt to their limitations.  With this in mind the universal dendrochronological data conversion tool - TRiCYCLE - was developed soon after the release of the tree ring data standard [@brewer2011tricycle].  See section 3.3 for further information.

## 2.4 File Naming Convention

Folder structure and file naming conventions should be decided upon and well documented before work begins.  Documentation should be kept in the base of the folder structure for reference.  For ease of access we strongly recommend a folder structure that follows the TRiDaS data model.  For instance a top level folder for each project, followed by one sub-folder for each 'object' (site), and nested sub-folders to handle  sub-objects if necessary.  Within these folders are folders for elements, samples etc.  The folder structure may be simplified and stopped at sites or trees, but in such cases it is essential to explicitly follow the file naming scheme outlined below.

```{figure} ../images/folders.png
:alt: Figure 2

__Figure 2__: Recommendation for structure of folders when saving dendrochronological data files.  Note the structure follows\\the TRiDaS data model with the top level folder below the root of the repository corresponding to a TRiDaS project.
```

File naming conventions should also follow the TRiDaS data model.  This, however, can be problematic if you need to maintain compatibility with legacy (typically DOS-based) programs that have restrictions on file name length.  DOS programs can only handle file names with 8 characters plus a 3 character file extension.  If 8 character names are required then we recommend:
* 3 alpha character code for object e.g. ABC
* 3 digit code for element e.g. 001
* 1 character code for sample e.g. A
* 1 digit sequential number to distinguish between files

Note that this unfortunately necessarily excludes the concept of a TRiDaS radius.  This would result in a Tucson file being named: ABC001A1.rwl. This naming convention can also serve as a guide for the concept of a 'keycode'.  A number of legacy file formats use the concept of an 8 character 'keycode' for identifying a series.  When using these short file names it is more important to maintain the deep nested folder structure described above.

If backwards compatibility with DOS programs is not required, then the file naming convention should be longer and more explicit.  We recommend delimiting the TRiDaS entities within the file name using the hyphen and to include all levels of the TRiDaS data model.  For example: ABC-1-B-A-1.rwl would refer to the first measurement series, from radius A, of sample B, of element 1 from object ABC.  

We do not support the use of the file extension characters for anything other than identifying the format of the file.  This is a widely understood use for these characters and altering them to compensate for file length limitations can lead to confusion.  File extensions should follow established conventions e.g. .fh for Heidelberg, .rwl for Tucson etc.  If the format does not have a widely agreed upon file extension, then .txt should be used instead.

If deviations are necessary from the naming and structuring proposals outlined above, then it is essential that detailed documentation be made and stored with the data files.  These conventions must be adhered to, to ensure that those that follow can understand exactly what each data file refers to.

## 2.5 Documenting Data Creation and Processing

TRiDaS contains the capability to describe all aspects of the creation and processing of digital dendrochronological information.  The software and methods used to index and cross-date dendrochronological data sets can and should be included wherever possible.  The support for such extensive use of TRiDaS in software is currently very limited. 