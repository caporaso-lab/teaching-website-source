==========================================================================================
Homework assignments
==========================================================================================

.. important:: I encourage you to discuss homework assignments with each other, but you may not view other student's assignments or share your assignment with others. When you start programming, you often think there is a single way to address a task, but that is usually not the case: there are many ways to complete these assignments, and when code has been shared or copied it is often very obvious to a more experienced eye.

Turning in your homework by email
---------------------------------
Your homework must always be turned in with a standardized name. That name should be ``<nau_id>_<homework_id>.<extension>``, where ``<nau_id>`` is your NAU identifier (for example, mine is ``jgc53``), and ``<homework_id>`` and ``<extension>`` are provided on a per-assignment basis. 

Unless otherwise noted, homework must be turned in by email to jc33@nau.edu before class on the day it is due. 

Guest lecture reports (due 11 February 2013)
--------------------------------------------

For each of the two guest lectures, turn in answers to the questions in `this document <https://docs.google.com/document/d/1Fieqfkbn-dMLjR6bpVqoT8E8Rb9HBtAfCSvesvIvLtI/edit>`_. You can download this document and use it as a template for your assignment. You will turn these in as two separate PDFs by email to jc33@nau.edu. Taking detailed notes during these lectures will make this assignment a lot simpler!

.. important::
	Homework ids: ``johnson_lecture`` and ``butterfield_lecture``; Extension: ``pdf``; For this assignment, the files I turn in would be named ``jgc53_johnson_lecture.pdf`` and ``jgc53_butterfield_lecture.pdf``. 

BLAST exercises (due 4 February 2013)
-------------------------------------

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


GC content (due 23 January 2013)
--------------------------------
Download a genome and compute its GC content. Copy or download `the assignment <https://docs.google.com/document/d/1iY1sfH9uKulmO0CLugtQOzBoAIGqh0oIwzZfa1ARay0/edit>`_, fill in your answers, and turn the assignment in by email as a PDF.

Note that there are various ways that you can just look up the GC content, including via the IMG website. I'm asking you to compute it, and you're being graded on your descriptions. Getting the right answer is a bonus (i.e., if you spend a couple of hours trying, and get it wrong, you'll be graded on your well-documented effort, not your final answer).

Hints: Start with the IMG Genome Browser, and work with a bacterial, archaeal or viral genome.

Be creative - there are many ways to achieve this.

.. important::
	Homework id: ``gc_content``; Extension: ``pdf``; For this first assignment, the file I turn in would be named ``jgc53_gc_content.pdf``. 