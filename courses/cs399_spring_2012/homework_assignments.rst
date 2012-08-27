==========================================================================================
Homework assignments
==========================================================================================

Group Project: Final paper Due 1 May 2012 (45 points)
=====================================================

Write a five page paper presenting the goals of your project, your methods, your results, and your conclusions. This can incorporate text from your previous papers (specifically, your experimental design) if it's relevant. This should contain all of the results necessary to support your conclusions, and only those results. Be concise but thorough. Data generated from all three data sets should be included, including 2-3 display items (i.e., tables and figures) that illustrate your results.

To turn in by email:

 * Five page paper outlining your experimental design. The file should be named ``groupN_paper3.pdf`` where ``N`` refers to your group number. One member of the team should e-mail this to me by 8am on Tuesday May 1st with the subject ``Group N final paper`` where ``N`` refers to your group number.

 * You will grade all members of your team. You have 100 points to divide between all four team members. Give every team member a score, including your self. If the effort is balanced, the scores will be around Cosmo 25/Jerry 25/George 25/Elaine 25. If two team members did the vast majority of the work, the scores might look like Cosmo 40/Jerry 10/George 10/Elaine 40. Include up to a 4 sentence description of why you graded the team the way you did. You should e-mail this to me by 5pm on Tuesday May 1st with the subject ``Group N evaluation`` where ``N`` refers to your group number. I'm giving you until the end of the day in case there are any last minute issues you want to report on.

To post to the ``cs399-project-data`` S3 bucket:

 * A single zip file containing all data and code that was generated in this project, including notes files containing the exact series of commands that were run for the different analyses. The notes file should be in the top-level directory, and be called ``notes.txt``. The zip file should be called ``groupN_final_data.zip``, where ``N`` is your group number.

Group Presentation 2:  Final results: 26 May 2012 in class (10% of final grade!)
================================================================================================================

This presentation will be an oral version of your final paper. Describe the question you addressed, your methods, your results, and you conclusions with respect to the initial question. This is worth a lot, so spend a lot of time preparing, and plan to practice it at least 3 times before you present. All members of the team must give part of the presentation. Look and act professional!

This presentation should be 15 minutes long, plus a 5 minute question/answer period (don't go over time!).


Group Project 3: Progress report Due 19 Apr 2012 (25 points)
============================================================

Write a three page paper outlining your progress to date. Briefly describe the question your addressing and your experimental design (one - two paragraphs, less than one page). Then describe where you are in the analysis, challenges that you've run into, and how you overcame (or plan to overcome) those challenges. Describe your expected results on the basis of your preliminary analyses: do the preliminary results (e.g., on one of the three data sets) support your initial intuition about how the results might look? Include one or two display items (tables or figures) that illustrate your preliminary results.

The file should be named ``groupN_paper2.pdf`` where ``N`` refers to your group number. One member of the team should e-mail this to me by 8am on Thursday April 19th with the subject ``Group N paper 2`` where ``N`` refers to your group number.

Report on Sahl Lecture: Due 20 Mar 2012 (10 points)
===================================================
Write one page describing Dr. Sahl's lecture. What are the question(s) he's interested in addressing; what techniques is he using; what are his primary conclusions? I highly recommend writing this before you leave on Spring Break while it's fresh in your mind! E-mail this to me by 8am on 20 Mar 2012 with the subject: ``Sahl lecture report``.

Group Presentation 1:  Outline experimental design for group project: 22 Mar 2012 in class (10% of final grade!)
================================================================================================================

This presentation will be an oral version of your Group Project 2 paper. Describe the question you're addressing, the results you might expect to see, and how you will address that question. This should include your plan for division of labor, what resources you'll use, etc. This is worth a lot, so spend a lot of time preparing, and plan to practice it at least 3 times before you present. All members of the team must give part of the presentation. Look and act professional! Preliminary data is encouraged.

This presentation should be 15 minutes long, plus a 5 minute question/answer period (don't go over time!).

Group Project 2: Outline experimental design for group project: Due 8 Mar 2012 (35 points)
==========================================================================================

This project will form the basis of your presentation on March 22nd.

As a group you will design a bioinformatics experiment to address one of three questions. You will make use of the three data sets used for Group Project 1, so familiarize yourself with each of those data sets.

To turn in by email:

 * Three page paper outlining your experimental design. Describe the question you're addressing, the results you might expect to see, and how you will address that question. In this document you should have a plan for dividing up labor, and resources that you'll use. This document should include one display item: a flow chart that can take up to one page (included in your page limit) showing an overview of the tasks and dependencies involved in the project, with one or more names assigned to each task. The file should be named ``groupN_paper1.pdf`` where ``N`` refers to your group number. One member of the team should e-mail this to me by 8am on Thursday March 8th with the subject ``Group N project 2 paper`` where ``N`` refers to your group number.

 * You will grade all members of your team. You have 100 points to divide between all four team members. Give every team member a score, including your self. If the effort is balanced, the scores will be around Cosmo 25/Jerry 25/George 25/Elaine 25. If two team members did the vast majority of the work, the scores might look like Cosmo 40/Jerry 10/George 10/Elaine 40. Include up to a 4 sentence description of why you graded the team the way you did. You should e-mail this to me by 5pm on Thursday March 8th with the subject ``Group N evaluation`` where ``N`` refers to your group number. I'm giving you until the end of the day in case there are any last minute issues you want to report on. 

To complete on the web:

 * Fill in the doodle poll `here <http://www.doodle.com/znddpba8gksdb74s>`_ to let me know all times that all members of your group can meet in Dr. Caporaso's office. In this meeting we will discuss your presentation, and will review and modify your project outline and division of labor.

Group Project descriptions
==========================

**If you have questions about your project, see me in office hours the week of Feb 27th! I will be traveling March 3-17th, so email contact will be slow.**

Team 1 Project
--------------
You will investigate the effect of sequence read length on microbial community alpha diversity results, beta diversity results, and OTU category significance results. Specifically we want to know how starting with different read lengths might effect the biological conclusions that a researcher might draw from their data. Given the three data sets from Group Project 1, you will compare all of the above results with reads sliced to 100%, 75%, 50%, 25% of full read length. This will require trimming of the initial reads.

Team 2 Project
--------------
You will compare the QIIME 1.4.0 and mothur 1.23.1 software packages, and report on the usability, run time, and consistency of results between the two. You should have both installed on the same AWS EC2 image (you'll need to create one - I recommend starting from the QIIME 1.4.0 image, installing mothur, and saving as a new image). Here we are interested in consistency of alpha and beta diversity results across the two systems, run times for all steps in the pipeline from OTU picking through diversity analyses, and a discussion of the pros and cons in terms of usability for each (I want an honest assessment here - don't be biased by the fact that I'm a developer on QIIME!). You will analyze all three data sets from Group Project 1. 

Team 3 Project
--------------
You will compare the effect of the choice of reference set and OTU picking threshold in closed-reference OTU picking on microbial community alpha diversity results, beta diversity results, and OTU category significance results. Here we are interested in which methods are best for identifying results of interest in alpha diversity, beta diversity, and otu category significance tests. The reference collections you'll use are available `here <http://greengenes.lbl.gov/Download/Sequence_Data/Fasta_data_files/Caporaso_Reference_OTUs/gg_otus_4feb2011.tgz>`_. You will run all analyses of all three data sets from Group Project 1. The specific combinations you'll use are:
 * picking 99% OTUs against the 99% reference set; 
 * picking 97% OTUs against the 97% reference set; 
 * picking 97% OTUs against the 99% reference set; 
 * picking 94% OTUs against the 97% reference set; 
 * picking 94% OTUs against the 94% reference set. 




PyUnit Homework: Test buggy_translate.py: Due 23 Feb 2012 (25 points)
=====================================================================

For this assignment you will write unit tests for the ``buggy_translate.py`` script. There are (at least) 3 bugs in this code, and you will identify those bugs using unit tests and turn in your test code and a brief write up of your results.

Download :download:`this file <./pyunit.tgz>` to get started. You'll find the ``buggy_translate.py`` file in that directory as well as a template for the unit tests that you should use for your assignment. 

These are the specifications for the function. 
 - Given a DNA sequence, the ``buggy_translate`` function should return amino acid sequence between the start codon (``ATG``) and any of the three standard (i.e., `human nuclear genetic code <http://plato.stanford.edu/entries/information-biological/GeneticCode.png>`_) stop codons.
 - If an invalid character is detected in the input sequence a ValueError should be raised. 
 - If no start codon is detected an empty string should be returned. 
 - No character should be returned in place of the stop codon - the sequence should terminate at the first detected stop codon.
 - If no stop codon is found, the translated sequence should be returned for the start codon through the end of the input sequence.

Example usage::
	
	import buggy_translate
	buggy_translate.buggy_translate('AAACGGATGACCTACCTATGACCA')
	'MTYL'

To turn in by email (before class!):
 - Your unit test file. It should be named ``test_buggy_translate_<userid>.py``.
 - One paragraph (each) describing a bug you found in ``buggy_translate.py``. Include a description of what the buggy output is, what the output should be, and the test you wrote that allowed you to determine that there was a bug in the code. Include the name of the test function(s) that allowed you to detect each bug. There should be at least 3 paragraphs here, and this document should not be longer than one page. This file should be turned in as a PDF, and named ``buggy_translate_<userid>.pdf``.
 - The subject of this email must be ``<userid> PyUnit Homework``.

In all cases, ``<userid>`` should be replaced by your NAU user id. For example, my test file would be named ``test_buggy_translate_jgc53.py``. **Name your files exactly as described here!**

Group Project 1: QIIME data analysis and write-up: Due 14 Feb 2012 (35 points)
===============================================================================

Group 1: English Channel (454, 16S V6)

Group 2: Guerrero Negro (Sanger, full length 16S)

Group 3: Host-associated, free-living, and artificial communities (Illumina GAIIx, 16S V4). See `notes on picking OTUs on Illumina data <http://qiime.org/svn_documentation/tutorials/processing_illumina_data.html#using-illumina-data-in-downstream-analysis>`_. You'll want to use an 8 processor AWS instance and run this command on all eight processors.

All data sets are available in the ``cs399-project-data`` S3 bucket. These are not all publicly available - `do not make them public!`. 

You will run a complete QIIME analysis, generating alpha rarefaction plots (``alpha_rarefaction.py``), beta diversity plots (``beta_diversity_through_plots.py``, be sure to run this with even sampling!), and an OTU category significance (``otu_category_significance.py``) table.

To turn in:
 * All output from this analysis in a single zip file. Your zip file should be named ``groupN_project1.zip`` where ``N`` is replaced with your project number.
 * Paper describing the background of the study (where did this data come from, why is it interesting?), your bioinformatics methods, and your bioinformatics results (i.e., your conclusions from the analyses described above). This should be between 2 and 3 pages. Write this as if you're presenting it to someone outside the class, so include information on the QIIME version that you used, etc.  Your paper should be in PDF format, and be placed in the zip file named ``groupN_paper1.pdf`` where ``N`` is replaced with your project number. Your paper should include two figures, one illustrating your beta diversity conclusions (PCoA screenshot is good) and one illustrating the alpha diversity conclusions (rarefaction plot screenshot), and one table containing the 10 most significant OTUs that discriminate samples from the metadata category of interest. Be sure that these figures support your conclusions, and discuss them in this section! Each Figure and Table should take up approximately 1/4 of a page, and do count toward your page limit. Format this nicely!
 * Document listing all of your commands. This should be in the zip file and be named ``groupN_analysis_notes.txt`` where ``N`` is replaced with your project number. Don't include commands that failed - only the ones that contributed to your data. 

Your assignment results, including the paper, will be visible by everyone in the class, and everyone will ultimately be assigned to read the reports generated by the other groups as we'll all be working with this data through the rest of the semester. Your grade *will not* be available to the rest of the class.

I will be grading you on the quality of your results, the comprehensiveness of your notes (could I reproduce the results from what you've given me), and the quality of your paper. The quality of your paper includes writing style, spelling errors, grammatical errors, typos, and formatting.

Divide the labor, but be sure that everyone understands all components of the project. You will be expected to understand both the bioinformatics, the analysis steps, and the biology for your quizzes and exams. I suggest working on all pieces of the project in groups.


QIIME tutorial on Fierer et al data: Due 2 Feb 2012 (25 points)
===============================================================

For this assignment you will use the 1.4.0-dev version of QIIME (AMI: ``ami-792bfd10``).

To update the latest version of QIIME you should run the following commands after booting and logging in to your instance::
	
	cd /software/app-deploy-qiime-1.4.0-repository/
	python app-deploy.py /software/ -f etc/qiime_1.4.0_repository.conf --force-remove-failed-dirs --force-remove-previous-repos
	cd

You should have already read the `Fierer et al paper <http://www.pnas.org/content/107/14/6477.long>`_ (due 31 Jan 2012) before beginning this assignment.

Data analysis: You will perform a complete QIIME analysis of the data set presented in Fierer et al, and turn in the following items:
 - evenly sampled OTU table (generated by `beta_diversity_through_3d_plots.py`)
 - PDF or PNG showing a single view of the unweighted unifrac 3d PCoA plot that you find informative (i.e., it should illustrate the conclusions presented in the Fierer et al paper)
 - text file containing the full list of commands that you ran to generate the above data, noting any problems that you ran into along the way

The following commands will get you started. Run these after logging in to your AWS instance.
::
	
	# download the Fierer data
	wget https://s3.amazonaws.com/s3-public_ssu_data/fierer_forensic_keyboard.tgz
	
	# unpack the tgz file and change to the resulting directory
	tar -xvzf fierer_forensic_keyboard.tgz
	cd fierer_forensic_keyboard
	
	# unpack the sff file and the mapping file
	tar -xvzf study_232_FFCKVMW.sff.tgz
	unzip study_232_run_FFCKVMW_mapping.txt.zip
	
	# generate .fna and .qual files from the sff file
	process_sff.py -i ./

Hints:
 - From here you'll probably want to follow the steps in the `QIIME overview tutorial <http://qiime.org/svn_documentation/tutorials/tutorial.html>`_, but modified to use the data from the Fierer et al study. You may want to run that tutorial as-is first, to familiarize yourself with the steps.
 - Remember that the ``screen`` command will be important to allow your analyses to continue running if your network connection is interrupted. You can find `details on screen here <http://www.ibm.com/developerworks/aix/library/au-gnu_screen/>`_.

Turn your results in by email (gregcaporaso@gmail.com) before class on 2 Feb 2012. Name your files as follows::

	- <userid>_otu_table_even.biom
	- <userid>_unweighted_unifrac_pcoa.png or <userid>_unweighted_unifrac_pcoa.pdf
	- <userid>_analysis_notes.txt

In all cases, ``<userid>`` should be replaced by your NAU user id. For example, my OTU table would be named ``jgc53__otu_table_even.biom``. **Name you files exactly as described here!**

.. warning:: I modified the name of the first output file on 26 Jan 2012. This should now end with ``.biom`` rather than ``.txt``.


Administrative tasks (5 points): Due 19 Jan 2011
================================================

| Fill in the Office Hours poll `here <http://www.doodle.com/q7a7mcnbrc7yf44t>`_ to have your say at when I'll hold my office hours. IMPORTANT: Don't pay attention to the specific dates in the poll: just pay attention to the days.
|
| E-mail me at gregcaporaso@gmail.com with the following subject line to be added to my course mailing list: 
|     CS 399 mailing list: ``email-address``
| where ``email-address`` is replaced with the email address you'd like messages to go to. You are expected to check this e-mail at least once per day for important announcements.