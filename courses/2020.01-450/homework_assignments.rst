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

In this assignment you'll use the Jupyter Notebook on monsoon to analyze 16S rRNA PCR primers. You'll work on the `class Jupyter Notebook server for this assignment <https://ondemand.hpc.nau.edu/>`_. Begin by creating a new directory to work in and uploading the following two files: `assignment4.py <https://www.dropbox.com/s/t9s36b8n2tv3928/assignment4.py?dl=0>`_ and `assignment4.ipynb <https://www.dropbox.com/s/q5hwc5dbqctp6hg/assignment4.ipynb?dl=0>`_. You will answer the questions in `this Google Doc <https://docs.google.com/document/d/1GV9Hyp4SlrqKqWbYcQHMo0h52M6vLBRGWUWpzNxqies/edit?usp=sharing>`_. **You will not need to open or edit the `assignment4.py` file.** You will edit the `assignment4.ipynb` file to show your work and experiment with the functions that you'll use for this assignment. You will create a copy of the Google Doc, answer the questions in there, and then submit that as a PDF.

.. important:: To submit this assignment, after you have completed your work in the Jupyter Noteboook (`.ipynb` file), rename it to include your NAU id in the name, so the file name looks like: `assignment4-<nau-id>.ipynb`, where `<nau-id>` is replaced with your NAU id. For example, my file would be named `assignment4-jgc53.ipynb`. You will also turn in the answers to your question as a PDF, based on the template in the Google Doc. This file should be named `assignment4-<nau-id>.pdf`, where `<nau-id>` is replaced with your NAU id. For example, my file would be named `assignment4-jgc53.pdf`. Email these two files to Dr. Caporaso (greg.caporaso@nau.edu) with the subject line: Assignment 4.

Assignment 5: Learning and presenting on a bioinformatics workflow
------------------------------------------------------------------

In assignment 5 you will learn about and present on a bioinformatics workflow that is being used or proposed for SARS-CoV-2 research. This is a very real world bioinformatics task. In fact, I'm doing this very same thing at the moment as `we develop our capacity for sequencing and analyzing genomes from covid-19 cases in Arizona <https://azdailysun.com/news/local/tgen-diversifying-covid-19-testing-and-research/article_df3d2fb2-7540-5774-9ab0-a92cc481d786.html>`_ at the Pathogen and Microbiome Institute. 

You can do this in groups of up to three students, or work on this on your own. If you would like to create your own group or work on your own, please e-mail me with the full names of everyone in your group or to let me know that you want to work on your own by Tuesday, April 7th at 12:30pm. If I don't hear from you by then, I will randomly assign you to a group by 5pm on Tuesday, April 7th. Any of these three options (working on your own, creating your own group, or being assigned to a group) are totally fine - given the current challenges that everyone is facing, I just want to make sure that you have the flexibility to choose whichever option works best for you. 

For this assignment, you will turn in a video file in mp4 format by uploading it to `this Google Drive folder <https://drive.google.com/drive/folders/1_0LgXLUqAl1o9J6_kyo5ZBbFQD9CQ4LC?usp=sharing>`_. Each member of the group must contribute to the project in some way. This can be by doing research and writing a script for the video, presenting in the video, installing and demonstrating a workflow, or in some other way. 

Choose one of the Bioinformatic Tools, Scripts or Workflows described in `this document provided by the CDC <https://github.com/CDCgov/SARS-CoV-2_Sequencing#bioinformatic-tools-scripts-and-workflows>`_ (choose something outside of the "0. General Resources" section). (Alternatively, if there is another bioinforamtics tool/script/workflow that you're interested in learning about, and which is or could be related to SARS-CoV-2 research, email me to see if it would be a good subject for this presentation.) Present the tool/script/workflow of your choice in a video that is between 8-12 minutes long. Your presentation should address the following questions:

#. What organization or people are providing this tool/script/workflow?
#. Who provided the funding for this tool/script/workflow (try to determine this, but don't worry if you can't find it - it may not be reported)? 
#. What is the biological question that the tool/script/workflow is trying to address?
#. What is the motivation for addressing this question? (In other words, what could we learn by applying the tool/script/workflow?)
#. What computational technologies are used in this tool/script/workflow (e.g., bioinformatics software, programming language)?
#. What biological resources (e.g., public sequence databases) did the authors make use of?
#. What is the input to this tool/script/workflow?
#. What is the output from this tool/script/workflow?
#. Present either a demo of the tool/script/workflow (e.g., install it on your computer and run it with test data) or present an example of the output generated by this workflow and explain how to interpret it.

All students in a group will receive the same grade on this assignment unless there is clear evidence that some student(s) didn’t contribute, in which case the rest of the group should e-mail me to discuss the issue.

Before choosing a tool/script/workflow to present on, you should look at several in the list. Some of these have higher quality descriptions and examples than others. 


Final project: Microbiome-based forensics with QIIME 2
------------------------------------------------------

The final project is made up of three parts that you will work on in order. In this assignment, you'll be using `QIIME 2 <https://qiime2.org>`_ version 2020.2 to analyze two data sets. The objective of this assignment is to learn a bioinformatics tool from its documentation (Part 1), apply it to answer a specific question (Part 2), and report your findings (Part 3).  

In **Part 1**, you'll read and run the QIIME 2 `Moving Pictures of the Human Microbiome tutorial <https://docs.qiime2.org/2020.2/tutorials/moving-pictures/>`_, a tutorial that is designed to be a first entry point into the QIIME 2 microbiome bioinformatics platform. This will familiarize you with running QIIME 2 and interpreting QIIME 2 output. In **Part 2**, you'll adapt the commands from that tutorial to analyze another data set, where human-associated microbial communities were explored for their forensic potential. In **Part 3**, you'll interpret and write up your results from **Part 2** in a three-page report. Before starting this assignment, you should read `Fierer et al (2010) <http://www.pnas.org/content/early/2010/03/01/1000162107.full.pdf>`_, where this forensic study was initially published. This will help you understand the study.

**IMPORTANT**: This assignment includes some steps that will take time to run (possibly up to 20 minutes). You should avoid starting this assignment close to the deadline - if the server is backlogged because many people are using it, it may take time for your notebook server to be accessible. You are responsible for starting this in a timely manner!

For **Part 1**, you will run analyses in the Jupyter Notebook provided `here  <https://www.dropbox.com/s/igtz8go7gwaxg2j/qiime2-assignment-part1.ipynb?dl=0>`_. Note: Due to a configuration error on the server, at the `Sequence Quality Control ... step <https://docs.qiime2.org/2020.2/tutorials/moving-pictures/#sequence-quality-control-and-feature-table-construction>`_, use Option 2 (deblur).

For **Part 2**, you will run analyses in the Jupyter Notebook provided `here <https://www.dropbox.com/s/uw7782lpotoc915/qiime2-assignment-part2.ipynb?dl=0>`_, and answer the questions posted `here <https://docs.google.com/document/d/1hhoRNohnCWtfE_z_cVb3Zti5BLf1mOzSQoNiY4wZjWw/edit?usp=sharing>`_. 

For **Part 3**, you will write a 2.5 to 3 page paper describing your analysis (details are provided below).

Download each of the notebooks from the links provided above. Log into the class Jupyter Notebook server, and create two new folders: one for assignment part 1, and one for assignment part 2. Upload each of the notebooks to it's corresponding folder. (Creating these folders is important - otherwise it'll be very easy to mix up the files from these two parts, which will lead to all sorts of confusing error messages.) Each notebook contains empty cells for you to work in.

Items to turn in by email
+++++++++++++++++++++++++

For **Part 1**, you'll turn in the notebook containing the commands that you ran. Append your NAU ID to the beginning of the file name. For example, the file I turn in would be named `jgc53-qiime2-assignment-part1.ipynb`.

For **Part 2**, you'll turn in the notebook containing the commands that you ran, as well as a completed question sheet (linked above), and the `.qza` or `.qzv` files that you reference in your answers in the question sheet (with the exception of any `.qza` or `.qzv` files that I'm providing for you). Append your NAU ID to the beginning of each file name. For example, the files I turn in would be named: `jgc53-qiime2-assignment-part2.ipynb`, `jgc53-qiime2-assignment-part2-questions.pdf`, and multiple files with names like `jgc53-*.qzv` (where the `*` is replaced with a descriptive name for each file, such as `jgc53-taxonomy-barplot.qzv`). Don't try to submit artifacts that I've provided for you, such as `gg-13-8-99-nb-classifier.qza`. Some will be too large to send by email, and I already have them.

For **Part 3**, you will write a 2.5 to 3 page paper describing your analysis. **Your paper should not be any shorter than 2.5 pages nor any longer than 3 pages. It must have 1.5 line spacing, 0.5" margins, and be written in 12 point Times New Roman font. Figures and tables are included in the page count, though the total space taken by these should be a maximum of one page.**

Write this as if you’re submitting to a journal, so your paper should contain:

* A title and list of authors (just you, in this case). This should be in no more than 14 point font, and follow the margin/spacing requirements listed above.
* An *Introduction* section describing the goals of the study (you can refer to `Fierer et al (2010) <http://www.pnas.org/content/early/2010/03/01/1000162107.full.pdf>`_);
* A *Methods* section containing a brief description of your bioinformatics methods (e.g., what version of QIIME, what commands were used), and how the data was generated (e.g., sequencing platform);
* And a *Results and Conclusions* section describing the results of your analysis. 

You should address several specific questions in your *Results and Conclusions*:

* Which keyboard belonged to each of the human subjects? Back this up with figures and statistics that support your answer. Describe what each of your figures tells you.
* Which bacterial phyla appear to be most useful for matching each individual to their keyboard? Refer to *Taxonomic barplots* to address this.
* Which features were most different in abundance across the subjects? Refer to the *Taxonomic barplots* to address this. Present a table containing the most differentially abundant features and their taxonomy. 
* Which subject had the most features (i.e., the highest microbial community richness) in their skin microbiome, on average? Was the number of features across subjects significantly different? 

Please turn all of this in by e-mail to greg.caporaso@nau.edu with subject: _final assignment_.

Troubleshooting
+++++++++++++++

* If you receive a `SyntaxError`, confirm that you're using the Bash kernel, as instructed at the top of both notebooks.
* If you receive an error `Plugin error from dada2`, switch to using Option 2 (deblur) at the `Sequence Quality Control ... step <https://docs.qiime2.org/2020.2/tutorials/moving-pictures/#sequence-quality-control-and-feature-table-construction>`_ in Part 1.
* If one of your commands fails with the message `Killed!`, save your work and start a new server with 8000 MB of memory (8GB). See Dr. Caporaso's video for for details.
* Be sure that each of your notebooks is running in it's own folder. 

