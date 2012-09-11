==========================================================================================
Homework assignments
==========================================================================================

Turning in your homework
------------------------
Your homework must always be turned in with a standardized name. That name should be ``<nau_id>_<homework_id>.<extension>``, where ``<nau_id>`` is your NAU identifier (for example, mine is ``jgc53``), and ``<homework_id>`` and ``<extension>`` are provided on a per-assignment basis. 

Unless otherwise noted, homework must be turned in by email to alk224@nau.edu before class on the day it is due. 

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
