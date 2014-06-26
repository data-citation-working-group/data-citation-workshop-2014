
# Data citation guidelines to JATS mapping **\[DRAFT\]**

@@TOC@@

## Introduction.
This document provides a guideline on how to use the [Journal Article Tag Suite](http://jats.nlm.nih.gov/about.html) to tag data citations. These are an
are an evolving set of guidelines that have been developed sa part of the NISO-JATS Data Citation Implementation Workshop held at the British Library on
the 19<sup>th</sup> of June 2014. This document is aimed at describing how to tag data citations within the XML. These guidelines do not concern themselves
with where data citations should be placed within the article, nor how they should be presented to the reader, but rather attempts to provide
JATS tagging guidelines that can improve the tagging irrespective of those concerns.


## Layout of this document.

We describe the fields that cover most of the use cases for data citation, in addition to our criteria for determining those fields. We then describe our
proposed approach to mapping these fields into JATS. We then describe, field by field, alternatives within JATS named and tagged. We describe
a mapping for each field to existing alternatives within JATS where such alternatives exists. For some fields we offer recommendations for modifications to
JATS that could make implementing data citation easier, and we clearly delineate between existing and proposed options.

---

## Data citation elements - decision criteria.

The workshop settled on a set of fields to map based on a an analysis of published recommendations from a large variety of sources on best practice for data citation.
By identifying the most commonly used fields across all of these recommendations we hope that the mapping guidelines provided in this document can cover
a significant number of use cases for data citation, however we do not anticipate that these guidelines will cover all use cases (though we would be delighted if that
	turns out to be the case). The working document that summarises that work can be found at .... The fields that were identified are:



---

## Fields to JATS Elements Mapping

In the following pages:
- A numbered heading will list the field name (as found in several sources)  
- The paragraph below it will give an approximate definition. (Non-italicized definitions are from [ESIP Data Citation Guidelines](http://commons.esipfed.org/node/308) (Ruth Duerr 20120). Properties and sub-properties are from the [DataCite Schema 2013](http://schema.datacite.org/meta/kernel-3/index.html))  
- The bulleted list following will show JATS alternatives, named and tagged.
- Comments MAY be given at the end.  

----

## 1. Author/Rightsholder/ Creator/Primary Responsibility
Data creators. People or organizations responsible for developing (intellectual work) the dataset (_type subproperty_) _Primary Responsibility_

### Existing JATS Equivalents  
#### name  
	<name> <surname>Edelstein</surname> <given-names>PH</given-names> </name>


#### person-group/name  
	<person-group person-group-type=”author”>
	<name> <surname>Edelstein</surname> <given-names>PH</given-names> </name>
	</person-group>

#### person-group/collab  
	<person-group person-group-type=”author”>
	<collab collab-type=”compilers”>The BAC Resource Consortium</collab> 
	</person-group>  

#### institution  
	<institution>The World Health Organization</institution>  

#### institution-wrap  
	<institution-wrap>
	<institution-id institution-id-type="Ringgold">1812</institution-id>
	<institution content-type="university">
	Harvard University</institution>
	</institution-wrap>

### JATS modification suggested

----

## 2. Publication/Release Date /Year  
When this version of the dataset was made available for citation. May be only a year

### Existing JATS Equivalents  
#### date  
	<date iso-8601-date=”2014-07”>
	<month>July</month><year>2014</year>
	</date>

#### year  
	<year iso-8601-date=”2014-07”>2014</year>

### JATS modification suggested
----

## 3. Title/Name of the Dataset
Formal title  of the dataset (may include applicable dates) (optional type subproperty). Some sources place this inside the name.

### Existing JATS Equivalents  
#### source
	<source>Monitoring the Future: A Continuing Study of American Youth (12th Grade Survey)</source>  

### JATS modification suggested
----

## 4. Version/Edition
The precise version number of the data used.

### Existing JATS Equivalents  
#### edition  
	<edition>2014- Third</edition>

#### version - If edition and version are considered to be different, a new element would need to be added to JATS:
	<version>16.2.1</version>

### JATS modification suggested
----

## 5. Resource Type  
Material designator; medium; (general type description subpropery).  
### Existing JATS Equivalents  
The only way current JATS has to record this is `@publication-format/@publication-type`
	<mixed-citation publication-type=”dataset”   publication-format=”online”>...

If this information should be recorded as an element, a new element would need to be added to JATS, for example one of:

- `<data-format>dataset</data-format>`
- `<data-format>spreadsheet</data-format>`
- `<data-format>data</data-format>`

### JATS modification suggested
----

## 6. Persistent Global Identifier/ Locator (DOI/URL)  
Possibly a URL, but ideally a persistent ( DOI, PURL, Handle, or ARK) HTTP form of the DOI is preferred by some sources.

### Existing JATS Equivalents  
#### `<pub-id>` with `@pub-id-type`
	<pub-id pub-id-type="doi">10.1128/JCM.02410-08</pub-id>
	<pub-id pub-id-type="doi">10.1099/ijs.0.039248-0</pub-id>

Note: At the moment, <pub-id> does not take any linking attributes. We might need to add these to JATS:  
	`<pub-id="doi" xlink:href="http://dx.doi.org/http://dx.doi.org/10.6070/H4WM1BBQ">10.6070/H4WM1BBQ</pub-id>`

#### `<ext-link>` with `@ext-link-type`  
	<ext-link-type="uri" xlink:href="http://dx.doi.org/10.6070/H4WM1BBQ">
	http://dx.doi.org/10.6070/H4WM1BBQ</ext-link>

#### `<uri>`  
	<uri xlink:href="http://www.biomedcentral.com/1471-2180/13/198">http://www.biomedcentral.com/1471-2180/13/198</uri>

### JATS modification suggested
----

## 7. Publisher/Distributor/ Repository/ Data Center /Archive

The organization distributing and curating the data (ideally over the long term) such as a Data Center or Archive

### Existing JATS Equivalents  
#### <publisher-name>
	<publisher-name>Public Library of Science</publisher-name>

### JATS modification suggested
----

## 8. Location of publisher/distributor  
Such as city, state, country
### Existing JATS Equivalents  
#### `<publisher-loc>`
	<publisher-loc>San Francisco, USA</publisher-loc>

### JATS modification suggested
----

## 9. Access Date(s) and Time
Exactly when the online data was accessed.

### Existing JATS Equivalents  
#### `<date-in-citation>`
	<date-in-citation iso-8601-date=”2014-06-13:10:00”>Accessed on:
	<year>2014</year, <month>June</month>,<day>13</day> at 10:00am</date-in-citation>

### JATS modification suggested
----

## 10. Additional URI/Location /bridge service
Typically used for a URL in addition to the regular DOI

### Existing JATS Equivalents  
#### `<ext-link>` with `@ext-link-type`
	<ext-link ext-link-type="uri" xlink:href="http://r-forge.r-project.org/projects/splits">
	http://r-forge.r-project.org/projects/splits</ext-link>

#### `<uri>`
	`<uri xlink:href="http://www.biomedcentral.com/1471-2180/13/198">http://www.biomedcentral.com/1471-2180/13/198</uri>`

### JATS modification suggested
----

## 11. Secondary distributor/ other Institutional Role
Typically used for a URL in addition to the regular DOI

### Existing JATS Equivalents  
#### institution with `@content-type` `institution-wrap` (*would need to be added*) 
	*do we need an institution example here?*

### JATS modification suggested
