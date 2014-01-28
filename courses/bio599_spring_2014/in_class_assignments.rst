==========================================================================================
In-class assignments
==========================================================================================

Lecture 5
=========

Create a koding account
-----------------------

.. note::
	If you want e-mail updates on NAU's Linux cluster (and other local "big data" topics), see `here <http://caporasolab.us/teaching/#keeping-up-to-date-on-bioinformatics-at-nau>`_.**

Go `here <https://koding.com/R/gregcaporaso>`_) to create a new account at koding.com. Boot up a virtual machine, and open the terminal.

The remaining exercises will be performed in your koding.com virtual machine. 

Using ``curl`` and ``grep``
---------------------------
Download the EMP minimal mapping file, directly into your AWS instance, from `here <https://www.dropbox.com/s/up005whnyunid9o/emp_11sept2012_minimal_mapping_file.txt.zip>`_ using ``curl``. You'll need to unzip that file with ``gunzip`` to get started. You can read about the `file format here <http://qiime.org/documentation/file_formats.html#metadata-mapping-files>`_.

How do you invert a search with ``grep``?  How many lines contain information on human-associated samples? How many lines contain information on non-human-associated samples?

Using ``grep`` and navigating directories
-----------------------------------------
Under the ``qiime_software`` directory, there is a ``gg_otus_4feb2011`` directory, and another directory under that called ``rep_set`` which contains several fasta files. How do you perform a search with ``grep``? How do you get ``grep`` to print the number of lines in a file rather than the lines which match a pattern? How many sequence records are in the ``97``, ``88``, and ``73`` variants of those files?

Configure ftp in your coding account
------------------------------------

See the instructions here. 

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




