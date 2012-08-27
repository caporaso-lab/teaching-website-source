=============================
Lecutre 25: Genome assembly
=============================

What is genome sequencing? 
 * The determination of the full order of bases (As, Cs, Gs, and Ts) in an organism's genome.

How do we sequence genomes?
 * Current DNA sequencing technologies generate sequencing reads that are much shorter than the full genomic sequences we're interested in. We therefore must sequence fragments of the genome and ``assemble`` them into the full length sequence of interest.
 * To achieve this, we must sequence in great depth so we observe each base multiple times. During the human genome project, the human genome was sequenced to `8x` coverage, meaning that on average every base was sequenced 8 times. This can help with sequencing error detection and correction, but also provides many overlapping reads which are necessary for assembly.

Why is assembly hard? 
 * `Repeat elements`, or fragments of DNA with identical sequences, can make a genome appear to fit together in multiple different ways. When the same sequence is observed many times, an assmebler (or program that performs genome assembly) will generally tag that sequence as a repeat.
 * Very short reads cause more of a repeat problem than longer reads. As you get shorter, repeats are more likely; as you get longer repeats are less likely. Note that genome sequence is not random though, so the probability of a repeat doesn't just decrease exponentially with increasing read length (i.e., probability of a repeat is not 0.25**read_length). 
 * Good discussion of the problems with assembly from short reads can be found `here <http://www.ncbi.nlm.nih.gov/pubmed/20508146>`_.

How do we assemble genomes:
 * Create `contigs` by identifying overlapping reads segments and merging into contiguous segments.
 * In any complex genome, contigs will be interrupted by repeat regions or regions that do not get sequenced by chance. These can be assembled using `paired end` or `mate pair` reads. This involves sequencing both ends of sequences of known length, so for certain pairs of reads which would be incorporated into contigs, you'd know the length of sequence separating those reads. You can use this information to create `scaffolds`, which are contigs that are interrupted by gaps that represent unknown sequence. 
 * Description of different approaches for genome assembly can be found `here <http://www.ncbi.nlm.nih.gov/pubmed/20211242>`_.

Finished versus draft genomes:
 * Finished genome requires the full sequencing of the entire genome; draft allows small gaps due to missing coverage or segments that cannot be accurately determined due to repeat elements. 
 * Generating the draft is a lot cheaper than generating the finished genome (the former is heavily automated, while the latter is not) so many projects stop at the draft. 



