============================================
Lecture 15: Programming review session
============================================


Common data types in python: lists, strings, dictionaries, ints, floats, boolean values, tuples
================================================================================================

string
^^^^^^^
::

    s = '40'
    r = '20'

    print r + s

int
^^^
::

    s = 40
    r = 20

    print r + s

float
^^^^^
::

    s = 40.0
    r = 20.0

    print r + s

boolean values: True or False
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
::

    s = True
    r = False

    print s or r

    print s and r

    print 42 == 42

    print 4 > 5

    c = True
    print (42 >= 41) and ('A' == 'a' or c)


Loops and conditionals
======================

Loops
^^^^^^^^^^^^^^^^^^^^^^

``for`` loops are much more commonly used in python then ``while`` loops (although this isn't necessarily true in other languages). ``for`` loops allow you to iterate over several steps of code to perform the same operation multiple times, usually with a different value for one or a few variables. For example, what does this code do::

    for c in 'ACCGATTGACC':
        print c.lower(),

``c`` in this case is a variable name that gets set to each entry in the string in turn. All code in the indented block will be executed before ``c`` gets assigned to the next value.

Sometimes you need to do the same thing some specified number of times with no different variable settings (which differs from the previous example where we're doing the same thing multiple times with a different value of ``c`` each time). To do this in python, you would typically use the ``range`` function, which when called as::

    range(n)

returns a list of numbers from 0 to n-1: ``[0, 1, 2, ..., n-1]``. For example, to randomly reorder the positions in a given DNA sequence 25 times and print the resulting sequences, you could do the following::

    sequence = 'ACCGAGGACCATACATTA'
    for i in range(25):
        shuffle(sequence)
        print ''.join(sequence)

Note that we don't actually use the value assigned to the variable ``i`` ever: we just use that in combination with range to iterate 25 times.

Conditional statements
^^^^^^^^^^^^^^^^^^^^^^^

Conditional statements allow you to apply some steps under certain conditions, such as when two values are equal, and apply some other steps in cases where those certain conditions are not met. The ``if/elif/else`` statements are used for conditionally executing some code in python. For example, describe line-by-line what this code does::

    sequence = 'ACCTAGGCAT'
    result = []
    for base in sequence:
        if base == 'T':
            result.append('U')
        elif base == 'A' or base == 'C' or base == 'G':
            result.append(base)
        else:
            print "Unknown base (%s). Cannot complete." % base
            exit()
    print ''.join(result)

Functions in python
===================

::

    def complement_sequence(seq,complements={'A':'T','C':'G','T':'A','G':'C'}):
        result = []
        for base in seq:
            result.append(complements[base])
        return ''.join(result)

    my_seq = 'ACCGATTAGCCA'
    complement_sequence(my_seq)
    my_seq_comp = complement_sequence(my_seq)

    my_seq_comp_non_default = complement_sequence(my_seq,{'A':'t','C':'g','T':'a','G':'c'})