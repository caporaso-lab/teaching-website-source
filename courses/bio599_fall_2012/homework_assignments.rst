==========================================================================================
Homework assignments
==========================================================================================

.. important:: I encourage you to discuss homework assignments with each other, but you may not view other student's assignments or share your assignment with others. When you start programming, you often think there is a single way to address a task, but that is usually not the case: there are many ways to complete these assignments, and when code has been shared or copied it is often very obvious to a more experienced eye.

Turning in your homework by email
---------------------------------
Your homework must always be turned in with a standardized name. That name should be ``<nau_id>_<homework_id>.<extension>``, where ``<nau_id>`` is your NAU identifier (for example, mine is ``jgc53``), and ``<homework_id>`` and ``<extension>`` are provided on a per-assignment basis. 

Unless otherwise noted, homework must be turned in by email to alk224@nau.edu before class on the day it is due. 

Turning in your homework via the cluster
----------------------------------------
You can also turn in your programming assignments by placing them in a specific location on the cluster. If your assignment file is called ``jgc53_translate.py`` you could do this as follows::
	
	chmod o-rwx jgc53_translate.py
	cp jgc53_translate.py /mnt/assignments/translate/

Note that the directory that you're turning your files in to will always be ``/mnt/assignments/<homework_id>/``, where ``<homework_id>`` is replaced with the current ``homework_id``. You should ``cp``, not ``mv``, the file so you retain a backup of it (and on that note, also remember to copy the file to your local hard drive as a backup).

Accessing the cluster
---------------------
For the remaining assignments this semester we'll use an Amazon Cloud based cluster. You should have received a key file (``<nau-id>.rsa``) and ip address by email. (I won't post the ip address here for security reasons.) Use the key file and the ip address to connect as follows::

	ssh -i <key-file> <nau-id>@<ip-address>

For example, I would connect as follows::

	ssh -i jgc53.rsa jgc53@<ip-address>

Where ``<ip-address>`` is replaced with the IP address that was provided by email.

To move files in and out of the instance, I recommend using `Cyberduck <http://www.cyberduck.ch>`_. You can find `instructions for connecting to AWS with Cyberduck here <http://qiime.org/tutorials/working_with_aws.html#working-with-cyberduck>`_. Instead of the public DNS entry, you'll use the IP address referenced above. You can also experiment with `command line tools to move data in and out of the cluster <http://qiime.org/tutorials/working_with_aws.html#working-with-command-line-tools>`_. 

Final project (13 Dec 2012 9:30am)
----------------------------------

You will have two options for the final project: one performing a QIIME meta-analysis, and one writing a python program. You will turn in only one of these assignments.

Final project: QIIME Database meta-analysis
-------------------------------------------

.. warning:: Start Early! The QIIME DB uses a shared server for this analysis, and you never know how busy it will be.

For this assignment you will perform a meta-analysis of several microbial surveys of the indoor environment. To get more details on microbiology of the built environment, check out `microBEnet <http://www.microbe.net/>`_. You will use the QIIME Database to perform this meta-analysis - you'll export several initial results from the QIIME DB, including a combined OTU table, and taxonomy survey and beta diversity results. You'll download these data either to the class cluster or your own computer to perform some more in-depth analyses.

Follow these steps to perform the QIIME meta-analysis:

1. Create an account with the `QIIME Database <http://www.microbio.me/qiime>`_.
2. On logging in, choose 'Create a New Meta-Analysis'. Name your meta-analysis and hit 'Next'. Click 'Perform Meta-analysis'
3. Next, you'll choose the studies you want to include. Choose ``Kelley_office_contamination`` (`cite <http://www.plosone.org/article/info%3Adoi%2F10.1371%2Fjournal.pone.0037849>`_), ``Flores_restroom_surface_biogeography`` (`cite <http://www.plosone.org/article/info%3Adoi%2F10.1371%2Fjournal.pone.0028132>`_), and ``CaporasoIlluminaPNAS2011_5prime`` (`cite <http://www.pnas.org/content/108/suppl.1/4516.long>`_). Then do the following: uncheck "Show Common Fields Only"; Select Metadata Fields: "All"; Hit '>>' to copy all metadata fields to your mapping file; Hit "Continue".
4. Select "Processing Method: Serial"; Check "Taxonomy Summary"", then expand "Optional parameters (sort_otu_table.py), and set "Category to sory by" to STUDY_TITLE; Check "Beta-Diversity", expand "Optional Parameters (rarefaction.py), and set "Rarified at" to 500 seqs/sample, then expand "Optional Parameters (beta_diversity.py), and set "Metrics to use" to bray_curtis, weighted_unifrac, unweighted_unifrac, euclidean; choose 3d PCOA plots (no optional parameters). Click "Submit".
5. This may take a while to run. When it's done, you can begin to explore the results via the database website. Download the "Zip Archive" to address the questions below.

You will turn in an approximately three page paper describing your analysis, including a brief introduction (describe what specific types of samples are under investigation here as well as some background on the studies the initial studies they were derived from), description of your methods, and description of your results. Focus your results on the following questions:

Do the four distance metrics you applied result in statistically similar PCoA plots? Present a distance matrix of Procrustes M^2 values between four the principal coordinate matrices generated by the QIIME DB (``*_pc.txt``) as a table in your paper and discuss your conclusions from this analysis.

What does the clustering pattern in your unweighted UniFrac PCoA plot tell you about the likely sources of each of the indoor microbial communities (as judged by the similar of the indoor communities to the diverse set of samples in the ``CaporasoIlluminaPNAS2011_5prime`` study)? Include the most informative view of your PCoA, with a color legend, in your paper to support this analysis.


.. note::
	See the Procrustes tutorial `here <http://qiime.org/tutorials/procrustes_analysis.html#performing-procrustes-analysis>`_. Since your principal coordinate matrices were already generated for you by the QIIME DB, you'll pick up the tutorial with ``transform_coordinate_matrices.py``. Do some research on Procrustes analysis to learn how to interpret these plots.

.. note::
	UniFrac clustering analysis: modifying the mapping file (e.g., in Excel) to create a single metadata column that is informative across all samples will help here. You would need to run make_3d_plots.py with your new mapping file to generate a new PCoA plot.


Final project: Building a tree of life (programming assignment)
------------------------------------------------------------------

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

.. important::
	Homework id: ``tol``; Extension: ``py``, ``tre`` and ``pdf``; For this assignment, the files I turn in would be named ``jgc53_tol.py``, ``jgc53_tol.tre`` and ``jgc53_tol.pdf``.

.. note::
	`This page <http://dl.dropbox.com/u/2868868/pycogent_160dev_docs/cookbook/building_a_tree_of_life.html>`_ should help quite a lot.

.. note:: 
	The cluster has PyCogent, muscle, and FastTree preinstalled. Working there will save you a lot of time on software installation.

.. note::
	Remember that you can call ``dir()`` on an object to find out what methods are available to that object. One of the methods associated with your tree object will help you generate a newick formatted tree.


Programming Assignment 3 (4 Dec 2012)
-------------------------------------

You will write a program that extracts latitude and longitude information from a `QIIME-compatible mapping file <http://qiime.org/documentation/file_formats.html#metadata-mapping-files>`_, and writes that to a `Keyhole Markup Language (kml) file <https://developers.google.com/kml/documentation/kml_tut>`_, which can be opened in `Google Earth <http://www.google.com/earth/index.html>`_. To achieve this you'll need to understand the QIIME mapping file format so you can parse it, the ``kml`` file format so you can write it, and the basics of file reading and writing in python so you can read the mapping file, process the input, and write the kml file.

Your script should take two command line arguments: the input mapping file, and the name of the output file to write. For example, I would call my script as follows::

	jgc53_coordinates.py glen_canyon_map.tsv jgc53_coordinates.kml

You can obtain the mapping file from `here <https://docs.google.com/spreadsheet/ccc?key=0AvglGXLayhG7dDNCWnUwSHhWNmxKODZISWx6VzBqU0E>`_ (choose 'File > Download as > Plain text' to save as tab-separated text). You can see an example of what the output file should look like `here <https://gist.github.com/4121975>`_.

.. important::
	Homework id: ``coordinates``; Extension: ``py`` and ``kml``; For this assignment, the files I turn in would be named ``jgc53_coordinates.py`` and ``jgc53_coordinates.kml``.

.. note::
	Be sure to download, install, and use `Google Earth <http://www.google.com/earth/index.html>`_ to confirm that your ``kml`` file is written correctly, and that the points end up in the right place (i.e, Utah).

.. note::
	You can copy some information from the `example output file <https://gist.github.com/4121975>`_ to generate the header and the footer information in your kml file. 

Programming Assignment 2 (15 Nov 2012)
--------------------------------------

Write a program that makes use of a ``for`` loop and a dictionary to translate an RNA sequence to a protein for all four orientations of the input sequence (forward, reverse, forward complement, reverse complement, where forward refers to the sequence that was passed in). This program should query a user for an input RNA sequence and print the translated protein sequences to the screen. If a stop codon is encountered in the RNA sequence, an ``*`` should be inserted in the translated sequence, and translation should continue. 

Assume that you will only receive IUPAC RNA bases (either upper or lower case) as input. In other words, you don't need to handle non-RNA characters in the input sequence. You can also assume that the length of an input sequence will be a multiple of three, so you only need to handle full-length codon sequences. 

.. important::
	Homework id: ``translate``; Extension: ``py``; For this assignment, the file I turn in would be named ``jgc53_translate.py``.


To get every third base, you can build a for loop that looks like the following. Use a variation on this to identify each codon::

	s = "ACCTTTAGGACCCGG"
	for e in range(0,len(s),3):
   		print s[e]

Example input 1::
	
	Enter a DNA sequence: 
	ACCGGGTTACCC

Example output 1::
	
	Forward orientation:
	TGLP
	Reverse orientation:
	PIGP
	Forward complement orientation:
	WPNG
	Reverse complement orientation:
	G*PG

.. note:: One step in this process is going to be building a dictionary where you can look up codons to get the amino acid that they code for (or the ``*`` in the case of stop codons). You should pull the genetic code off the web from somewhere, and refer to the `Generating dictionaries` section of Chapter 9 of `Practical Computing for Biologists`. You'll go back to your regular expressions for this process.

Programming Assignment 1 (8 Nov 2012)
-------------------------------------

Write a program that does the following:
 - query a user for an input sequence
 - print the sequence, all in uppercase, in four orientations (forward, reverse, forward complement, reverse complement), where forward refers to the sequence that was passed in.
 - print the GC content (percent of the sequence which is either G or C) of the forward orientation of the sequence
 - print the length of the sequence

.. note:: Complementing the sequence can be tricky with your current skill set. You may need to go through an intermediate state by replacing characters with some other character. There are many ways to do this and the goal here is to get the right answer. I don't care how you implement it.

.. note:: To reverse a string ``s``, you can use the command ``s_rev = s[::-1]`` We'll talk about this syntax within the next couple of weeks - for now, just treat this command as magic.

.. note:: To perform real division using integers, add the following line at the beginning of your file (just after the `shebang` line): ``from __future__ import division``

.. important::
	Homework id: ``sequence_stats``; Extension: ``py``; For this assignment, the file I turn in would be named ``jgc53_sequence_stats.py``. 


QIIME analysis (25 Oct 2012)
------------------------------

.. important:: This assignment involves large data files. You will need to work in your `scratch` directory, or you will run out of space. On logging into the cluster change to ``/mnt/<nau-id>`` where ``<nau-id>`` is your NAU identifier. For example, I would do this by running the command: ``cd /mnt/jgc53``.

.. important:: Remember that the ``screen`` command will be important to allow your analyses to continue running if your network connection is interrupted. You can find `details on screen here <http://www.ibm.com/developerworks/aix/library/au-gnu_screen/>`_.

.. important:: This assignment is designed to force you to use existing resources (internet, primary literature) to learn to use an existing bioinformatics tool to address a biological question. Because of the amount that you're expected to learn on your own, this homework will involve additional effort relative to the others so far this semester. **It will be a lot easier** if you begin by working through the `Illumina Overview Tutorial <http://qiime.org/svn_documentation/tutorials/illumina_overview_tutorial.html>`_, followed by the `QIIME Overview Tutorial <http://qiime.org/svn_documentation/tutorials/tutorial.html>`_.  There is no class on 16 October 2012: use that time to get started on this! 

Begin by reading `Fierer et al <http://www.pnas.org/content/107/14/6477.long>`_. You will use QIIME to reproduce the analyses presented in this paper.

Data analysis: You will perform a complete QIIME analysis of the data set presented in Fierer et al, and turn in the following items:
 - A 3 page (maximum!) paper describing your analysis. Write this as if you're submitting to a journal, so should contain an `Introduction` section describing the hypotheses being addressed and the strategy for addressing these (refer to `Fierer et al <http://www.pnas.org/content/107/14/6477.long>`_), a `Methods` section containing a brief description of your bioinformatics methods (e.g., what version of QIIME, what type of OTU picking was used) and how the data was generated (e.g., sequencing platform), and a `Results` section describing the results of your analysis. Your 2-3 pages should include a beta diversity PCoA plot (generated by `beta_diversity_through_plots.py <http://qiime.org/scripts/beta_diversity_through_plots.html>`_; focus on Unweighted UniFrac, which is what we discussed in class) in a view that supports your conclusions, and an alpha rarefaction plot (generated by `alpha_rarefaction.py <http://qiime.org/scripts/alpha_rarefaction.html>`_). You should also include a table that lists the five OTUs that are most significantly different across the `Subject` category in your mapping file (generated by `otu_category_significance.py <http://qiime.org/scripts/otu_category_significance.html>`_). Figures and tables should take up no more than one total page of your paper. This paper must be turned in as a PDF - ``.doc`` or other word processing formats will not be accepted.
 - Evenly sampled OTU table (generated by `beta_diversity_through_plots.py <http://qiime.org/scripts/beta_diversity_through_plots.html>`_). This should be provided as a gzipped `.biom` file.
 - Text file containing the full list of commands that you ran to generate the above data, noting any problems that you ran into along the way. 

The following commands will get you started. Run these after logging in to your cluster account.

::
	
	# CHANGE TO YOUR SCRATCH DIRECTORY (remember <nau-id> should be replaced by your NAU identifier)!!!
	cd /mnt/<nau-id>
	
	# download the Fierer data
	curl -O https://s3.amazonaws.com/s3-caporaso-share/fierer_forensic_keyboard_assignment.tgz > fierer_forensic_keyboard_assignment.tgz
	
	# unpack the tgz file and change to the resulting directory
	tar -xvzf fierer_forensic_keyboard_assignment.tgz
	cd fierer_forensic_keyboard_assignment
	
	# generate .fna and .qual files from the sff file
	process_sff.py -i ./

The steps in the `QIIME Overview Tutorial <http://qiime.org/svn_documentation/tutorials/tutorial.html>`_ are the next place to go from here... Good luck!

.. important::
	Homework id: ``qiime``; Extension: ``biom``, ``pdf``, and ``txt``; For this assignment, the files I turn in would be named <userid>_qiime_otu_table_even.biom, <userid>_qiime_paper.pdf and <userid>_qiime_analysis_notes.txt. 
	
	E-mail your files as three separate attachments to alk224@nau.edu.


Shell script (due 9 Oct 2012)
------------------------------

In this assignment you will automate retrieval and processing of PDB files with a shell (``bash``) script, and turn that script in. We will run that script and grade you on the results. Your script should perform the following steps:

1. Create a new directory called ``<nau-id>_pdb_files`` (e.g., mine would be called ``jgc53_pdb_files``).

2. Create a file in that directory called ``pdb_retrieval.log`` which contains:
 a. the time the script began running (including descriptive text like `Logging started at:` ``<time>``) - this should only be the time, not the date (use google and ``man`` to figure out the formatting)
 b. the time the script completed running (again with descriptive text like `Logging ended at:` ``<time>``) - this should only be the time, not the date (use google and ``man`` to figure out the formatting) 
 c. the URLs of the files that were downloaded
 d. the date of the download (so in case of future changes to the files on the PDB you know what versions of the files you obtained) - this should only be the date, not the time (use google and ``man`` to figure out the formatting)
 e. any other information that you think might be important to log.

3. Download the following PDB records as PDB files in ``.gz`` format: ``4DA7``, ``1HSG``,  ``1ZQA``, ``2RNM``, ``1RCX``, ``1GFL``,  ``2WDK`` (Hint: first go to the Protein Data Bank website and find the link to those records. Then figure out how to generalize that link to match different records.)

4. Unzip all of the ``.gz`` files. (Hint: a wildcard expression is useful here.)

5. Extract the line(s) containing PMIDs (PubMed Identifiers) for each of the records (Hint: Use ``egrep`` for this, and review the files to figure out where that information is) and write those lines to a new file called ``pmids.txt``.

6. Extract the line(s) containing TITLE for each of the records (Hint: Use ``egrep`` for this, and review the files to figure out where that information is) and write those lines to a new file called ``titles.txt``. 

7. Zip all of the PDB files in the directory with ``gzip``.

.. important::
	Homework id: ``shellscript``; Extension: ``sh``; For this assignment, the script file I turn in would be named ``jgc53_shellscript.sh``. Note that you will not turn in any files in the ``pdb_files`` directory: we'll generate those using your script. 
	
	E-mail your shell script as an attachment to alk224@nau.edu.

Regular Expressions (due 18 Sept 2012)
--------------------------------------
Download the EMP minimal mapping file :download:`here <files/emp_11sept2012_minimal_mapping_file.txt.gz>` - you'll need to unzip that file to get started. You can read about the `file format here <http://qiime.org/documentation/file_formats.html#metadata-mapping-files>`_.

Perform the reformatting steps described below. You'll turn in two metadata mapping files, one for the human-associated samples and one for all other samples (this splitting is one of the formatting steps described below). You'll also turn in a *patterns file*, which will be a text file containing list of the search and replace patterns that were applied to perform the reformatting, including "comment" lines before each pair of patterns describing what the following pattern does. Comment lines *must* begin with the ``#`` symbol so they can be computationally differentiated from non-comment lines.

Each line in your *patterns file* should contain exactly one regular expression pattern: for each task you should have the search pattern on one line, followed by the replace pattern on the next line. These patterns must work in either TextWrangler or jEdit (I don't care which, but your patterns must work in one of the two).

The tasks you must achieve are as follows:

#. Replace all fields where full text is ``no_data`` with ``NA``

#. Reorder the columns so the final output is in this order: ``SampleID``, ``BarcodeSequence``, ``LinkerPrimerSequence``, ``LATITUDE``, ``LONGITUDE``, ``PRINCIPAL_INVESTIGATOR``, ``COUNTRY``, ``STUDY_ID``, [intermediate fields: order doesn't matter], ``Description``

#. Append ``emp.summer2012.`` to the beginning of each line except the header line.

#. Reformat ``RUN_DATE`` entries to contain full year (four digits rather than two)

#. Create two new fields from ``PCR_PRIMERS`` field: ``FWD_PCR_PRIMER`` and ``REV_PCR_PRIMER`` where each field contains the primer nucleotide sequence only (ie., including only the IUPAC nucleotide characters).

#. Remove these columns: ``EMP_PERSON``, ``PRINCIPAL_INVESTIGATOR_CONTACT``
	
#. Split the full metadata file into two subfiles: one for human-associated samples, and one for all other samples.

#. ``TAXONID`` and ``PMID`` refer to NCBI database entries. What do these mean? Thinking ahead, how might you automatically extract these the information that these terms refer to? Do some research... (NOTE: nothing to turn in for this one, but I will call on people in class to share their ideas.)

.. important::
	Homework id: ``regex``; Extension: ``txt``; For this assignment, the patterns file I turn in would be named ``jgc53_regex.txt``. The metadata mapping files should be named ``<nau_id>_human_emp_11sept2012_minimal_mapping_file.txt`` and ``<nau_id>_other_emp_11sept2012_minimal_mapping_file.txt`` where ``<nau_id>`` is your NAU identifier. Mine would be ``jgc53_human_emp_11sept2012_minimal_mapping_file.txt`` and ``jgc53_other_emp_11sept2012_minimal_mapping_file.txt``.
	
	E-mail these three files as attachments to alk224@nau.edu.


GC content (due 4 Sept 2012) 
----------------------------
Download a genome and compute its GC content (i.e., the percent of the genome that is composed of G or C). Turn in a max of one page describing the steps that you took to achieve this, including failed attempts, and the genome you selected (include a link to the download page) and the GC content that you computed.

Note that there are various ways that you can just look up the GC content, including via the IMG website. I'm asking you to compute it, and you're being graded on your description of the process. Getting the right answer is a bonus (i.e., if you spend a couple of hours trying, and get it wrong, you'll be graded on your well-documented effort, not your final answer).

Hints: Start with the IMG Genome Browser, and work with a bacterial, archaeal or viral genome.

Be creative - there are many ways to achieve this.

.. important::
	Homework id: ``gc_content``; Extension: ``pdf``; For this first assignment, the file I turn in would be named ``jgc53_gc_content.pdf``. 

Text editor (due 30 Aug 2012)
-----------------------------
Download and install a text editor. Use one of the ones recommended in PCFB. There is nothing to turn in for this assignment.
