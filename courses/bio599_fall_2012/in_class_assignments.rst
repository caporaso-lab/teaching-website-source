==========================================================================================
Homework assignments
==========================================================================================

Lecture 9
=========
Today's exercises are all to be performed in the QIIME AWS instance. You'll get a public DNS entry to connect in class.


Using ``grep``
--------------
Under the ``qiime_software`` directory, there is a ``gg_otus_4feb2011`` directory, and another directory under that called ``rep_set`` which contains several fasta files. How do you perform a search with ``grep``? How do you get ``grep`` to print the number of lines in a file rather than the lines which match a pattern? How many sequence records are in the ``97``, ``88``, and ``73`` variants of those files? 


``curl`` and ``grep``
----------------------
Download the EMP minimal mapping file, directly into your AWS instance, from :download:`here <files/emp_11sept2012_minimal_mapping_file.txt.gz>` using ``curl`` - you'll need to unzip that file with ``gunzip`` to get started. You can read about the `file format here <http://qiime.org/documentation/file_formats.html#metadata-mapping-files>`_.

How do you invert a search with ``grep``?  How many lines contain information on human-associated samples? How many lines contain information on non-human-associated samples?



