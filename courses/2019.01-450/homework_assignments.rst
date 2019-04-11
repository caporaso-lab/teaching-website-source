==========================================================================================
Homework assignments
==========================================================================================

.. important:: I encourage you to discuss homework assignments with each other, but you may not view other student's assignments or share your assignment with others.

Homework assignments will be listed here as they are assigned.

Turning in your homework by email
---------------------------------

Your homework must always be turned in with a standardized name. That name should be ``<nau_id>_<homework_id>.<extension>``, where ``<nau_id>`` is your NAU identifier (for example, mine is ``ams379``), and ``<homework_id>`` and ``<extension>`` are provided on a per-assignment basis. **Assignments that are not turned in according to these specifications will lose 10%.**

Unless otherwise noted, homework must be turned in by email to Arron (ams379@nau.edu) before class on the day it is due.

Assignment 1: GC content (see schedule for due date, 10 points)
---------------------------------------------------------------
Download a genome and compute its GC content. Copy or download `the assignment <https://docs.google.com/document/d/1iY1sfH9uKulmO0CLugtQOzBoAIGqh0oIwzZfa1ARay0/edit>`_, fill in your answers, and turn the assignment in by email as a PDF. **While you will get started on this assignment in class (optionally in small groups), you will complete the questions in assignment yourself.**

Note that there are various ways that you can just look up the GC content, including via the IMG website. I'm asking you to compute it, and you're being graded on your descriptions. Getting the right answer is a bonus (i.e., if you spend a couple of hours trying, and get it wrong, you'll be graded on your well-documented effort, not your final answer).

Hints: Start with the `NCBI Genome Browser <http://www.ncbi.nlm.nih.gov/genome>`_, and work with a bacterial, archaeal or viral genome.

Be creative - there are many ways to achieve this.

.. important::
	Homework id: ``gc_content``; Extension: ``pdf``; For this first assignment, the file I turn in would be named ``jgc53_gc_content.pdf``.


Assignment 2: BLAST exercises (see schedule for due date, 20 points)
--------------------------------------------------------------------

Using `NCBI nucleotide BLAST <http://blast.ncbi.nlm.nih.gov/Blast.cgi?PROGRAM=blastn&BLAST_PROGRAMS=megaBlast&PAGE_TYPE=BlastSearch&SHOW_DEFAULTS=on&LINK_LOC=blasthome>`_, complete the `assignment worksheet <https://docs.google.com/document/d/e/2PACX-1vQcHJfgGWr3AP98-HD9VEm8KYtBIlzyHnYNPZjCI8ncduR77ubXFhbXm8E3-ykVzf5bguRJ8hQfxLLX/pub>`_. You should turn in a PDF of that file with all answers filled in by email.

.. important::
Homework id: ``blast``; Extension: ``pdf``; For this assignment, the file I turn in would be named ``jgc53_blast.pdf``.

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
		TTAATACATGCGAGTTGAACGTGAATTTTTTAATTAAAATGAAAGTAGCGT
		ACTGGTGAGTAACACGTGAGAATCTACCTTTCAAATCAACATAAAATGTTG
		AATAAAAGCTTCTAAAGCTATAAAGATATGTTTTCGTTGAAAGATGAGCTT
		GCGCAAGATTAGGTAGTTGGTAAGGTAACGGCTTACCAAGCCAAAGATCTT
		TAGCTGGTTTGAGAAAATGATCAGCCACATTGGAACTGAAACACAGTCCAA
		ACGTAATATAACGGCAGCAGTAGGGAATTTTGAACACTGAGCGAAAGCTTG
		ATTCAGCCAAGTATCGTGGATGAAGAAGGCTGTCTTTTGGTCGTAAAATCC
		ATTTATATAGTCACATGAAATGTGTCTTTTATTTCGATAAAAGGAAAGATT
		ATGACTTTCTATTGAAAAGTCCCGGCTAATCTCGTGCCAGCAGCCGCGGTA
		ATACGAGAGGGGCAAACGATGTTTAGCATGATTGGGCGTAAAGAGCTTGTA
		GATGGTTTCTTTTAATTTTATATAAAAGCTCTAAGCTTAACTTTGATTATA
		TATAAAGGAAAGATAACTTGAGTTATGGAAAGGAAAGTAGAATTCTTGGAG
		GAGAGGTAGAATTTGGTGATATCAAGAGGAATTCCAAAAGCGAAGGCAGCT
		TTCTTGCCATATACTGACATTGAAGGGCGAAAGCGTGGGTAGCGACAGGGA
		TTAGATACCCCATTAGTCCACGCCGTCAACGATGACCTTTATTTATTGGTT
		TCTCTTAAAATAAATAAATTATTTTTTAGTTTGATCAGTGAAACAGTTAAC
		GCGTTAAAAGGTCCGCCTGAGGAGTACGATCGCAAGATTAAAACTCAAAAG
		AATAGACGGGAGCGTTCACAAGTGGTGGAGCATGAAGTTTAATGCGATACA
		ACACGCAAAACCTTACCATTTTTTGATATTTTACTTATCAGTTATTTCTCA
		TGAAATAATGTTTTTTACTAAAGTAAAAATTTGTTTGTATAACAGGCGTTG
		CATGGCTGTCGTAAGTTCGTACTGTGAAGTGTTGGATTAATTTCCTTAACG
		AACGTAACCCCTTGGTTTTGTTAAAACTAAAATCTACCGCTAGTCATAAAC
		TAGAGGAAGGGAGGGATCACGTCAAGTCCTCATGACCCTTATAAAATGGGC
		TACGCTTTTCGTGCTACAATGATAAATACAATAAGAAGCAATAACGAAAGT
		TGGAGCAAATCTATAAAATTTATCTCAGTTCAGATTGTTCTCTGCAATTCG
		AGAACATGAAGATGGAATCACTAGTAATCGTAGATCAGCATGCTACGGTGA
		ATATGTAATTACGCTCTGTACTCACAGCCCGTCACACAATGGAAGTAAAAT
		GTATCGGAAATTTGTCAAATATTGTTAGATTTTCTTTTTTAAATTTATTGA
		ATAAATTATTTTAATTAATATCTTTCAACTAAATGGGAACTGATGATATGT
		TTCATGACTGTTGTGAAGTCGTAACAAGGTAGCGCTAGCGGAAGCTGGTGC
		TGGAT
		>Sequence5
		TTCCGGTTGATCCTGCCGGACCCGACTGCTACTTGGGTGAGAATAAGCCAT
		GCAAGTCGAATGGAATACCAAAATATTCCATAGCAAACTGCTCAATAACAC
		GTGATCAACTTACCCTATGGAAAACAATAACCTCTGGAAACGGAGGATAAT
		GGTTTATAGTTGAAAAGGCTTGGAAAAGTTTTTCAATAAAAGGGAATAATA
		AAAATGGTTATTATTTTGCCATAGGATAGGATTGCGGTCGATCATGGCTGT
		TGGTGAGGTAATGGCTCACCAAACCAATAATCGATAGGGGCCGTGAGAGCG
		GGAGCCCCGAGATGGGTACTGAGACAGCGACCCAGGCCTTACGAGGTGCAG
		CAGGCGCGAAAACTCCGCAATACGCGAAAGTGTGACGGGGTTACCCAAGGT
		GCTTAATTTTTAAGCTGTGGTAAGTGTGTAATGTACCTTACTAGAAAGGAG
		AGGGCAAGGCTGGTGCCAGCCGCCGCGGTAAAACCAGCTCTTCAAGTGGTC
		GGGATAATTATTGGGCTTAAAGTGTCCGTAGCTTGTATAATAAGTTCCTGG
		TAAAATCTAATAGCTTAACTATNAGTATGCTAGGAATACTGTTGTACTAGA
		GGGCGGGAGAGGTCTGAGGTACTTCAGGGGTAGGGGTGAAATCCTATAATC
		CTTGAAGGACCACCAGTGGCGAGGGCGTCAGACTGGAACGCGCCTGANAGT
		GAGGGACGAAAGCCAGGGGAGCGAACCGGATTAGATACCCGGTAGTCCTGG
		CCGNTAAACGATGCACACTAGGTGTGGTATGGCTATTGAGCCCATATCAGT
		GCCGAAGGGAAACCCATTAAGCGTGCCGCCTGGGGAAGTACGGTCGCAAGG
		CTAAAACTAAAAGGAATTGGCGGGGGAGCACCACAAAGGGGTGAAGCCTGC
		GGTTCAATTGGACTCAACGCCGGGAAAACTTCCCAGGGGAGACAGCAGAAA
		TGAAAAGTCAGGTTGACGACCTTACTTAACGAGCTGAGAGGAGGGTGCCAT
		GGCCGTCGCCAGTTCGTGCCGTGAGGTATCCTGTTAAGTCAGGCAACGAAC
		GAGACCCGTGCTTTTAGTTCCCAGCAAGACGTCACGACTTCGATGGGAACA
		CTAAAAGGACCGCCATCGATAAGATGGAGGAAGGAGCGGGCCAAGGCAGGT
		CAGTATGCCCCGAAACCCCTGGGCCACACGCGGGCTGCAATGGTATGAACA
		ATGGGCTGTAACTCCGAAAGGAGAAACCAATCCCGAAATCATATCTCAGTT
		GGGATTGTTGGCTGTAACTCGCTGACATGAACGTGGAAT
		>Sequence6
		AGAGTTTGATCCTGGCTCAGGATGAACGCTAGCTACAGGCTTAACACATGC
		AAGTCGAGGGGCAGCATGGTGTATCAATATATCTATGGCGACCAGCGCACC
		GGTGATGCACACCTCTCCTACCTGCCCCTTACTCCGGGATGATCTTTCTAA
		AAAAATATTACTACTCCATGGTATTACCGAAAAACGTCTTTTTGTTGTTTA
		AAAACTTCGATGGTGGAAGGTGATGCTTTCTATTATATACTTGGTGGGGTA
		ACAGCCCACCACCTCAGCGATGAATAGGGGTTCTAATAAGAAGGTCCCCCC
		CATGGTAACTGGGCCCCGGTCCAAATTCTTCGGGAAGCCACCAGTGAGGAT
		TATTGTTCAATGGCGGAGATTTTGACCCAGCCCAAGTAGCGTGAAGGATGA
		CTGCTCCCATAGGTGGTAAACTTCTTTTATATGGGAATAAAGTGAGTCACG
		TGTGTCTTTTTGTATGTATCATATGAATAAGGATCGGCTAACTCCGTGCCA
		GCAGCCGCGGTAATACGGAGGATTCGAGCGTTATCCGGATTTATTGGGTTT
		AAAGGGAGCGTAGGCGGTTTGTTAAGTCAGTGGTGAAAGTTTGGGGCTCAA
		CCGTGAAATTGCATTTGATACTGGCGGTCTTGAGTGCAGTAGAGGTGGGCG
		GAATTTGTGGTGTAGCGGTGAAATGCTTAGATATCATGCAGAACTCCGATT
		GCGAAGGCAGCTCACCGGAGTGTATCTGACGTTGAGGCTCGAAAGTGTGGG
		TATCAAACAGGATTAGATACCCTGGTAGTCCACACAGTAAAGAAGGAATAT
		TGTCGTTGTGGGATCTCCATTAAGGGGTCAAGGGAAAGCATTAATTATTCC
		CCTGGGGGAGTAGTCCGCCAGAGGTGAAATTAAAAGAAATGGAGGGGGGCC
		GGCCCAAGGGAAGGACCATGTGGTTTAATTGGAGGATAGGGGAGGACCTTT
		CCCGGGGTTGAAAGTGCAAATGAATTATGGGGAGAGCCATTCCCTTCAAGG
		CATGAGAGAAGGTGCTGCATGGTTGTCGTCAGCTCGTGCCGTGAGGTGTCG
		GGTTAAGTCCCATAACGAGCGCAACCCTTATCTTCAGTTACTATCAGGTCA
		AGCTGAGCACTCTGGAGAGACTGCCGTTGTAAGATGAGAGGAAGGTGGGGA
		TGACGTCAAATCAGCACGGCCCTTACGTCCGGGGCTACACACGTGTTACAA
		TGGGGGGTACAGAAGGCAGCTACCCAGCGACAGGATGCCAATCCCAAAAAC
		CTATCTCAGTTCGGATTGAAGTCTGCAACCCGCCTTCGTGAAGTTGGATTC
		GCTAGTAATCGCGCATCAGCCATGGCGCGGTGAATACGTTCCCGGGCCTTG
		CACACACCGCCCGTCA
		>Sequence7
		GATGAACGCTGGCGGCGTGCCTAATACATGCCAGTCGAGCGAACTTATGAT
		AAGCTTGCTTCTCTGATGTTAGCGGCGGACAGGTGAGTAACGCTTGGGTAA
		CCTACCTATAACAGTGGGATAACTCCGGAAAACCGGGGCTAATACCGGATA
		ATATATTGAACCGCATGGTTCAATGTTGAAAGACGGTTTCGGCTGTCTCTT
		ATAGATGGACCCTCGCCCCATTATCTATTTGGTAAGGGAACAGCTTACCGA
		GGCAACGAGACGTAACCCACCTGAGAGGGTGATCGGCCACCCTGCAACTGA
		GACCCGGTCCACACTCCTAACGCAGGCAGCAGGAAGGAATCTTCCACCATG
		GGCGAAAGCCTGACGGATCACCGCCCCGCGACTGATGAATGACTTAGGATC
		TCAAATCTCTGTTGTCAGGGAAGAACAAATATGTTAGATACTGAACAAATC
		TTGACCGCACCTCACCATAAAGCCACGGCTAACTACGTGCCAGCAGCCGCG
		GTAATACGTAGGCGGCAATCGTCATCCGGAATTATTGGGCGTAAAGCGCGC
		GTAGGCGTTTTCTTTAGTCTGATGTGACAGCCCGCGCCTCAGCCGTGGAGC
		GTCATTGGAAACTGGGGAACTTGAGTGCAGAGGAGAGTGGAATTCCATGTG
		TAGCGGTGAAATGCGCAGAGATATGGAAGAACACCAGTGGCGAAGGCGGCT
		CTCTGGTCTGTAACTGACGCTGATGTGCGAAAGCGTGGGGATCAAACAGAA
		TTAGATACCCTGGTAGTCCACGCCGTAAACGATGAGTGGTAAGTGTTAGGG
		TGTTTGCGCTCCTTAGTGCTGCAGCTAACGCATTAAGCACTCCGCTCGGGG
		AGTGCGACTGCAAGGTTGAGATTCAAATGAATTGACGGGACCCGCACAAGC
		GGTGGAGCATGTGGTTTAATTCGAAGCAACGCGAAGAACATTAACAAATCT
		TGACATCGTCAGATCGCTCTAGAGATAGAGTTTTAGCTTTCGGTGGACAAA
		GTGACAGGTGGTGCATGGTTGTCGTCAGCTAGTGTCGTGAGATGTTGGGTT
		AAGTACAGTGCAACGAGCGCAACCCTTAAGTTTAGTTGCCATCATTAAGTT
		GGGCACTATTGGTTGACTGCCGGTGACAAACCGGAGGAAGGTGGGGATGAC
		GTCAAATCATCATGCTCCTTATGATTTGGGGTACACAAGTGGTGCAATGGA
		TAATACGAAGGGCAGTGAACCCGTGAGGTCAAGCAAATCCTATAAAATTAT
		TTTCAGTTGGGATTGTAGTATGCAACTAGTCTACATGAAGAAGGAATAGTT
		AGTAATAGTAGATCAGCATGATACGGTGAATAAGTTCCTGGGTGTCGTACA
		CCCCGCCCGTCACCCCACCAGAGTTTGTAACACCAGAAGCCGGTGGAGTAA
		CATTTTATTAGGAGCTAGCCGTCGAAGGTGGGAC


Assignment 3: Pairwise alignment exercises
------------------------------------------

For this assignment, you will answer four questions from the IPython Notebook provided `here <https://github.com/applied-bioinformatics/built-iab/blob/master/IAB-notebooks/4/1.ipynb>`_. Download that file (click the download icon on the top-right) and then upload it to the `class Jupyter Notebook server <https://jupyter.hpc.nau.edu/>`_. You should answer the questions in a text or word processing document, and email that document as a PDF before class on the due date.

Point breakdown:
 * Question 1: 4 points
 * Question 2: 2 points
 * Question 3: 2 points
 * Question 4: 12 points; This is the majority of the assignment. You should answer with 1-2 paragraphs. This is also where we can score you on your process, rather than just on whether you get the correct answer, if you provide sufficient detail.


.. important::
	Homework id: ``pairwise_alignment``; Extension: ``pdf``; For this assignment, the file I turn in would be named ``jgc53_pairwise_alignment.pdf``.


Assignment 4: Multiple sequence alignment and phylogeny exercises
-----------------------------------------------------------------

For this assignment, you will answer questions from the IPython Notebook provided `here <https://github.com/applied-bioinformatics/built-iab/blob/master/IAB-notebooks/4/2.ipynb>`_. Download that file (click the download icon on the top-right, and save it to your computer) and then upload it to the class IPython Notebook server. You should answer the questions in your copy of the IPython Notebook, and submit that notebook by email.

Point breakdown:
 * Question 1: 1 point
 * Question 2: 1 point
 * Question 3: 2 points
 * Question 4: 2 points
 * Question 5: 10 points; This is the majority of the assignment. You should thoroughly explain your process (7 pts) and provide the correct answers (3 pts).
 * Question 6: 2 points
 * Question 7: 2 points

.. important::
	Homework id: ``multiple_alignment``; Extension: ``ipynb``; For this assignment, the file I turn in would be named ``jgc53_multiple_alignment.ipynb``.

Assignment 5: Microbiome-based forensics with QIIME 2
-----------------------------------------------------

For this assignment, you will run analyses and answer questions in the Jupyter Notebook provided `here  <http://nbviewer.jupyter.org/github/gregcaporaso/bio450-qiime2-assignment/blob/master/qiime2-assignment.ipynb>`_. Download that file (click the download icon on the top-right, and save it to your computer) and then upload it to the class Jupyter Notebook server. You should answer the questions in **Parts 1 and 2 only** in your copy of the Jupyter Notebook, and submit that notebook by email. You will also submit all `.qzv` files that you reference in your answers to the *Part 2 Questions*.

.. important::
	Homework id: ``qiime2``; Extensions: ``ipynb`` and ``.qzv``. For this assignment, the files I turn in would be ``jgc53_qiime2.ipynb``, and some number of ``.qzv`` files (these can have any file names).


Group presentations
-------------------

Groups will be assigned in class.

.. important::
	Homework id: ``app``; Extension: ``pdf``; The assignment should be named ``<group-number>_app_slides.pdf``, so for example Group 1’s assignment would be named ``group1_app_slides.pdf``.

Each group will be pre-assigned a bioinformatics software package and associated documentation or paper at least two weeks before their presentation date, and will present the software in class the day they’re assigned. Every member of the group must give part of the presentation. Your presentation should answer the following questions and your slides must be turned in as a PDF (by email, with all group member names included, before class on the day of your presentation).

#. What is the biological problem that the authors are trying to address?
#. What is the motivation for addressing this problem?
#. What previous work has been done in this area? Are there preexisting tools that address this problem?
#. What computational technologies did the authors make use of to create this tool (e.g., programming language, databases, etc)?
#. What preexisting biological resources (e.g., sequence databases) did the authors make use of (if any)?
#. What is the input to this tool?
#. What is the output of this tool?
#. How did the authors test this tool? Was performance benchmarking included in their paper?
#. How did the authors evaluate whether this tool was giving biologically meaningful results?

Your presentation will additionally include a live demo of the software where the presenters show/discuss the input data, run the application, and show/discuss the output. Your presentation should be 15 +/- 2 minutes, including the live demo. **You will lose points if your presentation falls outside of this time range.**

All students in a group will receive the same grade on this assignment, unless there is clear evidence that some student(s) didn’t contribute, in which case the rest of the group should discuss with the instructor.

Presentations groups
````````````````````
.. raw:: html

	<iframe src="https://docs.google.com/spreadsheets/d/e/2PACX-1vQE_rDxdEcfnlm0ESoEUdoEPivz1RpUnB5mVE8DYuDTBuy9p6fRDIwjXFv3rnQTZb9s14UXaRYxtb1i/pubhtml?gid=0&amp;single=true&amp;widget=true&amp;headers=false" width="1000" height="400"></iframe>

BIO 685: extra assignment and presentation
------------------------------------------

Students enrolled in BIO 685 will have one extra assignment that is ideally tailored to their graduate research. They will present this project individually in place of joining a group for group presentations.

Final assignment: Interpreting and reporting QIIME 2 results
------------------------------------------------------------

This assignment continues on from *Assignment 5*. For this assignment you will turn in a 2.5 to 3 page paper as a PDF. Details on the format are provided in the Assignment 5 Jupyer Notebook.

.. important::
	Homework id: ``final``; Extension: ``pdf``; For this assignment, the file I turn in would be named ``jgc53_final.pdf``.
