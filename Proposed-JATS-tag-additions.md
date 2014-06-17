Based on the overview of how [to potentially model data citation in JATS](https://github.com/data-citation-working-group/data-citation-workshop-2014/blob/master/data-citation-to-JATS-mapping-v1.md) a number of tag 
additions/modifications are explicity suggested. 

These are

- addition of a `<version>` element 
- addition of a `<data-format>` element (would '<resource-format>' be a better name?)
- extension of `<pub-id>` to take the `@xlink` attributes
- addition of an '<institution-wrap>' element
 
These new elements to be be added to (at least):
   <mixed-citation>
   <element-citation>
   <related-object>

We might also want to consider:

1) Add data-specific values to the suggested values for 
the attribute @publication-type (which is currently used 
on <mixed-citation> and <element-citation> to record
pub type such as 'book' and 'journal').

2) Add data-specific values (real or suggested) to the 
attribute @pub-id-type (which currently says what kind
of identifier and namnes things like DOI and PUBMED ID).
For example, it should be able to say ARK, Handle,
and other dataset-specific values.

