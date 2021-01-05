==================================================
Lecture 5: DNA to Protein; part 2: mRNA to Protein
==================================================

`RNAs can form complex structures <http://www.nature.com/scitable/topicpage/chemical-structure-of-rna-348>`_ based primarily on base pairing interactions between bases within the single stranded molecule.

Adapter molecules are required which bind the codon and the coded amino acid - these are the `transfer RNAs (tRNAs) <http://www.nature.com/scitable/definition/trna-transfer-rna-256>`_. 

`Proteins are synthesized <http://www.nature.com/scitable/topicpage/the-information-in-dna-determines-cellular-function-6523228>`_ from their N-terminal end to their C-terminal end by the ribosome. The anticodon of an activated tRNA molecule (i.e., a tRNA molecule with an attached amino acid) base pairs with the corresponding codon in an mRNA molecule inside of a ribosome. 

`Ribozymes` are RNA molecules capable of catalyzing reactions. The ribosome is composed primarily of functional RNA molecules (the rRNAs), and is therefore a ribozyme. The functional activities of the ribosome (binding mRNA and tRNA, and catalyzing peptide bond formation) are all performed by the rRNAs. Proteins appear to have less critical roles such as stabilizing the RNA core of the ribosome.

The topics presented here are covered in more detail in Molecular Biology of the Cell, available from the NIH Bookshelf `here <http://www.ncbi.nlm.nih.gov/books/NBK26887/>`_.


Coding discussion
-----------------

Using boolean logic to generalize our reverse complement script
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The homework for tonight starts with boolean logic: primarily understanding and evaluating boolean expressions. Logic in your programs is about determining if a statement (possibly composed of simpler statements) evaluates to       ``True`` or ``False``. This framework is at the base of programming, and allows you to incorporate logic into your code, which in turn lets you increase the complexity of what your scripts can do. 

One type of comparison that you can do is a string comparison, where you test the equality of two strings. For example, try these::

    "A" == "A"
    "A" == "B"
    "A" != "B"

The `operators` used here are equal (``==``) and not equal (``!=``). Comparisons with these operators always return a boolean value: either ``True`` or ``False``. 

Let's jump in by making use of string comparisons to generalize our reverse complement script to perform some additional functions.

Last time we wrote the following script which allowed us to reverse complement a sequence::

    from sys import argv
    script_name, sequence, sequence_name, output_fasta_fp = argv
    
    output_file = open(output_fasta_fp,'w')
    output_file.write('>%s' % sequence_name)
    output_file.write('\n')
    output_file.write(sequence.replace('A','t').replace('T','a').replace('G','c').replace('C','g').upper()[::-1])
    output_file.write('\n')
    output_file.close()

.. _sequence-processing-script:

Let's add the ``reverse_complement`` and ``transcribe`` functions that we added last time, and then add a flag to this script that allows the user to either reverse complement or transcribe a sequence using the same script::

    from sys import argv
    script_name, sequence, sequence_name, output_fasta_fp, function = argv

    def reverse_complement(sequence):
        return sequence.replace('A','t').replace('T','a').replace('G','c').replace('C','g').upper()[::-1]

    def transcribe(sequence):
        return sequence.replace('T','U')

    if function == "r":
        output_sequence = reverse_complement(sequence)
    elif function == "t":
        output_sequence = transcribe(sequence)
    else:
        print """Unknown function: '%s'. Acceptable functions are 'r' (reverse complement) and 't' (transcribe).""" % function

    output_file = open(output_fasta_fp,'w')
    output_file.write('>%s' % sequence_name)
    output_file.write('\n')
    output_file.write(output_sequence)
    output_file.write('\n')
    output_file.close()


.. warning:: **The reverse complement function that we implemented here is incomplete and dangerous.** The reason for this is that it doesn't do anything with characters other than ``A``, ``C``, ``G``, and ``T``. See the note in the `Lecture 4 outline <./lecture4.html>`_ for more of a discussion of this point.



