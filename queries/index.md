# Beacon Network Example Queries

Implementation of networks for the Beacon v2 specification is being done based
on a set of standardized queries. In the beginning, those queries will address
limited-but-beyond-v1 scenarios, especially such where many resources are
expected to have some kind of real data.

## TP53 Range Query

TP53 is a classical testing target since it can carry both germline mutations 
(e.g. in Li-Fraumeni syndrome) as well as frequent somatic mutations (SNVs, 
indels and CNVs) in a large fraction of cancer samples. Therefore, a [Beacon
Range Query](http://docs.genomebeacons.org/variant-queries/#beacon-range-queries)
represents a nice real-world test case in which both genomic variation matching
as well as different filter types can be tested.

* [TP53 variant examples](TP53-variant-examples.md)