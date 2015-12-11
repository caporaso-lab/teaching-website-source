=========================================================================
Lecture 4: From DNA to protein (part1, continued), and python programming
=========================================================================

Chromosome structure
--------------------

* DNA is highly compressed (particularly in eukaryotes, but see `here <http://www.nature.com/scitable/topicpage/genome-packaging-in-prokaryotes-the-circular-chromosome-9113>`_ for a discussion of DNA supercoiling in bacteria)
* `Compression of eukaryotic DNA into chromosomes <http://www.nature.com/scitable/topicpage/chromosomes-14121320>`_ affects access of RNA polymerase to sequences to be transcribed (heterochromatin versus euchromatin).

Review of the LPTHW exercises, so far
-------------------------------------

Printing: key concepts
^^^^^^^^^^^^^^^^^^^^^^

* Several types of quotes can be used: ``"``, ``'``, ``'''``, and ``"""``
* Strings can be join with ``+`` or continued across lines by ending a line with a ``,``
* Several special characters in strings: tab (``\t``) and new line (``\n``)
* To print a `literal character` you `escape` it with a `\\`
* ``%s`` versus ``%r``: the former prints a string while the latter prints python's internal representation of a string (hence the surrounding singe quotes). Try this::

    print "this is a test comparing %s to %r" % ("hello","hello")

Variables
^^^^^^^^^

Variables: a name associated with some value (a number, a string, a list...) for the purposes of storage and reference. These can generally be changed as follows::

    a = 42
    print a
    a = 43
    print a

Exercise 13: the ``sys`` module and ``argv``
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

``argv`` allows you to take parameters from the command line. This is useful for allowing your python scripts (ie., your python ``.py`` files) to do different things with different inputs. Here's a script that makes use of ``argv`` to reverse complement a sequence provided on the command line::

    from sys import argv
    script_name, sequence = argv
    print sequence.replace('A','t').replace('T','a').replace('G','c').replace('C','g').upper()[::-1]

For some help with the third line of that script refer back to the `Lecture 2 outline <./lecture2.html>`_.

.. note:: Advanced users should check out the ``optparse`` module for interacting with command line arguments. This is what's used in PyCogent and QIIME to create very complex command line interfaces which include things like optional and required arguments and help text for scripts.

Exercise 13: Packing and unpacking variables 
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Exercise 13 also shows how to set multiple variables in one step. This is purely used for convenience and clarity of code. The following code block do the exact same thing::

    a, b, c = 42, 44, 46
    print a
    print b
    print c

::

    a = 42
    b = 44
    c = 46
    print a
    print b
    print c

Exercise 15: files
^^^^^^^^^^^^^^^^^^

On the subject of opening files, let's look at a standard bioinformatics file type: the ``fasta`` file. You'll run into these a lot so it's important to understand what they look like. Here's an example of a valid fasta file::

    >sequence1 Homo sapiens
    ACCGGAGGACCGTACGACTAGCATCACGACTACGACTACAGCATCACGACTACGACTACGACG
    ACTACGCACTACTTTTGACACTACGACACACCTAGCTCCGACTACGACGACTGACCGCGATCA
    GCAGCATCAGCACGATCAGCACG
    >sequence2 Pan troglodytes
    ACCGGAGGACCGTACGACTAGCATCACGACTACGACTACAGCATCACGACTACGACTACGACG
    ACTACGCACTACTTTAGACACTACGCACCTAGCTCCGACTACGACGACTGACCGCGATCAGCT
    GCATCAGCACGAACAGCACC

Here's a breakdown of what the fields represent::

    >sequence_identifier comment or description
    sequence

``>``: indicates the beginning of a new sequence record [REQUIRED]

``sequence_identifier``: this is an identifier that is unique within this file and contains no spaces [REQUIRED]

``comment or description``: everything after the first space is considered a comment or description -- this is arbitrary and optional text [OPTIONAL]

``sequence``: this is the nucleic acid or protein sequence [REQUIRED]

Let's integrate file writing with our reverse complement script. We'll take a sequence, a sequence name, and an output file name as input and write the reverse complement of the sequence to file::

    from sys import argv
    script_name, sequence, sequence_name, output_fasta_fp = argv
    
    output_file = open(output_fasta_fp,'w')
    output_file.write('>%s' % sequence_name)
    output_file.write('\n')
    output_file.write(sequence.replace('A','t').replace('T','a').replace('G','c').replace('C','g').upper()[::-1])
    output_file.write('\n')
    output_file.close()

.. note:: I'm calling my output file name ``output_fasta_fp`` here. The ``fp`` is shorthand for `filepath`, or the location of the file on the system. By default the file gets written to the `current working directory` (look this term up if it's unfamiliar) but you can also specify other places to write the file. For example, on my Apple laptop I could specify ``/Users/caporaso/Desktop/my.fasta`` to write the file to my desktop.

Exercises 18 to 21: Functions
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Now let's spend a little time on functions. Functions are self-contained pieces of code that (usually) take something as input and (usually) return something as output. Let's define a ``reverse_complement`` function::

    def reverse_complement(sequence):
        return sequence.replace('A','t').replace('T','a').replace('G','c').replace('C','g').upper()[::-1]
        
Now try calling this function::

    sequence = "GTTTATCCATCGTGCGTC"
    rc_sequence = reverse_complement(sequence)

Notice that we didn't get any information printed to the screen here. We were previously calling print on the resulting sequence, but here we're setting a new variable with that sequence. To see the result you can do the following::

    print rc_sequence

Note that you can also call print directly on the return value of the function::

    print reverse_complement(sequence)

This is because ``reverse_complement`` returns a string, and ``print`` takes a string as an argument.

.. warning:: **The reverse complement function that we implemented here is incomplete and dangerous.** The reason for this is that it doesn't do anything with characters other than ``A``, ``C``, ``G``, and ``T``. Try passing a ``M`` somewhere in your sequence. What happens? The reason why this is dangerous is because ``M`` (and several other characters) are often used in nucleic acid sequences, despite not being one of the four DNA bases. These other characters are known as `degenerate bases`, and represent more than one possible choice of a base. For example, you may see a sequence that looks like ``GTTMATCCATCGTGCGTC``. This means that the fourth base can either be an ``A`` or a ``C``, so the correct reverse complement of ``M`` is actually ``K`` (the degenerate base representing ``T`` or ``G``). Review this list of the `IUPAC nucleotide bases <http://www.bioinformatics.org/sms/iupac.html>`_. What's the reverse complement of ``H``? How about ``W``? **We'll soon implement a safer version of reverse complement.**

We can also define a ``transcribe`` function to simulate the process of transcription. That one is pretty simple - it looks like this::

    def transcribe(sequence):
        return sequence.replace('T','U')

You can now transcribe sequences as follows::

    transcribe(sequence)

Soon we'll build a script that can apply any of these functions to one or more input sequences in a fasta file and write the results to a new fasta file. There's a bit more learning to do before we get there.


