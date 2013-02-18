==========================================================================================
Homework assignments
==========================================================================================

.. important:: I encourage you to discuss homework assignments with each other, but you may not view other student's assignments or share your assignment with others. When you start programming, you often think there is a single way to address a task, but that is usually not the case: there are many ways to complete these assignments, and when code has been shared or copied it is often very obvious to a more experienced eye.

Turning in your homework by email
---------------------------------
Your homework must always be turned in with a standardized name. That name should be ``<nau_id>_<homework_id>.<extension>``, where ``<nau_id>`` is your NAU identifier (for example, mine is ``jgc53``), and ``<homework_id>`` and ``<extension>`` are provided on a per-assignment basis. 

Unless otherwise noted, homework must be turned in by email to jc33@nau.edu before class on the day it is due. 

Application presentations
-------------------------

.. important::
	Homework id: ``app``; Extension: ``pdf``; The assignment should be named ``<group-number>_app.pdf`` and ``<group-number>_app_slides.pdf``, so for example Group 1's assignments would be named ``group1_app.pdf`` and ``group1_app_slides.pdf``.

Expectations
^^^^^^^^^^^^

Each group will be pre-assigned an article seven days before their presentation date. The students will present their article in class the day they're assigned. Each member of the group will present part of the material. Answers to the following questions will be turned in (by email, with all group member names included). These answers should form an approximately two-page report. 
 
 1. What is the biological problem that the authors are trying to address?
 2. What is the motivation for addressing this problem?
 3. What previous work has been done in this area? Are there pre-existing tools that address this problem?
 4. What computational technologies did the authors make use of to create this tool (e.g., programming language, databases, etc)?
 5. What preexisting biological resources (e.g., sequence databases) did the authors make use of (if any)? 
 6. What is the input to this tool?
 7. What is the output of this tool?
 8. How did the authors test this tool? Was performance benchmarking included in their paper?
 9. How did the authors evaluate whether this tool was giving biologically meaningful results?
 
Presentations will address these same questions, and will additionally include a live demo of the software where the presenters show/discuss the input data, run the application, and show/discuss the output.

Grading
^^^^^^^

All students in the group will receive the same grade, except in circumstances where it appears that vastly different amounts of effort were contributed by different members of the same group. In addition to being graded by the instructor, anonymous reviews will be turned in by all students - the results of these reviews will factor into each group's score. 

Groups
^^^^^^

Group 1 (3/11/13): jrh355 etb36 rwf25 hhh34 (`paper <http://bioinformatics.oxfordjournals.org/content/early/2010/08/12/bioinformatics.btq461.full.pdf+html>`_ and `supplementary material <http://bioinformatics.oxfordjournals.org/content/suppl/2010/08/11/btq461.DC1/supp_mat_rev2.pdf>`_ - both are required reading!)

Group 2 (3/11/13): gz38 kn95 sk367 ad572 (`paper <http://dl.dropbox.com/u/2868868/cs299_slides_XCFGcsdFGGad/Genome%20Res.-2009-Parks-1896-904.pdf>`_)

Group 3 (3/13/13): bs527 eca37 kh832 ajc388 (`paper <http://www.mcponline.org/content/5/8/1520.full.pdf+html>`_ and `website <http://bmf.colorado.edu/divergentset/>`_)

Group 4 (3/13/13): esm23 msk53 pja43 (`paper <http://genomebiology.com/2010/11/8/R86>`_)

Homework 4: Tree of life (15 points)
------------------------------------

.. important::
	Homework id: ``tol``; Extension: ``py``, ``tre`` and ``pdf``; For this assignment, the files I turn in would be named ``jgc53_tol.py``, ``jgc53_tol.tre`` and ``jgc53_tol.pdf``.

In this assignment you will make use of the PyCogent software package to automate the process of constructing a phylogenetic tree from a set of genes. This will including querying NCBI to obtain sequences, performing a multiple sequence alignment, building a phylogenetic tree, writing a newick string containing that tree to file, and writing a visualization of that tree to a PDF file.

Your script must define a function called ``obtain_sequences_and_build_tree`` that takes:
1. a list of queries (as strings) to be run against NCBI;
2. a list of query labels (also as strings) to label the sequences resulting from each query in the final tree;
3. the filepath where the output newick string should be written;
4. the filepath where the output pdf should be written;
5. an optional parameter ``n`` which defines how many randomly chosen query results should be chosen for each of the queries. The default value for ``n`` should be 5.

Your ``obtain_sequences_and_build_tree`` function must return a phylogenetic tree derived from ``n`` aligned representatives of each of the queries passed via parameter 1. Your function definition should look exactly like this, where you replace ``# do a bunch of work`` with your code::

    def obtain_sequences_and_build_tree(queries,
                                        query_labels,
                                        output_newick_fp,
                                        output_pdf_fp,
                                        n=5):
        # do a bunch of work
        return tree

As part of your analysis, you should filter any sequences that have one or more ``N`` characters in them. Each sequence label in the output tree should begin with the query label corresponding to that sequence. ``tree`` should be a PyCogent ``PhyloNode`` object (the output of ``cogent.app.fasttree.build_tree_from_alignment``).

In your script, you should call the function you define as follows::

    obtain_sequences_and_build_tree(
         ['"small subunit rRNA"[ti] AND archaea[orgn]',
          '"small subunit rRNA"[ti] AND bacteria[orgn]',
          '"small subunit rRNA"[ti] AND eukarya[orgn]'],
         ['A: ','B: ','E: '],
         "<nau-id>_tol.tre",
         "<nau-id>_tol.pdf",
         n=5)

where ``<nau-id>`` is replaced with your NAU identifier. This should perform all of the analysis steps and write the newick file and PDF to the directory where you are running the script from. You'll turn in the script, the newick file, and the PDF.

.. note::
	`This page <http://dl.dropbox.com/u/2868868/pycogent_160dev_docs/cookbook/building_a_tree_of_life.html>`_ should help quite a lot.

.. note:: 
	The cluster has PyCogent, muscle, and FastTree preinstalled. Working there will save you a lot of time on software installation.

.. note::
	Remember that you can call ``dir()`` on an object to find out what methods are available to that object. One of the methods associated with your tree object will help you generate a newick formatted tree.

Homework 3: Alignments (25 points)
----------------------------------

.. warning:: This is a big assignment. Start early!

.. important::
	Homework id: ``align``; Extension: ``ipynb``; For this assignment, the file I turn in would be named ``jgc53_align.ipynb``.

.. important:: For this assignment you should work in the QIIME Virtual Box, or in another local IPython installation. You may not use the class IPython Notebook server for this, since it is not a mutli-user environment (i.e, other students will see your work). After installing the QIIME Virtual Box (`instructions here <http://qiime.org/install/virtual_box.html>`_), you can start IPython by opening a terminal and typing ``ipython notebook``. Leave the terminal window open, and open the URL that is printed to the terminal. 

Begin with the Needleman-Wunsch implementation in the `Lecture 10 IPython Notebook <https://speakerdeck.com/gregcaporaso/bio-299-lecture-8-10-nau-fall-2013>`_ and the materials in the `Lecture 8-10 slides <http://nbviewer.ipython.org/4657175/Lecture10.ipynb>`_.

For this assignment you will turn in an IPython notebook. You will generate this notebook by starting with the `Lecture 10 IPython Notebook <http://nbviewer.ipython.org/4657175/Lecture10.ipynb>`_ and modifying to add new functionality and annotation.

Part 1
^^^^^^
Add a new function with this `exact` form::

    nw_align(sequence1,sequence2,substitution_matrix)

This function should return, in this order, the aligned sequence 1 as a string, the aligned sequence 2 as a string, and the score of the global alignment.

To confirm that this is working for you, you should test with the following command, as this is one of the tests that we will apply to your homework::
	
	nw_align('HEAGAWGHEE','PAWHEAE',blosum50)

which should result in the following output::
	
	("HEAGAWGHE-E", "--P-AW-HEAE", 1.0)

Part 2
^^^^^^

In the same notebook, define a new function of the form::

    generate_random_score_distribution(query_sequence,subject_sequence,n,substitution_matrix)

Which returns a list of ``n`` scores for aligning each of ``n`` random sequences of the same length as ``query_sequence`` against ``subject_sequence``. 

Next, define a function that takes a query sequence, a subject sequence, and a value ``n`` with this form::

    fraction_better_or_equivalent_alignments(query_sequence,subject_sequence,n,substitution_matrix)

This function should call ``generate_random_score_distribution`` to generate a list of scores for random alignments. It should then compute the score for aligning ``query_sequence`` against ``subject_sequence``. The return value of this function should be the number of random alignment scores that are better or equal to the actual alignment score divided by ``n``.

After defining this function, use it to compare the following sequences to one another using a value of ``n=1000`` when calling ``fraction_better_or_equivalent_alignments`` as follows::

	subject = "SAVLDMRPPEITCLCLHSVEWFWATDRAYITKFHVGQPMKCITGCHVFCGPRTSNLLQESCMYCVFSEIGCRNSANCFNFTRSCIRISSYLFSYYIVWGC"
	query1 = "RHT"
	query2 = "RHTSWIL"
	query3 = "RHTSWIIQECWYCWFS"
	query4 = "RHTSWIIQESCWYCWFSEIGCRNSANWFNFTRSCWRISYLFS"
	fraction_better_or_equivalent_alignments(query1,subject,1000,blosum50)
	...

Each of these query sequences is designed to be similar to the subject. Also compare some randomly generated query sequences to the subject sequence. Do this several times. In a *markdown cell* just below this analysis, describe any general patterns that you notice. What do you think this means? Run this example on the alignment we worked through in class (query sequence: ``HEAGAWGHEE``; subject sequence: ``PAWHEAE``) and describe the results. How does this alignment compare to your randomly generated alignments?

.. note:: In the `Lecture 8 IPython Notebook <http://nbviewer.ipython.org/4657175/Lecture8.ipynb>`_ there is code illustrating how to generate a random sequence of bases at a given sequence length (see the last cell where ``root_sequence`` is defined). Here we're working with protein sequences, so the alphabet is different but the process is the same.

.. note:: In my `Lecture 8-10 slides <Sequence searching and alignment	https://speakerdeck.com/gregcaporaso/bio-299-lecture-8-10-nau-fall-2013#>`_ I provide details on the differences between SW and NW initialization, scoring, and traceback. 

Part 3
^^^^^^

Define a general function that can perform global (Needleman-Wunsch; NW) or local (Smith-Waterman; SW) alignments.

Define a new function, ``generate_sw_and_traceback_matrices`` with the following form::

    generate_sw_and_traceback_matrices(seq1,seq2,gap_penalty,substitution_matrix)

The return value should be the dynamic programming matrix and the traceback matrix for a SW alignment.

.. note:: This will be much easier if you start with the ``generate_nw_and_traceback_matrices`` and modify it for Smith-Waterman.

Define a new function ``sw_traceback`` with the form::

    sw_traceback(traceback_matrix,sw_matrix,seq1,seq2)

This function should return aligned the aligned sequences in the order they were passed in and the alignment score.

.. note:: This will be much easier if you start with the ``nw_traceback`` and modify it for Smith-Waterman.

Next, define a new function ``sw_align`` with the form::

	sw_align(sequence1,sequence2,substitution_matrix)

.. note:: This will be much easier if you start with your ``nw_align`` function and modify it for Smith-Waterman.
Define a new function ``align`` with the following form::

    align(sequence1,sequence2,substitution_matrix,local)
    
Where ``local`` is a boolean (i.e., True or False) value. This function should return aligned_sequence1, aligned_sequence2, and the best alignment score. If ``local==False``, an NW alignment should be performed. If ``local==True`` an SW alignment should be performed. 

Run both local and global alignments as follows to test that this is working as expected::
	
	align('HEAGAWGHEE','PAWHEAE',blosum50, False)

which should result in the following output::
	
	("HEAGAWGHE-E", "--P-AW-HEAE", 1.0)

and::
	
	align('HEAGAWGHEE','PAWHEAE',blosum50, True)

which should result in the following output::
	
	("AWGHE", "AW-HE", 28.0)


Guest lecture reports (due 11 February 2013) (15 points; 7.5 points each)
-------------------------------------------------------------------------

For each of the two guest lectures, turn in answers to the questions in `this document <https://docs.google.com/document/d/1Fieqfkbn-dMLjR6bpVqoT8E8Rb9HBtAfCSvesvIvLtI/edit>`_. You can download this document and use it as a template for your assignment. You will turn these in as two separate PDFs by email to jc33@nau.edu. Taking detailed notes during these lectures will make this assignment a lot simpler!

.. important::
	Homework ids: ``johnson_lecture`` and ``butterfield_lecture``; Extension: ``pdf``; For this assignment, the files I turn in would be named ``jgc53_johnson_lecture.pdf`` and ``jgc53_butterfield_lecture.pdf``. 

BLAST exercises (due 4 February 2013) (20 points)
-------------------------------------------------

Using `NCBI nucleotide BLAST <http://blast.ncbi.nlm.nih.gov/Blast.cgi?PROGRAM=blastn&BLAST_PROGRAMS=megaBlast&PAGE_TYPE=BlastSearch&SHOW_DEFAULTS=on&LINK_LOC=blasthome>`_, complete the `assignment worksheet <https://docs.google.com/document/d/1x_ilvV9zW_SI1sFyqukhLz0Lnd4gAmwlVEJ4jrC814Q/edit>`_. You should turn in a PDF of that file with all answers filled in by email to jc33@nau.edu.

.. important::
	Homework id: ``blast``; Extension: ``pdf``; For this assignment, the file I turn in would be named ``jgc53_blast.pdf``. 
	
.. note:: This assignment is derived from `BLASTing Through the Kingdom of Life <http://www.digitalworldbiology.com/BLAST/62000sequences.html>`_. You may find `this tutorial <http://www.digitalworldbiology.com/BLAST/index.html>`_ to be very helpful. 

Query sequences::

	>Sequence1
	AACAATTCATTTTTCCTGCTTTCCTAGAAAATTCTATAAAAGCTTCAAAA
	TGAATTACTTGGTGATGATTAGTTTGGCACTTCTCTTCGTGACAGGTGTA
	GAGAGTGTAAAAGACGGTTATATTGTCGACGATGTAAACTGCACATACTT
	TTGTGGTAGAAATGCATACTGCAACGAGGAATGTACCAAGTTGAAAGGTG
	AGAGTGGTTATTGCCAATGGGCAAGTCCATATGGAAACGCCTGTTATTGC
	TATAAATTGCCCGATCATGTACGTACTAAAGGACCAGGAAGATGCCATGG
	CCGATAAATTATAAGATGGAATGTATCCTAAGTATCAATGTTAAATAAAT
	ATAATCAAAAAATT
	>Sequence2
	CTAATAATCCTTGGAATACTCCTATATTTTGTATAAAGAAGAAATCAGGG
	AAATGGAGAATGCTAATTGATTTTAGAGAACTTAATGCAAAAACAGAAAA
	AGGAGCAGAAGTCCAATTAGGATTACCTCACCCATCTGGATTACAGAAGA
	GAAAGAATGTAACAGTTTTAGATATAGGAGATGCTTATTTTACCATCCCT
	TTAGATCCTGATTATCAGCCCTATACTGCATTTACTTTACCATCTAAGAA
	TAATCAAAGTCCAGGAAAAAGGTATATTTGGAAATCTCTTCCACAGGGGT
	GGGTCTTGAGTCCCTTAATATACCAGAGCACTCTAGATAATATTCTACAA
	CCATTTAGAA
	>Sequence3
	TCTTGGTGAGGATCCGTTGAGAACAACCCAACCGCCGCCCCATCGCCCTN
	GTTAGANTNATGGCCGCGTCGGCGCTGCACCAGACCACCAGCTTCCTCNG
	CACCGCCCCTCGCCGGGATGAGCTCGTCCGCCGCGTCGGCGACTCCGGTG
	GCCGCATCACCATGCGCCGCACCGTCAAGAGCGCGCCCCAGAGCATCTGG
	TATGGACCTGACCGTCCCAAGTNCCTGGGCCCGTTCTCGGAGCAGACGCC
	ATCGTACCTGACCGGAGAGTTCCCGGGAGACTACGGGTGGGACACGGCGG
	GGCTATCGGCCGACCCGGANACGTTCGCTATGAACAGGGAGCTGGANGTG
	ATCCACTCNCGGTGGGCGATGCTGGGGGCGCTGGGCTGCGTCTTCCCGGA
	GATCCTGTCCAANAACGGGG
	>Sequence4
	GTTTTTAAAAGAGTTTGATCCTGGCTCAGGGTGAACGCGAATCAGCGCAC
	TTAACACATGCAAGTTTTATGGATAGCTTTGAGCCTAGCTTTTAGTTAGA
	CATAGCGAACGGGTGCGTAATGCTTAAGAATCTACTTTTAACTAAGGGAT
	AATGGAAGGAAACTTTTGCTAATTCCTTATAGGTATGGATAAGATAACCT
	ATCTTCATCTTGTTTAGAAAAAATTTGGCTGCTCAACGTAGTTAAGTTGG
	TTAAAAAAGAGCTTGAATCTGATTAGTTAGTAGGTGAGGTAAAGGCTTAC
	CTAGACGATAATCGGTAGCGGATCTGAGAGGATGACCCGCCACATTGGGA
	CTGAGACACGGCCCAAACTTCTACGGAAGGCAGCAGTGAGGAATATTCTG
	CAATGGGCGAAAGCCTGACAGTGTGACGCTGAGTGAAGGATGAAGGCCAC
	AACCCGAGTTCGGGGGTCGTAAACTTCTTTTCCTAGGCGAAGAATAATGA
	CTAACCTAGCAAGAAAGTATCGGCTAACTCCGTGCCAGCAGCCGCGGTAA
	GACGGGGGATGCGAGCGTTATCCGGAATGACTGGGCGTAAAGCGTTTGTA
	GGTGATCTTCTAAGTCTTGGTTTAAATCATAAAGCTTAACTTTTAAAAGA
	GCCAAGATACTGGTTGAATAGAGTGAAATTGAGGTATTTGGGGGAATTCT
	TAGAGGAATAGTAAAATGTAACGATACTAAGATGAAGACCGAAGGCGAAG
	GCGTCATACTAAATTTTAACTGACACTCAAGGACGAAAGCTAGGGGAGCA
	AATGGGATTAGAGACCCCAGTAGTCTTAGCAGTAAACGATGAGTACTAGA
	TGTTGGACGCACGGTAATATATAATCTATTTATCTACTCGTTCGGTATCT
	AAGCTAACGCAATAAGTACTCCGCCTGAGGAGTACGCTCGCAAGGGTGAA
	ACTCAAAGGAATTGACGGGGGCTCGTACAAGCGGCGGAGCATGTGGTTTA
	ATTTGATGCAAAGCAAAAAATCTTACCAGAGCTTGAAGTTGAAATTTTCA
	AATTTAATCGATTTGAAAAGCCATAAATTGGCAAAAACGAGGTGGTGCAT
	GGCTGTCGTCAGCTCGTGTCGTGAGACGTTGGGTTAATTCCCTTAACGAG
	CGCAACCCTTGTCATAAGTTCTTTTGTCTTATGAGAAGGCTCGATTCGTC
	GAGATTAAGAGGAGGATGACGTCAAGTCATCATGCCCTTTATGCTCTGGG
	CTACACACGTGCTACAATGGTCGTTACAATAAGTACTGAAGAAAAAAACG
	TATAACGATTATACGTTTAATTTTAACGTAAGTATGAAAATATTTACAAA
	TCTTTAAAAGCGTAGCCCTAATATGAATCGTGGACTGAAACTCGTCCACG
	TCAAACCGGAGTCGCTAGTAATCGCCGGTCACCATTACGGCGGTGAATAC
	GTAACCGAGCCTTGTACACACCGCCCGTCACACCCTGGGAATTTAGGCTT
	TTTGAAACATCTGCAGTGGGTGCGATTAAGGATTGGGTAACTGGGGTGAA
	GTCGTAACAAGGTAGCGGTACTGGAAGGTGCAGCTGGA


GC content (due 23 January 2013) (10 points)
--------------------------------------------
Download a genome and compute its GC content. Copy or download `the assignment <https://docs.google.com/document/d/1iY1sfH9uKulmO0CLugtQOzBoAIGqh0oIwzZfa1ARay0/edit>`_, fill in your answers, and turn the assignment in by email as a PDF.

Note that there are various ways that you can just look up the GC content, including via the IMG website. I'm asking you to compute it, and you're being graded on your descriptions. Getting the right answer is a bonus (i.e., if you spend a couple of hours trying, and get it wrong, you'll be graded on your well-documented effort, not your final answer).

Hints: Start with the IMG Genome Browser, and work with a bacterial, archaeal or viral genome.

Be creative - there are many ways to achieve this.

.. important::
	Homework id: ``gc_content``; Extension: ``pdf``; For this first assignment, the file I turn in would be named ``jgc53_gc_content.pdf``. 