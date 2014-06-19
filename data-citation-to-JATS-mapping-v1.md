# Mapping Data Citing Fields to JATS Elements  V1 2014-06-13

The document makes a start at answering the question of how parts of dataset citations  (as identified in the spreadsheet) might be tagged using JATS. 
A basic assumption is that all these elements will be placed inside the `<mixed-citation>` element, which will also include punctuation and other information, not recorded in these elements. There is rarely one way to tag something, of course, as JATS is permissive rather than enforcing.
As a reminder, here is a full example of a JATS-tagged citation for a journal article (XML courtesy of Jo McEntyre, as are most of the rest of the examples).


	<ref id="B45">
	<mixed-citation publication-type="journal">
	<name><surname>Kozak</surname>
	<given-names>NA</given-names>
	</name>
	<name><surname>Benson</surname>
	<given-names>RF</given-names>
	</name>
	<name><surname>Brown</surname>
	<given-names>E</given-names>
	</name>
	<name><surname>Alexander</surname>
	<given-names>NT</given-names>
	</name>
	<name><surname>Taylor</surname>
	<given-names>TH</given-names>
	</name>
	<name>
	<surname>Shelton</surname>
	<given-names>BG</given-names>
	</name>
	<name>
	<surname>Fields</surname>
	<given-names>BS</given-names>
	</name>
	<article-title>Distribution of lag-1 alleles and sequence-based types among Legionella
	pneumophila serogroup 1 clinical and environmental isolates in the United States</article-title>
	<source>J Clin Microbiol</source>
	<year>2009</year>
	<volume>13</volume>
	<fpage>2525</fpage>
	<lpage>2535</lpage>
	<pub-id pub-id-type="doi">10.1128/JCM.02410-08</pub-id>
	<pub-id pub-id-type="pmid">19553574</pub-id>
	</mixed-citation>
	</ref>

----

## Fields to JATS Elements Mapping

In the following pages: 
- A numbered heading will list the field name (as found in several sources)  
- The paragraph below it will give an approximate definition. (Non-italicized definitions are from [ESIP Data Citation Guidelines](http://commons.esipfed.org/node/308) (Ruth Duerr 20120). Properties and sub-properties are from the [DataCite Schema 2013](http://schema.datacite.org/meta/kernel-3/index.html))  
- The bulleted list following will show JATS alternatives, named and tagged.   
- Comments MAY be given at the end.  

----

### Author/Rightsholder/ Creator/Primary Responsibility
Data creators. People or organizations responsible for developing (intellectual work) the dataset (_type subproperty_) _Primary Responsibility_

### Potential JATS Equivalents  
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

----

### Publication/Release Date /Year  
When this version of the dataset was made available for citation. May be only a year

#### date  
	<date iso-8601-date=”2014-07”>
	<month>July</month><year>2014</year>
	</date>

#### year  
	<year iso-8601-date=”2014-07”>2014</year>

----

### Title/Name of the Dataset
Formal title  of the dataset (may include applicable dates) (optional type subproperty). Some sources place this inside the name.

#### source
	<source>Monitoring the Future: A Continuing Study of American Youth (12th Grade Survey)</source>  

----

### Version/Edition
The precise version number of the data used.

#### edition  
	<edition>2014- Third</edition>

#### version - If edition and version are considered to be different, a new element would need to be added to JATS:
	<version>16.2.1</version>

----

### Resource Type  
Material designator; medium; (general type description subpropery).  
The only way current JATS has to record this is `@publication-format/@publication-type`
	<mixed-citation publication-type=”dataset”    publication-format=”online”>...

If this information should be recorded as an element, a new element would need to be added to JATS, for example one of:

- `<data-format>dataset</data-format>`
- `<data-format>spreadsheet</data-format>`
- `<data-format>data</data-format>`

----

### Persistent Global Identifier/ Locator (DOI/URL)  
Possibly a URL, but ideally a persistent ( DOI, PURL, Handle, or ARK) HTTP form of the DOI is preferred by some sources.

#### `<pub-id>` with `@pub-id-type`
	<pub-id pub-id-type="doi">10.1128/JCM.02410-08</pub-id>
	<pub-id pub-id-type="doi">10.1099/ijs.0.039248-0</pub-id>

Note: At the moment, <pub-id> does not take any linking attributes. We might need to add these to JATS:  
	`<pub-id="doi" xlink:href="http://dx.doi.org/http://dx.doi.org/10.6070/H4WM1BBQ">10.6070/H4WM1BBQ</pub-id>`

#### `<ext-link>` with `@ext-link-type`  
	<ext-link-type="uri" xlink:href="http://dx.doi.org/http://dx.doi.org/10.6070/H4WM1BBQ">
	http://dx.doi.org/http://dx.doi.org/10.6070/H4WM1BBQ</ext-link>

#### `<uri>`  
	<uri xlink:href="http://www.biomedcentral.com/1471-2180/13/198">http://www.biomedcentral.com/1471-2180/13/198</uri>

----

### Publisher/Distributor/ Repository/ Data Center /Archive

The organization distributing and curating the data (ideally over the long term) such as a Data Center or Archive

#### <publisher-name>
	<publisher-name>Public Library of Science</publisher-name>

----

### Location of publisher/distributor  
Such as city, state, country
#### `<publisher-loc>`
	<publisher-loc>San Francisco, USA</publisher-loc>

----

### Access Date(s) and Time 
Exactly when the online data was accessed.

#### `<date-in-citation>`
	<date-in-citation iso-8601-date=”2014-06-13:10:00”>Accessed on:
	<year>2014</year, <month>June</month>,<day>13</day> at 10:00am</date-in-citation>

----

### Additional URI/Location /bridge service
Typically used for a URL in addition to the regular DOI

#### `<ext-link>` with `@ext-link-type`
	<ext-link ext-link-type="uri" xlink:href="http://r-forge.r-project.org/projects/splits">
	http://r-forge.r-project.org/projects/splits</ext-link>

#### `<uri>`
	`<uri xlink:href="http://www.biomedcentral.com/1471-2180/13/198">http://www.biomedcentral.com/1471-2180/13/198</uri>`
 
----
 
### Secondary distributor/ other Institutional Role
Typically used for a URL in addition to the regular DOI

#### institution with `@content-type` `institution-wrap` (*would need to be added*) 
	*do we need an institution example here?*
