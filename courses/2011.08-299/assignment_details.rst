.. _assignment_details:

=========================
Assignment details
=========================

Programming assignment 3: Assembling an overlap table
-----------------------------------------------------

In this assignment you will assemble an overlap table that could be used in the de novo assembly of a genome from a set of short sequencing reads.

Create a new python file named ``prog3_<userid>.py``, where ``userid`` is replaced with your NAU user id. You must also define ``userid=<userid>`` (again where <userid> is replaced with your NAU user id) in your script so that it can be imported into other code. Any deviations from these instructions **will result in a zero on this assignment**!

In this file, define a function that takes a list of (sequence id, sequence) tuples and a substitution matrix. This function should return:
 * ``overlap_matrix``: a 2D list where each internal list ``i``  represents a vector of the number of overlapping positions between sequence ``i`` and every sequence in the input sequence collection;
 * ``repeat_counts``: a list containing the number of times each sequence is repeated in its entirety. 

The overlap score should be ``-1`` for the overlap between a sequence and itself or any other identical repeat. (For identical repeat I use the definition of python string equality, so if ``a == b``, ``a`` is an identical repeat of ``b`` and vice versa.)

The function should be of the form::

    def compute_overlaps(seqs,substitution_matrix):
        # do a bunch of work
        return overlap_matrix, repeat_counts

You should additionally define a 2D dictionary ``assembly_substitution_matrix`` that contains scores for substitutions between the nucleotide bases. You will define the values in this martix to optimize them for this task.

Additionally, I want you to benchmark your script against several large collections of sequences, and plot the run time of each. You can get the run time by using the ``time`` command which is built-in to Unix/Linux and Mac OS X. If you are running Windows on your laptop you can either do this portion on the Amazon Cloud or in the Computer Science lab in the engineering building. It may be useful for you to generate a command line interface for your script to achieve this portion of the assignment. The ``MinimalFastaParser`` function in PyCogent will additionally be useful here: given an open fasta file, this returns a list (really a generator) of (sequence_id, sequence) tuples, which is the input expected by ``compute_overlaps``.

Download the files here for your benchmark analysis :download:`here <py/assembly_benchmark.zip>` For this component of the assignment, I want you to turn in a scatter plot where the x axis is the number of sequences in the input file and the y axis is the runtime of your script in seconds.

Hints:
 * You can optionally re-use the ``sw_align`` function generated in programming assignment 1. So everyone has access to a single implementation, you can use the version included :download:`here <py/sw_align.py>` To use this, place the file in the same directory as your ``prog3_<userid>.py`` and add the line ``from sw_align import sw_align`` to your script. If you choose not to use this function, be sure to include any necessary code in your ``prog3_<userid>.py`` file -- no other imports (unless from the python standard library or PyCogent) will be allowed (i.e., it needs to run on my laptop).
 * Your substitution matrix should be optimized so mismatches are scored so poorly that in practice they never show up.
 * You'll want to impose a high gap penalty so in practice gaps never show up.
 * Think about things you can do to optimize your code to reduce the run time. This may come up on the final... 

:download:`This script <py/test_prog3.py>` will allow you to test your code. This is a partial set of the tests that I will run. Passing all 4 of these tests will guarantee you at least a 40% on this homework assignment. After downloading this script to the same directory as your homework assignment you can run the tests as follows::

    python test_prog3.py prog3_jgc53.py

(Where my script is named ``prog3_jgc53.py``.)


Programming assignment 2: Constructing a phylogenetic tree
-----------------------------------------------------------

In this assignment you will make use of the PyCogent software package to automate the process of constructing a phylogenetic tree from a set of genes. 

Create a new python file named ``prog2_<userid>.py``, where ``userid`` is replaced with your NAU user id. You must also define ``userid=<userid>`` (again where <userid> is replaced with your NAU user id) in your script so that it can be imported into other code. Any deviations from these instructions **will result in a zero on this assignment**!

In this file, define a function that takes a list of queries to be run against NCBI and a list of query labels to label the results of each query in the final tree, and returns a phylogenetic tree derived from aligned representatives of those queries. This function should optionally take a parameter ``n`` which defines how many randomly chosen representative sequences should be chosen for each of the queries. The default value for ``n`` should be 5. For example::

    def obtain_sequences_and_build_tree(queries,query_labels,n=5):
        # do a bunch of work
        return tree

You should filter any sequences that have one or more ``N`` characters in them, and each sequence id should begin with the query label corresponding to that sequence.

``tree`` should be a PyCogent ``PhyloNode`` object. The function handle must look exactly like the one above (remember - the tests are automated so deviations from that will result in a zero!).

Items to turn in:
 * Your ``.py`` file, by e-mail.
 * Apply your function as follows and e-mail me a newick formatted tree file named ``prog2_<userid>.tre``, where ``userid`` is replaced with your NAU user id. Be sure your tree includes distances (i.e., branch lengths)::

    obtain_sequences_and_build_tree(
         ['"small subunit rRNA"[ti] AND archaea[orgn]',
          '"small subunit rRNA"[ti] AND bacteria[orgn]',
          '"small subunit rRNA"[ti] AND eukarya[orgn]'],
         ['A: ','B: ','E: '],
         n=5)

Hints: 
 * `This page <http://dl.dropbox.com/u/2868868/pycogent_160dev_docs/cookbook/building_a_tree_of_life.html>`_ will help.
 * The Amazon QIIME EC2 instance has PyCogent, muscle, and FastTree preinstalled. Working there will save you a lot of time on software installation.
 * Remember that you can call ``dir()`` on an object to find out what methods are available to that object. One of the methods associated with your tree object will help you generate a newick formatted tree.

:download:`This script <py/test_prog2.py>` will allow you to test your code. This is a partial set of the tests that I will run. Passing all 5 of these tests will guarantee you at least a 50% on this homework assignment. After downloading this script to the same directory as your homework assignment you can run the tests as follows::

    python test_prog2.py prog2_jgc53.py

(Where my script is named ``prog2_jgc53.py``.)




Programming assignment 1 (i.e., Modified exercise 41-44): Extra credit
----------------------------------------------------------------------

Create a new python file named ``prog1ec_<userid>.py``, where ``userid`` is replaced with your NAU user id. For example, mine is called ``prog1ec_jgc53.py``. Name it exactly like this (including case!). You must also define ``userid=<userid>`` (again where <userid> is replaced with your NAU user id) in your script so that it can be imported into other code. Any deviations from these instructions **will result in a zero on this assignment**!

Define a function of the form::

    def transcribe(dna)

which simulates transcription of a string passed as ``dna`` and returns the resulting sequence as a string.

Define another function of the form::
    
    def rc(dna)

which reverse complements a string passed as ``dna`` and returns the resulting sequence as a string.

Your python file should also define a command line interface that allows users to pass a single sequence followed by an operation (``t`` for transcribe or ``rc`` for reverse complement). The script should apply the appropriate operation and print the result to the terminal. If the user passes something other than ``t`` or ``rc``, for example ``xyz``, the script should print ``Unknown operation: xyz.``

You should be able to call your script as follows::

    python prog1ec_jgc53.py ACCGT t
    python prog1ec_jgc53.py ACCGT rc

Validate your script by downloading :download:`this script <py/test_prog1ec.py>` by saving it to the same directory as your script and running the command::

    python test_prog1ec.py prog1ec_jgc53.py

When your script is working correctly the output should end with::

    ----------------------------------------------------------------------
    Ran 5 tests in 0.117s

    OK

There are five tests implemented here, and each test is worth one extra credit point toward programming assignment 1. These are the same tests that I will run when you turn your assignment in.


Modified exercise 41-44
-----------------------

This exercise will be broken apart for the CS students and the Bio students. You should start this exercise with my Needleman-Wunsch python implementation presented here. If you feel that you should be doing the assignment assigned to the other group, e-mail me by Friday Oct 7th at the latest with an explanation of why and I will consider your request.

Begin with the Needleman-Wunsch implementation in the `lecture 11 notes <../lectures/lecture11.html>`_.

All students
^^^^^^^^^^^^
Add a new function with this `exact` form::

    nw_align(sequence1,sequence2,substitution_matrix)

This function should return, in this order, the aligned sequence 1 as a string, the aligned sequence 2 as a string, and the score of the global alignment.

Next, add a command line interface so users can call this with arbitrary sequences from the command line and have the aligned sequences and the score print to the screen.

Save this script named as follows replacing ``<userid>`` with your NAU user id ``prog1_<userid>.py``. For example, my file would be called ``prog1_jgc53.py`` because my NAU id is ``jgc53``.

Toward the top of the file define a variable ``userid`` that is set to your NAU user id. This is `very important` - you will receive a zero on this assignment if you do not do this. For me, this would look like::

    userid = "jgc53"

To confirm that your script is formatted correctly, :download:`this script <py/validate_assignment_specifications.py>`. Place this script in the same directory as your homework assignment and run the following command::
    
    validate_assignment_specifications.py <script_name>

Where ``<script_name>`` is replaced by the name of your script. For example, my command would look like::

    validate_assignment_specifications.py prog1_jgc53.py

You should get a message that three tests passed. If the message does not end with the following you have not formatted your homework correctly, and you will get a zero on the assignment::

    ----------------------------------------------------------------------
    Ran 3 tests in 0.007s

    OK

Bio students
^^^^^^^^^^^^

In the script you created above, define a new function of the form::

    generate_random_score_distribution(query_sequence,subject_sequence,n,substitution_matrix)

Which returns a list of ``n`` scores for aligning each of ``n`` random sequences of the same length as ``query_sequence`` against ``subject_sequence``. 

Next, define a function that takes a query sequence, a subject sequence, and a value ``n`` with this form::

    fraction_better_or_equivalent_alignments(query_sequence,subject_sequence,n,substitution_matrix)

This function should call ``generate_random_score_distribution`` to generate a list of scores for random alignments. It should then compute the score for aligning ``query_sequence`` against ``subject_sequence``. The return value of this function should be the number of random alignment scores that are better or equal to the actual alignment score divided by ``n``.

Generate a length 100 subject sequence randomly. Next generate about 5 query sequences of varied lengths (around 3 to around 75), and log the results of comparing each query sequence to the subject sequence. Log the sequences and results in your programming notebook. Describe any general patterns that you notice. What do you think this means? Run this example on the alignment we worked through in class (query sequence: ``HEAGAWGHEE``; subject sequence: ``PAWHEAE``) and describe the results. How does this alignment compare to your randomly generated alignments? Justify your answer in your programming notebook.

Hints:
 - In the Lecture 8 notes there is code illustrating how to generate a random sequence of bases at a given sequence length. Here we're working with protein sequences, but the process is the same.
 - Running your fraction_better_alignments on the query and subject sequences below will go quicker if you hook this up to the command line interface of your script. Every time the script is called, run this analysis and include the results at the end.

CS students
^^^^^^^^^^^

You will define a general function that can perform global (Needleman-Wunsch; NW) or local (Smith-Waterman; SW) alignments.

Define a new function, ``generate_sw_and_traceback_matrices`` with the following form::

    generate_sw_and_traceback_matrices(seq1,seq2,gap_penalty,substitution_matrix)

The return value should be the dynamic programming matrix and the traceback matrix for a SW alignment. 

Define a new function ``sw_traceback`` with the form::

    sw_traceback(traceback_matrix,sw_matrix,seq1,seq2)

This function should return aligned the aligned sequences in the order they were passed in and the alignment score.

Define a new function ``align`` with the following form::

    align(sequence1,sequence2,substitution_matrix,local)
    
Where ``local`` is a boolean value. This function should return aligned_sequence1, aligned_sequence2, and the best alignment score. If ``local==False``, an NW alignment should be performed. If ``local==True`` an SW alignment should be performed. 

Hook this up to the command line interface so the user can optionally create a global or a local alignment.

Hints:
 - In my `slides from lecture 9 <http://dl.dropbox.com/u/2868868/cs299_slides_XCFGcsdFGGad/Lecture9.pptx.pdf>`_ I provide details on the differences between SW and NW initialization, scoring, and traceback. 


Modified exercise 38
--------------------

For LPTHW modified exercise 38 I want you to find and review bioinformatics code (rather than some random code out on the internet). 

For folks who are already comfortable with Python, start with PyCogent, QIIME, or any other bioinformatics python code you come across. Start `here for PyCogent <http://pycogent.svn.sourceforge.net/viewvc/pycogent/trunk/cogent/>`_ or `here for QIIME <http://qiime.svn.sourceforge.net/viewvc/qiime/trunk/qiime/>`_ (after clicking on a file name, click the ``View`` link under ``Links to HEAD``). Record in your programming notebook which file(s) you work with.

For students who are just learning python, review in detail the sequence evolution script that we built in Lecture 8. Work through this until you can explain what `each line` is doing. Ideally work with a friend and explain the lines to each other. Then make some modifications to change the behavior. You can find that :ref:`here <sequence-evolution-script>`.


BLASTing Through the Kingdom of Life
-------------------------------------

**This assignment will be due in class on Tuesday Sept 27th. This is a graded homework assignment that must be turned in on paper (i.e., not digitally). Your answers must be typed, not hand-written, and formatted as in the example answers in** :download:`this document <./BTTKOL_students.pdf>` **. Your name must appear at the top left of the first page.** I will deduct points for deviations from these requirements.

In class on Tuesday Sept 20th I'll give out assignments of which students will work with which two sequences. Everyone should work independently on this project: it's OK to talk with other students about the project, but **it is not OK look at each others results**.

This assignment will go faster if you start by reviewing `this tutorial <http://www.digitalworldbiology.com/BLAST/index.html>`_.

You can find your sequences `here <http://www.digitalworldbiology.com/BLAST/62000sequences.html>`_ and the list of assigned sequences :download:`here <BLASTing_assignments.txt>` .

You should answer the questions posted :download:`here <./BTTKOL_students.pdf>` for each of your two sequences. Note that there are sample answers for an example sequence - you should format your answers as you see in the sample answers in this PDF (don't forget the `Information Source`!).



Modified Exercise 36: Adding error checking to our sequence processing script
-----------------------------------------------------------------------------

Read through Exercise 36, but don't do the `Homework` section. Instead, do the following.

Start with the example script from lecture 5 (:ref:`see here <sequence-processing-script>`: use the last one included in lecture 5 with the ``reverse_complement`` and ``transcribe`` functions.)

We discussed several times that the ``reverse_complement`` function as implemented is wrong. Use a ``for`` loop to improve this: this script should print an error message to the terminal and exit without writing the output file if the input sequence contains any characters other than ``A``, ``C``, ``G``, or ``T``. 

Advanced python users: try reimplementing this function with a dictionary and with string's ``translate`` method. Which implementation is most efficient if you try to process a lot (e.g., 100) very large strings (e.g., length 1,000,000)? Back up your answer with data (hint: check out the ``time`` command) and log your results in your programming notebook. Check out the ``choice`` method in the ``random`` module - use this with a ``for`` loop to generate your string. Can you come up with any more efficient mechanisms for reverse complementing a string (I don't have a specific example in mind here...)? What are some reasons why you might choose one implementation over another?

Log your modified script in your programming notebook by pasting the code in. 

**E-mail me your programming notebook before class begins on Tuesday!**


Programming noteboook (on-going; will be collected several times through-out the semester)
------------------------------------------------------------------------------------------
The programming notebook is an electronic journal to keep track of your progress with learning python. The things that I'm looking for are notes on what you had difficulties with, what you had to look up along the way, and how you solved certain problems. As you move through the exercises you'll undoubtedly run into the same issues again - if you have a record of how you previously solved a problem, looking back through this journal should help you. You are also expected to answer any ``Extra Credit`` questions that are raised in the LPTHW text in your programming notebook. I don't, however, need to see all of the code snippets that you write for the exercises here.

I recommend that you keep notes in whatever program you're comfortable with, provided that when I collect these you'll be able to generate a PDF that you can send to me. Some choices might be MS Word, Google Docs, Evernote, Gedit (you'll need to print to PDF), etc. 

A few (random) times through-out the semester I'll collect your programming notebooks in electronic form. I'll review these and score them on completeness.

Here's an example of what your notebook might look like for the first three exercises::

    Exercise 0 (31 Aug 2011)
    
    Installed Gedit and created a test file. Had to look up how to make and 
    change directories on the web. I googled "how to make a directory in the 
    Terminal" and found this page: http://guides.macrumors.com/Terminal. This
    pages covers some useful commands for working the in terminal - I found 
    mkdir and cd here.
    
    Exercise 1
    
    This exercise was easy. Ran into one issue where I got a syntax error 
    because I used a double-quote to start a string and a single-quote to 
    end a string. Easy fix once I figured out the problem. 
    
    Extra credits: 1) Just added another print statement; 2) Deleted all of 
    the lines except for one; 3) The '#' symbol causes a line not to be 
    interpreted - if you add this to the line everything after the # is ignored. 
    I figured this out by experimenting with putting # signs in my code and 
    rerunning it. This would have been a better way to achieve the result of 
    exercise (2).
    
    Exercise 2 (1 Sept 2011)
    
    No problems with writing or running the code.
    
    Extra credits: 1) Yep, I was right about what the '#' symbol does. 3) Missed a 
    space between print and "This will run." on line 9 when re-entering the code. This 
    caused a syntax error.
