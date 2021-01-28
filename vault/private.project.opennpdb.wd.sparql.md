---
id: 28099698-432a-4a13-a829-622e50fe5747
title: Sparql
desc: ''
updated: 1600775519524
created: 1600775519524
stub: false
---

## SPAQRL Query examples

``` sql
SELECT 

?classes
?itemLabel 
?inchi 
?inchikey 
?cas 
?chebi 
?chembl 
?pubchem 
?taxon 
?taxonLabel 
?parentTaxon 
?parentTaxonLabel 
?parentTaxon2
?parentTaxon2Label 

WHERE {
  VALUES ?classes {
    wd:Q11173 # chemical compound
  }
  ?item wdt:P31 ?classes ; # instance of
            wdt:P234 ?inchi ;
            wdt:P235 ?inchikey ;
            wdt:P231 ?cas ;
            wdt:P683 ?chebi ;
            wdt:P592 ?chembl ;
            wdt:P662 ?pubchem.
  
  ?taxon wdt:P225 'Arabidopsis thaliana';
         wdt:P171 ?parentTaxon.
         
  ?parentTaxon2 wdt:P171 ?parentTaxon.
  
  {
    ?item p:P1582 ?stmt. # natural product of taxon
    ?stmt ps:P1582 ?taxon. # natural product of taxon
    OPTIONAL {
      ?stmt prov:wasDerivedFrom ?ref. 
      ?ref pr:P248 ?art. # stated in
    }
  }
  UNION
  {
    ?item p:P703 ?stmt. # found in taxon
    ?stmt ps:P703 ?taxon. # found in taxon
    OPTIONAL {
      ?stmt prov:wasDerivedFrom ?ref.
      ?ref pr:P248 ?art. # stated in
    }
  }
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". }
}
```
