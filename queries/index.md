# Beacon Network Example Queries

Implementation of networks for the Beacon v2 specification is being done based
on a set of standardized queries. In the beginning, those queries will address
limited-but-beyond-v1 scenarios, especially such where many resources are
expected to have some kind of real data.

## TP53 Query examples

TP53 is a classical testing target since it can carry both germline mutations 
(e.g. in Li-Fraumeni syndrome) as well as frequent somatic mutations (SNVs, 
indels and CNVs) in a large fraction of cancer samples. Therefore, a [Beacon
Range Query](http://docs.genomebeacons.org/variant-queries/#beacon-range-queries)
represents a nice real-world test case in which both genomic variation matching
as well as different filter types can be tested.

We have selected a number of TP53 variants, both SNVs from ClinVar as well as
CNVs from cell lines:

* some TP53 information and variant examples [with descriptions](TP53-variant-examples.md) and [as `.bed` file](TP53-variant-examples.bed)
* display of the variants from the `.bed` file as [UCSC browser tracks](http://genome-euro.ucsc.edu/cgi-bin/hgTracks?org=human&db=hg38&position=chr17:7668421-7687490&hgt.customText=https://raw.githubusercontent.com/ga4gh-beacon/beacon-v2-networks/main/queries/TP53-variant-examples.bed)


### Any variant overlap with TP53 CDR - Range Query

#### Using `referenceName` with genome specific refseqId

##### GET

```
?referenceName=NC_000017.11&start=7668420&end=7687490
```

##### PUT

```json
{
    "$schema":"https://json-schema.org/draft/2020-12/schema",
    "meta": {
        "apiVersion": "2.0",
        "requestedSchemas": [
            {
                "entityType": "genomicVariation",
                "schema:": "https://raw.githubusercontent.com/ga4gh-beacon/beacon-v2/main/models/json/beacon-v2-default-model/genomicVariations/defaultSchema.json"
            }
        ]
    },
    "query": {
        "requestParameters": {
            "referenceName": "NC_000017.11",
            "start": [7668420],
            "end": [7687490]
        }
    },
    "requestedGranularity": "count"
}
```

#### Using chromosome as `referenceName` and `assemblyId`

```
?assemblyId=GRCh38&referenceName=chr17&start=7668420&end=7687490
```

##### To discuss:

* Should we even support this? It is like v1; but the use of the `referenceName` parameter is
ill-defined in the (e.g. _17_ or _chr17_?)

### More TBD
