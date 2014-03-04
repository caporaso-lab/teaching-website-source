==========================================================================================
Homework assignments
==========================================================================================

.. important:: I encourage you to discuss homework assignments with each other, but you may not view other student's assignments or share your assignment with others. When you start programming, you often think there is a single way to address a task, but that is usually not the case: there are many ways to complete these assignments, and when code has been shared or copied it is often very obvious to a more experienced eye.

Turning in your homework by email
---------------------------------
Your homework must always be turned in with a standardized name. That name should be ``<nau_id>_<homework_id>.<extension>``, where ``<nau_id>`` is your NAU identifier (for example, mine is ``jgc53``), and ``<homework_id>`` and ``<extension>`` are provided on a per-assignment basis. 

Unless otherwise noted, homework must be turned in by email to gregcaporaso@gmail.com before class on the day it is due.

Programming Assignment 2 (1 Apr 2014) (20 points)
-------------------------------------------------

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

Programming Assignment 1 (due 4 Mar 2014)  (20 points)
-------------------------------------------------------

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


Shell script (due 18 Feb 2014)  (20 points)
-------------------------------------------

In this assignment you will automate retrieval and processing of PDB files with a shell (``bash``) script, and turn that script in. I will run that script and grade you on the results. 

You should develop this script in your virtual machine on koding.com, or test it there before turning it in. That is where I'll run your code, so you need to be sure that it works correctly in that environment. If it works on your laptop, but not on koding.com, that's not good enough!

Your script should perform the following steps:

1. Create a new directory called ``<nau-id>_pdb_output`` (e.g., mine would be called ``jgc53_pdb_output``). I'll refer to this as your *output directory*.

2. Create a file in your output directory called ``pdb_retrieval.log`` which contains:
 a. the time the script began running (including descriptive text like `Logging started at:` ``<time>``) - this should only be the time, not the date (use google and ``man`` to figure out the formatting)
 b. the time the script completed running (again with descriptive text like `Logging ended at:` ``<time>``) - this should only be the time, not the date (use google and ``man`` to figure out the formatting) 
 c. the URLs of the files that were downloaded
 d. the date of the download (so in case of future changes to the files on the PDB you know what versions of the files you obtained) - this should only be the date, not the time (use google and ``man`` to figure out the formatting)
 e. any other information that you think might be important to log.

3. Download the following PDB records as PDB files in ``.gz`` format: ``4DA7``, ``1HSG``,  ``1ZQA``, ``2RNM``, ``1RCX``, ``1GFL``,  ``2WDK`` (Hint: first go to the Protein Data Bank website and find the link to those records. Then figure out how to generalize that link to match different records.)

4. Unzip all of the ``.gz`` files. (Hint: a wildcard expression is useful here.)

5. Extract the line(s) containing PMIDs (PubMed Identifiers) for each of the records (Hint: Use ``grep`` for this, and review the files to figure out where that information is) and write those lines to a new file called ``pmids.txt`` in your output directory.

6. Extract the line(s) containing TITLE for each of the records (Hint: Use ``grep`` for this, and review the files to figure out where that information is) and write those lines to a new file called ``titles.txt`` in your output directory. 

7. Zip all of the PDB files in the directory with ``gzip``.

.. important::
	Homework id: ``shellscript``; Extension: ``sh``; For this assignment, the script file I turn in would be named ``jgc53_shellscript.sh``. Note that you will not turn in any files in the ``pdb_files`` directory: I'll generate those using your script. 
	
	E-mail your shell script as an attachment to gregcaporaso@gmail.com.

Regular Expressions  (20 points)
--------------------------------------
Download the EMP minimal mapping file `here <https://www.dropbox.com/s/up005whnyunid9o/emp_11sept2012_minimal_mapping_file.txt.zip>`_. You'll need to unzip that file to get started. You can read about the `file format here <http://qiime.org/documentation/file_formats.html#metadata-mapping-files>`_.

Perform the reformatting steps described below. You'll turn in one metadata mapping file, reformatted as described below. You'll also turn in a *patterns file*, which will be a text file containing list of the search and replace patterns that were applied to perform the reformatting, including "comment" lines before each pair of patterns describing what the following pattern does. Comment lines *must* begin with the ``#`` symbol so they can be computationally differentiated from non-comment lines.

Each line in your *patterns file* should contain exactly one regular expression pattern: for each task you should have the search pattern on one line, followed by the replace pattern on the next line. These patterns must work in either TextWrangler or jEdit (I don't care which, but your patterns must work in one of the two).

The tasks you must achieve are as follows:

#. Replace all fields where full text is ``no_data`` with ``NA``

#. Reorder the columns so the final output is in this order: ``SampleID``, ``BarcodeSequence``, ``LinkerPrimerSequence``, ``LATITUDE``, ``LONGITUDE``, ``PRINCIPAL_INVESTIGATOR``, ``COUNTRY``, ``STUDY_ID``, [intermediate fields: order doesn't matter], ``Description``

#. Append ``emp.summer2012.`` to the beginning of each line except the header line.

#. Reformat ``RUN_DATE`` entries to contain full year (four digits rather than two)

#. Create two new fields from ``PCR_PRIMERS`` field: ``FWD_PCR_PRIMER`` and ``REV_PCR_PRIMER`` where each field contains the primer nucleotide sequence only (ie., including only the IUPAC nucleotide characters).

#. Remove these columns: ``EMP_PERSON``, ``PRINCIPAL_INVESTIGATOR_CONTACT``

#. ``TAXONID`` and ``PMID`` refer to NCBI database entries. What do these mean? Thinking ahead, how might you automatically acquire the information that these terms refer to? Do some research... (NOTE: nothing to turn in for this one, but I will call on people in class to share their ideas.)

.. important::
	Homework id: ``regex``; Extension: ``txt``; For this assignment, the patterns file I turn in would be named ``jgc53_regex.txt``. The metadata mapping file should be named ``<nau_id>_emp_11sept2012_minimal_mapping_file.txt`` where ``<nau_id>`` is your NAU identifier. Mine would be ``jgc53_emp_11sept2012_minimal_mapping_file.txt``.
	
	E-mail these three files as attachments to gregcaporaso@gmail.com.

GC content (due 21 Jan 2014) (10 points)
----------------------------------------
Download a genome and compute its GC content (i.e., the percent of the genome that is composed of G or C). Turn in a max of one page describing the steps that you took to achieve this, including failed attempts, and the genome you selected (include a link to the download page) and the GC content that you computed.

Note that there are various ways that you can just look up the GC content, including via the IMG website. I'm asking you to compute it, and you're being graded on your description of the process. Getting the right answer is a bonus (i.e., if you spend a couple of hours trying, and get it wrong, you'll be graded on your well-documented effort, not your final answer).

Hints: Start with the IMG Genome Browser, and work with a bacterial, archaeal or viral genome.

Be creative - there are many ways to achieve this.

.. important::
	Homework id: ``gc_content``; Extension: ``pdf``; For this first assignment, the file I turn in would be named ``jgc53_gc_content.pdf``. 

Text editor (due 21 Jan 2014)
-----------------------------
Download and install a text editor. Use one of the ones recommended in PCFB. There is nothing to turn in for this assignment.
