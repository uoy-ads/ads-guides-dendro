---
authors:
  - name: null
---

# 3 Archiving dendrochronological data

## 3.1 Deciding What to Archive

In comparison to many of the other data types covered by this good practice guide series, dendrochronological data files are very small and therefore the burden of retention is significantly lower.  It should be noted, however, that researchers are increasingly storing high-resolution scans and photos of wood surfaces which can substantially increase the space required for archiving.  Even with this consideration, it is good practice to archive all verified dendrochronological data and metadata including photos and research reports. For guidance regarding best practice for the creation and archival of image files, see the [Raster Images Guide](https://doi.org/10.5284/mtgj-7130).

What can be archived varies due to the policies of the repository being archived to.  For example the International Tree Ring Data Bank ([ITRDB](https://www.ncei.noaa.gov/products/paleoclimatology/tree-ring)) has strict data-quality control mechanisms resulting in the storage of verified and accurate data sets. The DCCD repository does not implement quality control which implies that the quality of the datasets stored in this repository is unverified and the responsibility of the author(s) of the data.

## 3.2 Deciding How to Archive

Dendrochronological data should be made publicly available wherever possible in order to enable follow-up research and to assist cultural-heritage management.  Many data sets are needed to build the chronologies necessary to date archaeological and historical structures, which means that the entire dendrochronological community benefits from the open sharing of data. In addition the ancient world was very interconnected, and often researchers will need the assistance of dendrochronologists working in other regions to accurately date wood samples. Hence it is only by collaboration and effective data sharing that we will get the most from dendrochronology.

There are currently two internationally recognised repositories for tree ring data: the International Tree Ring Data Bank [(ITRDB)](https://www.ncdc.noaa.gov/data-access/paleoclimatology-data/datasets/tree-ring); and the Digital Collaboratory for Cultural Dendrochronology [(DCCD)](http://dendro.dans.knaw.nl/).

The ITRDB is hosted by the National Oceanic and Atmospheric Administration (NOAA) in the USA and is primarily aimed at dendrochronological data for climate research although it does also contain archaeologically-sourced dendrochronological data.  The repository was set up following an international workshop in 1974 and is structured around the widely used Tucson decadal data format.  The ITRDB integrates with a number of other palaeo-climate proxy databases therefore the metadata it stores is rather minimal and generic.  The ITRDB does support the submission of additional data files so TRiDaS data should be submitted where possible.

The DCCD is a newer repository launched in 2012 hosted and maintained by Data Archiving and Networked Services [(DANS)](http://www.dans.knaw.nl) in the Netherlands.  The repository is based on TRiDaS and is primarily aimed at dendrochronological data associated with cultural research including archaeology, architecture, art, etc.  While DCCD users are encouraged to make their data publicly available, the repository has the facilities to enable the data provider to control access permissions.  This repository is therefore a good choice for users who do not wish - or are unable to make - their data publicly available yet and who meanwhile want to ensure their data is securely managed and maintained in a recognised repository. This procedure ensures that data that is orphaned by the death of researchers or the closure of departments or companies is not lost.

In some circumstance, perhaps for regulatory reasons, data needs to be stored in other designated generic repositories.  It should be noted that in such cases the usefulness of the data for follow-up research will likely be limited.  Generic repositories are more suited to allow the re-examination or verification of specific dendrochronological analyses, rather than the reanalysis of data in new ways (e.g. regional, national or international syntheses). Even when required to archive data into other designated archives, it is also recommended to submit data to one of the specialist dendrochronological archives described above.  If given the option of choosing a generic repository, care should be taken to ensure it is backed by the international EU 'Data Seal of Approval' or a similar authority, which indicates the archive is structured and managed according to current best practices. Any dendrochronological data archived in generic repositories should be stored in TRiDaS format files.

## 3.3 Archiving File Types

As mentioned in section 2.3, there are a great many data formats in use within the dendrochronological community.  However, with the exception of the Tree Ring Data Standard, none provide the mechanism for recording rich standardised metadata.  Wherever possible we strongly recommend using TRiDaS format files to store both your data and metadata.  

If the tools being used for the dendrochronological analyses do not support TRiDaS, then one option is to maintain your data within the legacy format supported by the software, and the metadata in a TRiDaS-enabled database like [TRiDaBASE](http://www.tridas.org/tridabase/) [@jansma2012tridabase].  The DCCD repository supports the submission of TRiDaS plus a variety of legacy formats, whereas the ITRDB supports the submission of Tucson and TRiDaS files.  

The managing of the legacy data files in a hybrid TRiDaS/legacy system is definitely the weakest link in this approach.  With no software to provide error checking, it is all too easy to mislabel, rename, move and delete files - especially in a multi-user environment.  The utmost care must be taken at all times to be as strict as possible.  Write access to the files should be limited to only essential personnel.  Folders containing site data files should be made read-only as soon as work on a site has been completed.

If one decides to follow this method it is important to ensure that the legacy data format that is used stores the ring-width data in an unambiguous manner.  Where ambiguities exist, these should be clarified in the TRiDaS metadata.  A list of formats, along with some of the potential issues they may have, is available in table 2. Further details are available in Brewer *et al.* [-@brewer2011tricycle].

One issue shared by many of the legacy data formats is the ambiguity of the calendar used for dates.  To reduce the programming complexity, many formats use what is known as the astronomical rather than the Gregorian calendar.  The astronomical calendar includes a year zero and denotes BC dates as negative integers. This means that prior to the AD/BC transition the year numbers are offset by one (e.g. 1AD = 1; 1BC = 0; 2BC=-1; etc.).  This can cause complications for researchers both outside and within the dendrochronological community.  It is not uncommon to find legacy data files with BC data where the offset has been removed.

```{list-table} Table 2: Legacy files formats: assessment of their suitability for storing dendrochronological data in combination with a companion TRiDaS file containing metadata.
:header-rows: 1
* - Format
  - Suitable for TRiDaS co-archival
  - Potential issues
* - Belfast Apple
  - With caveats
  - Format cannot store missing ring information
* - Belfast Archive
  - With caveats
  - Format cannot store missing ring information
* - Besancon
  - With caveats
  - The format should strictly only contain data values are in 1/100th mm, however, some users store micron resolution data instead. There is no standard way to discern the difference
* - CATRAS
  - No
  - Closed source proprietary binary format. There is some support for reading/writing CATRAS files in the TRiCYCLE library but the closed nature of the format means this is not comprehensive
* - Cracow Binary format
  - No
  - Simple binary format storing just ring-widths and sapwood markers. Although this is a very simple format, the fact it is binary means accessing the data is not trivial
* - Corina
  - No
  - File format with very limited software support
* - DendroDB
  - No
  - An export format used by the discontinued DendroDB database. No known software implementations generate this format.
* - FHX2
  - No
  - Dendro format for recording fire history event data. Does not support ring-width data
* - Generic spreadsheet formats
  - No
  - Various spreadsheet-style formats (including CSV, MS Excel, ODF etc) are used by some to store and transfer ring-width data.  The flexible nature of spreadsheets means that data can be stored in a wide variety of ways makes it unsuitable for long term storage of data.
* - Heidelberg
  - Yes
  - Native format for the widely used TSAP software.  Has extensive support for metadata fields, but the contents of these fields are not standardised
* - KINSYS-KS
  - With caveats
  - Format specific to the software of the same name produced by the Finnish Forest Research Institute although not widely used elsewhere.  Stores ring-width data effectively but the lack of support in software means it is not ideal for long term storage
* - Nottingham
  - No
  - A format with no known documentation or extant reference implementation
* - Oxford
  - With caveats
  - Does not store data: prior to 1AD; ring-widths >=1mm 
* - PAST4
  - No
  - Files can be in either astronomical or Gregorian calendar which can introduce ambiguities.  
* - Sheffield
  - With caveats
  - Format cannot store missing ring information
* - SYLPHE
  -   
  - (see Bescancon)
* - Topham
  - With caveats
  - Very simplistic format which should only be used for raw ring-width data
* - TRIMS
  - With caveats
  - Format cannot store missing ring information
* - Tucson
  - With caveats
  - There are many undocumented alterations to this format.  Check files with TRiCYCLE or COFECHA to ensure readability before archiving
* - Tucson compact
  - No
  - Rather complicated format that is not widely supported
* - VFormat
  - No
  - Highly encoded metadata makes this format not very accessible
* - WinDENDRO
  - No
  - Proprietary delimited text format
```

## 3.4 Converting Data Formats

All the formats listed in table 2 are supported in the universal dendrochronological data conversion tool [TRiCYCLE](http://www.tridas.org/tricycle/) [@brewer2011tricycle].  TRiCYCLE is an open source, cross-platform tool available as a desktop application and also as a library for use within other programs.  

TRiCYCLE makes use of TRiDaS as an intermediary in the conversion of data and metadata to/from the 24 data formats identified within the dendrochronological community.  TRiCYCLE includes a reader for each supported format that translates the data and metadata into TRiDaS, as well as a writer for each format to translate from TRiDaS to the legacy formats.  This architecture means that data and metadata can be converted back and forth between any combination of formats.  It should, however, be noted that depending on the formats used the process can be 'lossy' in that a round trip conversion may not result in an identical file.  The ambiguous nature of many of the formats (e.g. lack of measurement units) means that TRiCYCLE is forced to make assumptions, which although clearly presented to the user, may result in some degradation of information.  Users must therefore take time to understand the limitations of each format.

## 3.5 Archiving Strategies

The TRiDaS community is committed to maintaining this dendrochronological standard, including adding support for new features as deemed necessary.  The standard will, however, remain both backwards and forwards compatible ensuring easy access to existing TRiDaS data for years to come.  It should therefore not be necessary to periodically refresh or migrate data to newer versions of the standard.  

## 3.6 Metadata and Documentation

Rich, standardised metadata is essential to ensure archived data can be effectively reused.  The Tree-Ring Data Standard provides a robust data model around which this metadata can be stored.  A full description of the TRiDaS data model along with all the fields that it supports, can be found in the original publication by Jansma et al [-@jansma2010tridas].  

While the more metadata the better, there may not be the time and resources to comprehensively store all metadata.  This is often especially true when attempting to retrospectively archive existing collections where the metadata is not easily accessible or perhaps completely missing.  

To be as accommodating as possible few of the many data fields defined in TRiDaS are marked as mandatory.  However, there are a number of optional fields that are considered extremely desirable when archiving dendroarchaeological data.  A list of all mandatory and strongly recommend fields are provided in table 3.


```{list-table} Table 3: Metadata fields that are mandatory or strongly recommended when archiving dendrochronological data.
:header-rows: 1
* - Field
  - Mandatory
  - Definition
* - project.title
  - Yes
  - Name of the project
* - project.identifier
  - Yes
  - Laboratory project identification such as a report number
* - project.type
  - Yes
  - Examples include: dating; provenance; wood technology, vegetation reconstruction; climate study
* - project.laboratory
  - Yes
  - Name of the dendrochronological research laboratory
* - project.category
  - Yes
  - One of: former vegetation; archaeology; building history; ship's archaeology; art/furniture; actual vegetation
* - project.investigator
  - Yes
  - Name of the principal investigator
* - project.period
  - Yes
  - When the dendrochronological project took place
* - object.title
  - Yes
  - Name of the object being analysed e.g. the name of a ship, archaeological site, building or painting.
* - object.type
  - Yes
  - Functional description: building (church, house etc.) water well, painting, musical instrument (and type), ship (and type), forest 
* - object.latitude
  - No
  - Latitude of the object in WGS84 decimal degrees
* - object.longitude
  - No
  - Longitude of the object in WGS84 decimal degrees
* - element.title
  - Yes
  - Name of the element
* - element.taxon
  - Yes
  - The most detailed taxonomic name known: species, genus, family etc, preferably from the Catalogue of Life
* - element.latitude
  - No
  - Latitude of the element in WGS84 decimal degrees
* - element.longitude
  - No
  - Longitude of the element in WGS84 decimal degrees
* - sample.title
  - Yes
  - Name of the sample
* - sample.type
  - Yes
  - Method that was used to take a sample from the element e.g. core, section.
* - sample.samplingdate
  - No
  - Date the sample was taken
* - radius.title
  - Yes
  - Name of the radius
* - radius.pith
  - Yes
  - Whether the pith is present or absent
* - radius.sapwood
  - Yes
  - One of: n/a; absent; complete or incomplete
* - radius.bark
  - Yes
  - Whether the bark is present or absent
* - measurementSeries. title
  - Yes
  - Name of the measurement series
* - measurementSeries.measuringmethod
  - Yes
  - What method was used to measure the sample
* - measurementSeries. variable
  - Yes
  - Measured variable e.g. ring-width, earlywood, latewood etc
* - derivedSeries.type
  - Yes
  - If the series has been derived from other series, what type of series is it e.g. chronology, object curve etc 
```

Although the TRiDaS data model (i.e. the structure and data fields) is typically implemented as XML files that comply to the TRiDaS XML schema, it can also be followed in other less formal ways.  For instance the Heidelberg data format enables users to store user-defined metadata fields so it is possible to use the TRiDaS fields definitions as additional user-defined fields within a Heidelberg file.  If you are using the TRiDaS data model in such a manner, take time to get to know the structure of the model along with its deliberately introduced formatting restrictions.  For example, TRiDaS extends the Geography Markup Language (GML) for storing location information.  If you are storing coordinates, take care to format them in a logical and consistent manner and to record associated information such as the datum.  TRiDaS also defines a number of dictionaries for common terms.  These dictionaries should be followed wherever possible.