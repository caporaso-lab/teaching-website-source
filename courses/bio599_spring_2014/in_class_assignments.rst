==========================================================================================
In-class assignments
==========================================================================================


Lecture 5
=========

Working with the python interpreter
-----------------------------------

Define some variables, and do some math with those variables. 

Write a python `Hello World` script
-----------------------------------

Log in to the cluster, write a program called ``hello_world.py`` that when run prints the text ``Hello World!`` to the terminal. You should be able to call this script from anywhere like:

	hello_world.py


Lecture 4
=========

Using ``grep`` and navigating directories
-----------------------------------------
Download the Greengenes 13_8 OTUs subset from `here <https://dl.dropboxusercontent.com/s/a0coxo8zkw6qz63/gg_13_8_otus_sub.tgz>`_ using curl. Untar/zip the file (hint: use ``tar -xzvf``), and change to the resulting directory. Under this directory, there is another directory called ``rep_set`` which contains several fasta files. How do you get ``grep`` to print the number of lines in a file rather than the lines which match a pattern? How many sequence records are in the ``97``, ``88``, and ``73`` variants of those files?

Configure ftp in your coding account
------------------------------------

See the instructions `here <http://learn.koding.com/setting-up-ftp-on-koding/>`_. 

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

Write a more useful shell script
--------------------------------

Write a new shell script that tells you the number of records in a fasta file, if you provide a path to a fasta file on the command line. Hint: If you pass argument(s) to your script, you can access those within the script as ``$1``, ``$2``, .... 

Lecture 3
=========

Create a koding account
-----------------------

.. note::
	If you want e-mail updates on NAU's Linux cluster (and other local "big data" topics), see `here <http://caporasolab.us/teaching/#keeping-up-to-date-on-bioinformatics-at-nau>`_.

Go `here <https://koding.com/R/gregcaporaso>`_ to create a new account at koding.com. Boot up a virtual machine, and open the terminal.

The remaining exercises will be performed in your koding.com virtual machine. 

Using ``curl`` and ``grep``
---------------------------
Download the EMP minimal mapping file, directly into your AWS instance, from `here <https://dl.dropboxusercontent.com/s/f7ysoltbn0zpah7/e
mp_11sept2012_minimal_mapping_file.txt.gz>`_ using ``curl``. You'll need to unzip that file with ``gunzip`` to get started. You can read about the `file format here <http://qiime.org/documentation/file_formats.html#metadata-mapping-files>`_.

How do you perform a search with ``grep``? How do you invert a search with ``grep``?  How can you print the lines that contain information on human-associated samples? How can you print the lines that contain information on non-human-associated samples?

Lecture 2
=========

Working with regular expressions
--------------------------------

Download `this file <https://www.dropbox.com/s/m21r7l91al1k0nt/Lecture2_support.zip>`_ and unzip it. Work through the examples presented in the lecture slides.

Lecture 1
=========

Studying genomes
----------------

Download a bacterial or archaeal genome (I suggest starting at `IMG <http://img.jgi.doe.gov/w/>`_, but whatever source you're comfortable with is fine), find a gene in that genome, and determine the function of that gene.




