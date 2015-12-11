======================================================================
Lecture 21: OTU picking and microbial ecology (continued)
======================================================================

De novo OTU picking: reads are clustered based on similarity to one another.
 * Pros: All reads are clustered
 * Cons: Not easily parallelizable; OTUs may be defined by erroneous reads.

Closed-reference OTU picking: reads are clustered based on similarity to sequences in a reference database; reads that don't match something in the database are discarded.
 * Pros: Built-in quality filter; easily parallelizable; OTUs are defined by high-quality, trusted sequences
 * Cons: Reads that don’t hit reference dataset are excluded, so you can never observe new OTUs

Open-reference OTU picking: reads are clustered based on similarity to sequences in a reference database; reads that don't match something in the database are then clustered de novo and the resulting sets of OTUs are merged.

 * Pros: All reads are clustered; partially parallelizable
 * Cons: Only partially parallelizable; mix of high quality sequences defining OTUs (i.e., the database sequences) and possible low quality sequences defining OTUs (i.e., the sequencing reads)


