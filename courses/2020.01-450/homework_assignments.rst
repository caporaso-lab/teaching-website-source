==========================================================================================
Homework assignments
==========================================================================================

.. important:: I encourage you to discuss homework assignments with each other, but you may not view other student's assignments or share your assignment with others.

Homework assignments will be listed here as they are assigned.

Turning in your homework by email
---------------------------------

Your homework must always be turned in with a standardized name. That name should be ``<nau_id>-<homework_id>.<extension>``, where ``<nau_id>`` is your NAU identifier (for example, mine is ``jgc53``), and ``<homework_id>`` and ``<extension>`` are provided on a per-assignment basis. **Assignments that are not turned in according to these specifications will lose 10%.**

Unless otherwise noted, homework must be turned in by email to Greg (greg.caporaso@nau.edu) before class on the day it is due.

Assignment 1: GC content (see schedule for due date, 20 points)
---------------------------------------------------------------
Download a genome and compute its GC content. Copy or download `the assignment template <https://docs.google.com/document/d/1iY1sfH9uKulmO0CLugtQOzBoAIGqh0oIwzZfa1ARay0/edit?usp=sharing>`_, fill in your answers, and turn the assignment in by email as a PDF. **While you will get started on this assignment in class (optionally in small groups), you will complete the questions in assignment yourself.**

Note that there are various ways that you can just look up the GC content, including via the IMG website. I'm asking you to compute it, and you're being graded on your descriptions. Getting the right answer is a bonus (i.e., if you spend a couple of hours trying, and get it wrong, you'll be graded on your well-documented effort, not your final answer).

Hints: Start with the `NCBI Genome Browser <http://www.ncbi.nlm.nih.gov/genome>`_, and work with a bacterial, archaeal or viral genome. You can also work with a eukaryote genome, but it may be quite a bit more challenging.

Be creative - there are many ways to achieve this.

.. important::
	Homework id: ``gc-content``; Extension: ``pdf``; For this first assignment, the file I turn in would be named ``jgc53-gc-content.pdf``.

Assignment 2: BLAST exercises (see schedule for due date, 20 points)
--------------------------------------------------------------------

Using `NCBI nucleotide BLAST <http://blast.ncbi.nlm.nih.gov/Blast.cgi?PROGRAM=blastn&BLAST_PROGRAMS=megaBlast&PAGE_TYPE=BlastSearch&SHOW_DEFAULTS=on&LINK_LOC=blasthome>`_, complete the `assignment worksheet <https://docs.google.com/document/d/1d2A6KImyXKtIksKT2TAvwuBofQ7QcOqsNLHsH_4U38k/edit?usp=sharing>`_. You should turn in a PDF of that file with all answers filled in by email.

.. important::
  Homework id: ``blast``; Extension: ``pdf``; For this assignment, the file I turn in would be named ``jgc53-blast.pdf``.

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
		>Sequence5
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

Assignment 3: Python programming (see schedule for due date, 20 points)
-----------------------------------------------------------------------

In this assignment you'll apply some of the topics we covered in our Python programming lectures to write a Python script that can help you clean up information in a microbiome sample metadata file. The sample metadata that you'll work with here is from the Yellowstone Hot Springs study that Dr. Caporaso covered in class, and you'll modify a few functions in a template script to help standardize values in this file for use in microbiome analysis.

You can begin by downloading the `template script <https://www.dropbox.com/s/imi5b9m3aalauvl/fix_table.py?dl=0>`_, `a test script <https://www.dropbox.com/s/qi4p4btf2fa2b0y/test_fix_table.py?dl=0>`_, and `the input file <https://www.dropbox.com/s/yq12tfbbjhg5ogh/yellowstone.csv?dl=0>`_. You'll then upload these to the class Jupyter Notebook server, which you can access `here <https://ondemand.hpc.nau.edu/>`_.

After uploading these files, you should be able to run the following command::

		python test_fix_table.py

This is a test file that evaluates the accuracy of the functions that you've written by providing them with specific input, and then comparing their output to an expected result. It should report 16 failures, and you can use this to test whether your code is working correctly. You can run this as you make edits to the template script. When there are zero failures, you'll know that you have completely the assignment correctly.

Your code will do a few things. Acting only on the `Site` column in the table, it will remove leading and trailing whitespace, and convert the value to lowercase. Acting on the temperature column, it will remove units if they are present (this will be either `F` or `f`, for Fahrenheit), and convert the temperature value from Fahrenheit to Celsius. And finally, it will remove any rows that start with a `#` character, as these are often interpreted as comment lines that do not contain data. To achieve this, open the `fix_table.py` script and begin reading the comments to see what code you'll need to edit. All of your edits will be in the `fix_table.py` file.

You can apply your script to the input file as follows to created a new, cleaned up sample metadata file::

		python fix_table.py yellowstone.csv yellowstone-clean.csv

(You can name the output file whatever you'd like  - here I named it `yellowstone-clean.csv`.)


.. important:: To submit this assignment, after you have completed your code and tested it, rename your script to include your NAU id in the name, so the file name looks like: `fix-table-<nau-id>.py`, where `<nau-id>` is replaced with your NAU id. For example, my file would be named `fix-table-jgc53.py`. Email this file to Dr. Caporaso (greg.caporaso@nau.edu) with the subject line: Assignment 3.

Assignment 4: Primer analysis using Jupyter Notebooks
-----------------------------------------------------

In this assignment you'll use the Jupyter Notebook on monsoon to analyze 16S rRNA PCR primers. You'll work on the monsoon supercomputer for this assignment. Begin by creating a new directory to work in and uploading the following two files: `assignment4.py <https://www.dropbox.com/s/t9s36b8n2tv3928/assignment4.py?dl=0>`_ and `assignment4.ipynb <https://www.dropbox.com/s/q5hwc5dbqctp6hg/assignment4.ipynb?dl=0>`_. You will answer the questions in `this Google Doc <https://docs.google.com/document/d/e/2PACX-1vQKIoCNjQHrs53yiiqNmlW807o1M6JzjONFFtyafyPUvdukBXZNiO3Om0M_g6DEcBsAKRHyWdUmRa3s/pub>`_. **You will not need to open or edit the `assignment4.py` file.** You will edit the `assignment4.ipynb` file to show your work and experiment with the functions that you'll use for this assignment. You will create a copy of the Google Doc, answer the questions in there, and then submit that as a PDF.

.. important:: To submit this assignment, after you have completed your work in the Jupyter Noteboook (`.ipynb` file), rename it to include your NAU id in the name, so the file name looks like: `assignment4-<nau-id>.ipynb`, where `<nau-id>` is replaced with your NAU id. For example, my file would be named `assignment4-jgc53.ipynb`. You will also turn in the answers to your question as a PDF, based on the template in the Google Doc. This file should be named `assignment4-<nau-id>.pdf`, where `<nau-id>` is replaced with your NAU id. For example, my file would be named `assignment4-jgc53.pdf`. Email these two files to Dr. Caporaso (greg.caporaso@nau.edu) with the subject line: Assignment 4.
