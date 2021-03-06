
# Data citation guidelines to JATS mapping **\[DRAFT\]**

- [Data citation guidelines to JATS mapping **\[DRAFT\]**](#data-citation-guidelines-to-jats-mapping-draft)
    - [Introduction.](#introduction)
    - [Layout of this document.](#layout-of-this-document)
    - [JATS Citation tagging with a `publication-type="data"` attribute.](#jats-citation-tagging-with-a-publication-typedata-attribute)
        - [Examples](#examples)
    - [JATS cross references, and external references with `specific-use="data"`](#jats-cross-references-and-external-references-with-specific-usedata)
        - [Examples](#examples)
    - [Data citation elements - decision criteria.](#data-citation-elements---decision-criteria)
    - [1. Author/Rightsholder/ Creator/Primary Responsibility](#1-authorrightsholder-creatorprimary-responsibility)
        - [Existing JATS Equivalents](#existing-jats-equivalents)
            - [`<name>`](#name)
            - [person-group/name](#person-groupname)
            - [person-group/collab](#person-groupcollab)
            - [`<institution>`](#institution)
            - [`<institution-wrap>`](#institution-wrap)
        - [JATS modification suggested](#jats-modification-suggested)
            - [person-group/collab](#person-groupcollab)
    - [2. Publication/Release Date /Year](#2-publicationrelease-date-year)
        - [Existing JATS Equivalents](#existing-jats-equivalents)
            - [`<date>`](#date)
            - [`<year>`](#year)
    - [3. Title/Name of the Dataset](#3-titlename-of-the-dataset)
        - [Existing JATS Equivalents](#existing-jats-equivalents)
            - [`<source>`](#source)
        - [JATS modification suggested](#jats-modification-suggested)
            - [`<data-title>`](#data-title)
    - [4. Version/Edition](#4-versionedition)
        - [Existing JATS Equivalents](#existing-jats-equivalents)
            - [`<edition>`](#edition)
        - [JATS modification suggested](#jats-modification-suggested)
            - [`<version>`](#version)
    - [5. Resource Type](#5-resource-type)
        - [Existing JATS Equivalents](#existing-jats-equivalents)
            - [`@publication-format/@publication-type`](#publication-formatpublication-type)
    - [6. Persistent Global Identifier/ Locator (DOI/URL)](#6-persistent-global-identifier-locator-doiurl)
        - [Existing JATS Equivalents](#existing-jats-equivalents)
            - [`<pub-id>` with `@pub-id-type`](#pub-id-with-pub-id-type)
            - [`<ext-link>` with `@ext-link-type`](#ext-link-with-ext-link-type)
            - [`<uri>`](#uri)
        - [JATS modification suggested](#jats-modification-suggested)
            - [`pub-id` with `xlink` attribute](#pub-id-with-xlink-attribute)
    - [7. Publisher/Distributor/ Repository/ Data Center /Archive](#7-publisherdistributor-repository-data-center-archive)
        - [Existing JATS Equivalents](#existing-jats-equivalents)
            - [`<publisher-name>`](#publisher-name)
    - [8. Location of publisher/distributor](#8-location-of-publisherdistributor)
        - [Existing JATS Equivalents](#existing-jats-equivalents)
            - [`<publisher-loc>`](#publisher-loc)
    - [9. Access Date(s) and Time](#9-access-dates-and-time)
        - [Existing JATS Equivalents](#existing-jats-equivalents)
            - [`<date-in-citation>`](#date-in-citation)
    - [10. Additional URI/Location /bridge service](#10-additional-urilocation-bridge-service)
        - [Existing JATS Equivalents](#existing-jats-equivalents)
            - [`<ext-link>` with `@ext-link-type`](#ext-link-with-ext-link-type)
            - [`<uri>`](#uri)
    - [11. Secondary distributor/ other Institutional Role](#11-secondary-distributor-other-institutional-role)
        - [Existing JATS Equivalents](#existing-jats-equivalents)

## Introduction.
This document provides a guideline on how to use the [Journal Article Tag Suite](http://jats.nlm.nih.gov/about.html) to tag data citations. These are an
are an evolving set of guidelines that have been developed sa part of the NISO-JATS Data Citation Implementation Workshop held at the British Library on
the 19<sup>th</sup> of June 2014. This document is aimed at describing how to tag data citations within the XML. These guidelines do not concern themselves
with where data citations should be placed within the article, nor how they should be presented to the reader, but rather attempts to provide
JATS tagging guidelines that can improve the tagging irrespective of those concerns.


## Layout of this document.

We propose some general guidelines on how to tag when a cross reference or citation is pointing at data.
We then describe the fields that cover most of the use cases for data citation, in addition to our criteria for determining those fields. We then describe our
proposed approach to mapping these fields into JATS. We then describe, field by field, alternatives within JATS named and tagged. We describe
a mapping for each field to existing alternatives within JATS where such alternatives exists. For some fields we offer recommendations for modifications to
JATS that could make implementing data citation easier, and we clearly delineate between existing and proposed options.

---

## JATS Citation tagging with a `publication-type="data"` attribute.

In JATS references are tagged as `<mixed-citation>` or `<element-citation>`. These tags can carry the attribute `publication-type`. We make the
simple recommendation that for data citations the attribute be set to `data`.  

### Examples
	<mixed-citation publication-type="data">
		...
	</mixed-citation>

	<element-citation publication-type="data">
		...
	</element-citation>

---

## JATS cross references, and external references with `specific-use="data"`

Cross references and external references are supported via use of `<x-ref>`, `<pub-id>` and `<ext-link>` respectively. We make the recommendation that these take
the `specific-use="data"` attribute where possible, and where this will not conflict with an existing instance of `specific-use`.  

### Examples
	<pub-id specific-use=“data”>
	<ext-link specific-use=“data”>
	<x-ref specific-use=“data”>


---

## Data citation elements - decision criteria.

The workshop settled on a set of fields to map based on a an analysis of published recommendations from a large variety of sources on best practice for data citation.
By identifying the most commonly used fields across all of these recommendations we hope that the mapping guidelines provided in this document can cover
a significant number of use cases for data citation, however we do not anticipate that these guidelines will cover all use cases (though we would be delighted if that
	turns out to be the case). The working document that summarises that work can be found at .... The fields that were identified are:

1. Author/Rightsholder/ Creator/Primary Responsibility  
2. Publication/Release Date /Year  
3. Title/Name of the Dataset  
4. Version/Edition  
5. Resource Type  
6. Persistent Global Identifier/ Locator (DOI/URL)  
7. Publisher/Distributor/ Repository/ Data Center /Archive  
8. Location of publisher/distributor  
9. Access Date(s) and Time  
10. Additional URI/Location /bridge service  
11. Secondary distributor/ other Institutional Role  

---

## 1. Author/Rightsholder/ Creator/Primary Responsibility
Data creators. People or organizations responsible for developing (intellectual work) the dataset (_type subproperty_) _Primary Responsibility_

### Existing JATS Equivalents  
#### `<name>`
	<name> <surname>Edelstein</surname> <given-names>PH</given-names> </name>

#### person-group/name  
	<person-group person-group-type=”author”>
	<name> <surname>Edelstein</surname> <given-names>PH</given-names> </name>
	</person-group>

#### person-group/collab  
	<person-group person-group-type=”author”>
	</person-group>  

#### `<institution>`
	<institution>The World Health Organization</institution>  

#### `<institution-wrap>`
	<institution-wrap>
	<institution-id institution-id-type="Ringgold">1812</institution-id>
	<institution content-type="university">
	Harvard University</institution>
	</institution-wrap>

### JATS modification suggested

#### person-group/collab  
	<collab collab-type="curators">The BAC Resource Consortium</collab> 

We propose`collab-type` be extended to include `curators`

----

## 2. Publication/Release Date /Year  
When this version of the dataset was made available for citation. May be only a year

### Existing JATS Equivalents  
#### `<date>`  
	<date iso-8601-date=”2014-07”>
	<month>July</month><year>2014</year>
	</date>

#### `<year>`  
	<year iso-8601-date=”2014-07”>2014</year>

----

## 3. Title/Name of the Dataset
Formal title  of the dataset (may include applicable dates) (optional type subproperty). Some sources place this inside the name.

### Existing JATS Equivalents  
#### `<source>`
	<source>Monitoring the Future: A Continuing Study of American Youth (12th Grade Survey)</source>  

### JATS modification suggested
#### `<data-title>`
	<data-title>Monitoring the Future: A Continuing Study of American Youth (12th Grade Survey)</data-title>

We suggest that this reference element be added to at least `mixed-citation`, `element-citation` and `related-object`.

----

## 4. Version/Edition
The precise version number of the data used.

### Existing JATS Equivalents  
#### `<edition>`  
	<edition>2014- Third</edition>


### JATS modification suggested
#### `<version>`
	<version>16.2.1</version>

If edition and version are considered to be different, a new element would need to be added to JATS.

----

## 5. Resource Type  
Material designator; medium; (general type description subpropery).  
### Existing JATS Equivalents  
#### `@publication-format/@publication-type`
The only way current JATS has to record this is `@publication-format/@publication-type`
	<mixed-citation publication-type=”dataset”   publication-format=”online”>...

----

## 6. Persistent Global Identifier/ Locator (DOI/URL)  
Possibly a URL, but ideally a persistent ( DOI, PURL, Handle, or ARK) HTTP form of the DOI is preferred by some sources.

### Existing JATS Equivalents  
#### `<pub-id>` with `@pub-id-type`
	<pub-id pub-id-type="doi">10.1128/JCM.02410-08</pub-id>
	<pub-id pub-id-type="doi">10.1099/ijs.0.039248-0</pub-id>


#### `<ext-link>` with `@ext-link-type`  
	<ext-link-type="uri" xlink:href="http://dx.doi.org/10.6070/H4WM1BBQ">
	http://dx.doi.org/10.6070/H4WM1BBQ</ext-link>

#### `<uri>`  
	<uri xlink:href="http://www.biomedcentral.com/1471-2180/13/198">http://www.biomedcentral.com/1471-2180/13/198</uri>

### JATS modification suggested
#### `pub-id` with `xlink` attribute

Note: At the moment, <pub-id> does not take any linking attributes. We might need to add these to JATS:  
	`<pub-id="doi" xlink:href="http://dx.doi.org/http://dx.doi.org/10.6070/H4WM1BBQ">10.6070/H4WM1BBQ</pub-id>`

----

## 7. Publisher/Distributor/ Repository/ Data Center /Archive

The organization distributing and curating the data (ideally over the long term) such as a Data Center or Archive

### Existing JATS Equivalents

#### `<publisher-name>`
	<publisher-name>Public Library of Science</publisher-name>

----

## 8. Location of publisher/distributor  
Such as city, state, country
### Existing JATS Equivalents  
#### `<publisher-loc>`
	<publisher-loc>San Francisco, USA</publisher-loc>

----

## 9. Access Date(s) and Time
Exactly when the online data was accessed.

### Existing JATS Equivalents  
#### `<date-in-citation>`
	<date-in-citation iso-8601-date=”2014-06-13:10:00”>Accessed on:
	<year>2014</year, <month>June</month>,<day>13</day> at 10:00am</date-in-citation>

----

## 10. Additional URI/Location /bridge service
Typically used for a URL in addition to the regular DOI

### Existing JATS Equivalents  
#### `<ext-link>` with `@ext-link-type`
	<ext-link ext-link-type="uri" xlink:href="http://r-forge.r-project.org/projects/splits">
	http://r-forge.r-project.org/projects/splits</ext-link>

#### `<uri>`
	`<uri xlink:href="http://www.biomedcentral.com/1471-2180/13/198">http://www.biomedcentral.com/1471-2180/13/198</uri>`

----

## 11. Secondary distributor/ other Institutional Role
Typically used for a URL in addition to the regular DOI

### Existing JATS Equivalents  
#### institution with `@content-type` `institution-wrap` (*would need to be added*) 
	*do we need an institution example here?*
