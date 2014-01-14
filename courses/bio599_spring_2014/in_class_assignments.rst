==========================================================================================
In-class assignments
==========================================================================================

Lecture 26
==========

Create a `gist <http://gist.github.com>`_ containing your code for programming assignment 2.

Lecture 22
==========

In your IPython Notebook, write a block of code that implements a protein molecular calculator by summing the weights of the individual amino acids in a protein sequence.

Lecture 20
==========

Write a python `Hello World` script
-----------------------------------

Log in to the cluster, write a program called ``hello_world.py`` that when run prints the text ``Hello World!`` to the terminal. You should be able to call this script from anywhere like:

	hello_world.py


Lectures 13-14
==============

Working with a graphical ftp client
-----------------------------------
Use `Cyberduck <http://www.cyberduck.ch>`_ to move data files to and from the cluster. You can find `instructions for connecting to AWS with Cyberduck here <http://qiime.org/tutorials/working_with_aws.html#working-with-cyberduck>`_.

QIIME Illumina Overview tutorial
--------------------------------
We'll work through the QIIME Illumina overview tutorial in class. This will be related to the next homework assignment, so I encourage you to continue working on this outside of class if we don't finish up. You can `find the QIIME Illumina Overview Tutorial here <http://qiime.org/svn_documentation/tutorials/illumina_overview_tutorial.html>`_.

Lectures 10-11
=============
Today's exercises are all to be performed in the QIIME AWS instance. You'll get a public DNS entry to connect in class.

Writing a first shell script
----------------------------
Set your ``PATH`` environment variable to contain a new ``scripts`` directory under your directory. Create a new file called ``my_script.sh`` with ``nano`` and enter the following text::
	
	#!/bin/bash
	echo "Below are contents of the directory:"
	pwd
	ls -al
	echo "The time is currently:"
	date

Now change the permissions on this file to give it execute permissions::

	chmod u+x my_script.sh

This exercise is derived from *Practical Computing for Biologists*

Lecture 9
=========
Today's exercises are all to be performed in the QIIME AWS instance. You'll get a public DNS entry to connect in class.


Using ``grep``
--------------
Under the ``qiime_software`` directory, there is a ``gg_otus_4feb2011`` directory, and another directory under that called ``rep_set`` which contains several fasta files. How do you perform a search with ``grep``? How do you get ``grep`` to print the number of lines in a file rather than the lines which match a pattern? How many sequence records are in the ``97``, ``88``, and ``73`` variants of those files? 


Using ``curl`` and ``grep``
---------------------------
Download the EMP minimal mapping file, directly into your AWS instance, from :download:`here <files/emp_11sept2012_minimal_mapping_file.txt.gz>` using ``curl`` - you'll need to unzip that file with ``gunzip`` to get started. You can read about the `file format here <http://qiime.org/documentation/file_formats.html#metadata-mapping-files>`_.

How do you invert a search with ``grep``?  How many lines contain information on human-associated samples? How many lines contain information on non-human-associated samples?

Lecture 5
=========
These exercises will make use a text editor, such as TextWrangler or jEdit.

Reformat blast9 output
----------------------

Start with :download:`this file <files/blastx_out.bl9>`

Remove header (i.e. comment) lines

Format each line to contain the subject id, the query id, the e-value, the percent identity, and the alignment length, in that order!
Format as comma-separated text

Rearrange tabular data
----------------------

Start with :download:`this file <files/Ch3observations.txt>` (source: `Practical Computing for Biologists`)

Lecture 4
=========

Reformat sequence headers in a fasta file
-----------------------------------------

Start with :download:`this file <files/regex_seqs.fasta>`

Rewrite each identifier as the portion of the identifier preceding the . character, followed by an underscore, followed by the genus name.

Reformat coordinates
--------------------

Start with :download:`LatLong.txt <files/LatLon.txt>` (source: `Practical Computing for Biologists`)
Make Lat/Long pairs tab-separated on a single line
Remove trailing N and E, and replace with leading +
Remove trailing S and W, and replace with leading -

Lecture 3
=========

Reformat taxa names
-------------------

Start with :download:`this file <files/taxa_list.txt>`

Reformat taxa names to genus abbreviation, species name, name of person who named the species separated by underscores and excluding any parenthesis. 

Lecture 2
=========

Studying genomes
----------------

Download a bacterial or archaeal genome (I suggest starting at `IMG <http://img.jgi.doe.gov/w/>`_, but whatever source you're comfortable with is fine), find a gene in that genome, and determine the function of that gene.




