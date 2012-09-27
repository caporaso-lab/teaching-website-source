==========================================================================================
In-class assignments
==========================================================================================

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

Start with :download:`this file <>`

Remove header (i.e. comment) lines

Format each line to contain the subject id, the query id, the e-value, the percent identity, and the alignment length, in that order!
Format as comma-separated text

Rearrange tabular data
----------------------

Start with :download:`this file <>` (source: `Practical Computing for Biologists`)

Lecture 4
=========

Reformat sequence headers in a fasta file
-----------------------------------------

Start with :download:`this file <>`

Rewrite each identifier as the portion of the identifier preceding the . character, followed by an underscore, followed by the genus name.

Reformat coordinates
--------------------

Start with :download:`LatLong.txt <>` (source: `Practical Computing for Biologists`)
Make Lat/Long pairs tab-separated on a single line
Remove trailing N and E, and replace with leading +
Remove trailing S and W, and replace with leading -

Lecture 3
=========

Reformat taxa names
-------------------

Start with :download:`this file <>`

Reformat taxa names to genus abbreviation, species name, name of person who named the species separated by underscores and excluding any parenthesis. 

Lecture 2
=========

Studying genomes
----------------

Download a bacterial or archaeal genome (I suggest starting at `IMG <http://img.jgi.doe.gov/w/>`_, but whatever source you're comfortable with is fine), find a gene in that genome, and determine the function of that gene.




