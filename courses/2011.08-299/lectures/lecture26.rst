===========================================
Lecture 26: Genome assembly and annotation
===========================================

Redundant coverage in genome sequencing (in an ``Nx`` coverage genome sequencing project, each nucleotide is sequenced ``N`` times on average). 

Deeper coverage helps with:
 * Error detection/correction: probability of an erroneous base when you have (say) eight overlapping calls of that base is very low.
 * Sequencing polymorphic alleles in diploid or polyploid genomes.

Deeper coverage can't help with resolving repeats that are longer than the read length. Paired reads can help with this.

Genome annotation: the process of identifying genes and other functional regions, and ideally assigning function to those regions. This is related to the process of ORF calling (see my lecture slides).

Minimum genome sizes: 
 * Mycoplasma (a non-free-living bacterium) with around 500 genes. Through systematic mutatgenesis, estimated that 250-300 are necessary for a viable cell.
 * Bacillus subtilis has around 4100 genes, and similar results were found (around 270 genes were essential) but only when growing in a very rich media.  
 * Most essential genes are typically present in bacteria, and ~70% are also present in archaea and eukaryotes. 



A recent comparison of genome assembly tools was performed as `Assemblathon 1.0 <http://www.ncbi.nlm.nih.gov/pubmed?term=assemblathon>`_. This was a shared evaluation project, where different tools were compared on their ability to assemble the same data. In this study the authors simulated a genome using `Evolver <http://www.drive5.com/evolver/>`_.

To check out some existing genomes and associated metadata and annotations, follow these steps:

 * Go to the `Integrated Microbial Genomes (IMG site) <http://img.jgi.doe.gov/>`_. 
 * Click ``IMG``
 * Click ``Find Genomes``
 * Choose a genome and click it's name
 * Click ``Browse Genome``
 * Click ``Download Gene Information``
 
 
N50 value: a metric of the quality of assembly: 50% of the reads are contained in contigs of length N or greater
