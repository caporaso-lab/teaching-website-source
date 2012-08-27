========================================================
Lecture 10: Sequence alignment algorithms (continued)
========================================================


The following coding examples will cover the various features and tools in python that you've learned about (or will very shortly) and how they can be applied to implement the Needleman-Wunsch alignment algorithm. This same lesson can be applied to the Smith-Waterman alignment algorithm.


Two dimensional lists
=====================

You've been introduced to lists in python, but it's common that you need to represent multi-dimensional data such as a matrix. To do this, you can use a list where each entry in the list is a list. For example::

    matrix = [[0,1,2],[3,4,5],[6,7,8]]

You can then access entries in this list by indicating their index in order from the top-most list to the deeper lists. For example::

    # access the second entry of the second list
    matrix[1][1]

Try accessing some different values. You can also access one of the full inner lists in the usual way::

    matrix[1]

Dictionaries
============

A key concept is introduced in LPTHW exercise 40: the dictionary or ``dict``. These allow for efficient look-ups of `values` associated with a `key`, and are used constantly in python. 

Some of the key features associated with dictionaries include creating dictionaries, setting and resetting the values for certain keys, and looking up the values of certain keys. Dictionaries are created as follows::

    base_comps = {'A':'T', 'G':'C', 'T':'A', 'C':'G'}

This ``dict`` would be said to `map` each of the four DNA bases to its complement. You can do `lookups` on this dictionary as follows::

    print base_comps['A']

If you want to add or reset a value after dictionary creation you can do so as follows::

    # add a lookup for uracil
    base_comps['U'] = 'A'
    # remap the lookup for adenine 
    base_comps['A'] = 'U'
    # delete the entry for thymine
    del base_comps['T']
    
You can also check whether a key is contained in a dictionary using ``in``. For example, try these::

    'A' in base_comps
    
    'W' in base_comps

You'll notice that if you access an entry that is not in a dictionary you'll get a ``KeyError``. The error messages that you get when a ``KeyError`` is `thrown` may not always be very intuitive so adding a little additional error handling is a good idea. One way to do this is with an if/else statement, where you check for the presence of a key in a dictionary::

    if key in base_comps:
        return base_comps[key]
    else:
        print "%s is not in the base complement lookup dictionary" % key
        exit()

More commonly, expert python users will `catch` and handle the error if it happens using a ``try/except``. The following is a very common python idiom, so I want to introduce it in case you run into it in other code. Don't worry about integrating into your code too much for now - wait until you learn a little about ``Exceptions`` in python::

    try:
        print base_comps[key]
    except KeyError:
        print "%s is not in the base complement lookup dictionary" % key
        exit()

Using a dictionary to simplify our reverse complementing code
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Here's an example that will simplify our reverse complementing code::

    from sys import argv
    script_name, sequence = argv
    
    complements = {'A':'T',
                   'G':'C',
                   'T':'A',
                   'C':'G'}
    
    def reverse_complement_sequence(sequence,complements=complements):
        result = []
        # note that we're iterating over sequence in reverse here
        for base in sequence[::-1]:
            result.append(complements[base])
        return ''.join(result)
    
    rc_sequence = reverse_complement_sequence(sequence)
    print rc_sequence


Implementing substitution matrices with dictionaries
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

As with lists, you can create nested dictionaries, where each entry in the dictionary is a dictionary. One application of this is defining substitution matrices for use in sequence alignment. If you wanted to score different base substitutions differently, for example, you could define a substitution matrix as follows::

    substitution_matrix = {'A':{'A': 1,'C':-1,'G':-2,'T':-2},
                           'C':{'A':-1,'C': 1,'G':-2,'T':-2},
                           'G':{'A':-2,'C':-2,'G': 1,'T':-1},
                           'T':{'A':-2,'C':-2,'G':-1,'T': 1}}

This scoring matrix is scoring all substitutions events with negative scores, but differentiating between `transition` and `transversion` substitutions. If these terms are unfamiliar, look them up. Why might you score these differently? 

A commonly used scoring matrix for protein alignments is the BLOSUM50. To define the BLOSUM50 substitution matrix as a dictionary you could run the following::
    
    blosum50 = {'A': {'A': 5.0, 'C': -1.0, 'D': -2.0, 'E': -1.0, 'F': -3.0, 'G': 0.0, 'H': -2.0, 'I': -1.0, 'K': -1.0, 'L': -2.0, 'M': -1.0, 'N': -1.0, 'P': -1.0, 'Q': -1.0, 'R': -2.0, 'S': 1.0, 'T': 0.0, 'V': 0.0, 'W': -3.0, 'Y': -2.0},
 'C': {'A': -1.0, 'C': 13.0, 'D': -4.0, 'E': -3.0, 'F': -2.0, 'G': -3.0, 'H': -3.0, 'I': -2.0, 'K': -3.0, 'L': -2.0, 'M': -2.0, 'N': -2.0, 'P': -4.0, 'Q': -3.0, 'R': -4.0, 'S': -1.0, 'T': -1.0, 'V': -1.0, 'W': -5.0, 'Y': -3.0},
 'D': {'A': -2.0, 'C': -4.0, 'D': 8.0, 'E': 2.0, 'F': -5.0, 'G': -1.0, 'H': -1.0, 'I': -4.0, 'K': -1.0, 'L': -4.0, 'M': -4.0, 'N': 2.0, 'P': -1.0, 'Q': 0.0, 'R': -2.0, 'S': 0.0, 'T': -1.0, 'V': -4.0, 'W': -5.0, 'Y': -3.0},
 'E': {'A': -1.0, 'C': -3.0, 'D': 2.0, 'E': 6.0, 'F': -3.0, 'G': -3.0, 'H': 0.0, 'I': -4.0, 'K': 1.0, 'L': -3.0, 'M': -2.0, 'N': 0.0, 'P': -1.0, 'Q': 2.0, 'R': 0.0, 'S': -1.0, 'T': -1.0, 'V': -3.0, 'W': -3.0, 'Y': -2.0},
 'F': {'A': -3.0, 'C': -2.0, 'D': -5.0, 'E': -3.0, 'F': 8.0, 'G': -4.0, 'H': -1.0, 'I': 0.0, 'K': -4.0, 'L': 1.0, 'M': 0.0, 'N': -4.0, 'P': -4.0, 'Q': -4.0, 'R': -3.0, 'S': -3.0, 'T': -2.0, 'V': -1.0, 'W': 1.0, 'Y': 4.0},
 'G': {'A': 0.0, 'C': -3.0, 'D': -1.0, 'E': -3.0, 'F': -4.0, 'G': 8.0, 'H': -2.0, 'I': -4.0, 'K': -2.0, 'L': -4.0, 'M': -3.0, 'N': 0.0, 'P': -2.0, 'Q': -2.0, 'R': -3.0, 'S': 0.0, 'T': -2.0, 'V': -4.0, 'W': -3.0, 'Y': -3.0},
 'H': {'A': -2.0, 'C': -3.0, 'D': -1.0, 'E': 0.0, 'F': -1.0, 'G': -2.0, 'H': 10.0, 'I': -4.0, 'K': 0.0, 'L': -3.0, 'M': -1.0, 'N': 1.0, 'P': -2.0, 'Q': 1.0, 'R': 0.0, 'S': -1.0, 'T': -2.0, 'V': -4.0, 'W': -3.0, 'Y': 2.0},
 'I': {'A': -1.0, 'C': -2.0, 'D': -4.0, 'E': -4.0, 'F': 0.0, 'G': -4.0, 'H': -4.0, 'I': 5.0, 'K': -3.0, 'L': 2.0, 'M': 2.0, 'N': -3.0, 'P': -3.0, 'Q': -3.0, 'R': -4.0, 'S': -3.0, 'T': -1.0, 'V': 4.0, 'W': -3.0, 'Y': -1.0},
 'K': {'A': -1.0, 'C': -3.0, 'D': -1.0, 'E': 1.0, 'F': -4.0, 'G': -2.0, 'H': 0.0, 'I': -3.0, 'K': 6.0, 'L': -3.0, 'M': -2.0, 'N': 0.0, 'P': -1.0, 'Q': 2.0, 'R': 3.0, 'S': 0.0, 'T': -1.0, 'V': -3.0, 'W': -3.0, 'Y': -2.0},
 'L': {'A': -2.0, 'C': -2.0, 'D': -4.0, 'E': -3.0, 'F': 1.0, 'G': -4.0, 'H': -3.0, 'I': 2.0, 'K': -3.0, 'L': 5.0, 'M': 3.0, 'N': -4.0, 'P': -4.0, 'Q': -2.0, 'R': -3.0, 'S': -3.0, 'T': -1.0, 'V': 1.0, 'W': -2.0, 'Y': -1.0},
 'M': {'A': -1.0, 'C': -2.0, 'D': -4.0, 'E': -2.0, 'F': 0.0, 'G': -3.0, 'H': -1.0, 'I': 2.0, 'K': -2.0, 'L': 3.0, 'M': 7.0, 'N': -2.0, 'P': -3.0, 'Q': 0.0, 'R': -2.0, 'S': -2.0, 'T': -1.0, 'V': 1.0, 'W': -1.0, 'Y': 0.0},
 'N': {'A': -1.0, 'C': -2.0, 'D': 2.0, 'E': 0.0, 'F': -4.0, 'G': 0.0, 'H': 1.0, 'I': -3.0, 'K': 0.0, 'L': -4.0, 'M': -2.0, 'N': 7.0, 'P': -2.0, 'Q': 0.0, 'R': -1.0, 'S': 1.0, 'T': 0.0, 'V': -3.0, 'W': -4.0, 'Y': -2.0},
 'P': {'A': -1.0, 'C': -4.0, 'D': -1.0, 'E': -1.0, 'F': -4.0, 'G': -2.0, 'H': -2.0, 'I': -3.0, 'K': -1.0, 'L': -4.0, 'M': -3.0, 'N': -2.0, 'P': 10.0, 'Q': -1.0, 'R': -3.0, 'S': -1.0, 'T': -1.0, 'V': -3.0, 'W': -4.0, 'Y': -3.0},
 'Q': {'A': -1.0, 'C': -3.0, 'D': 0.0, 'E': 2.0, 'F': -4.0, 'G': -2.0, 'H': 1.0, 'I': -3.0, 'K': 2.0, 'L': -2.0, 'M': 0.0, 'N': 0.0, 'P': -1.0, 'Q': 7.0, 'R': 1.0, 'S': 0.0, 'T': -1.0, 'V': -3.0, 'W': -1.0, 'Y': -1.0},
 'R': {'A': -2.0, 'C': -4.0, 'D': -2.0, 'E': 0.0, 'F': -3.0, 'G': -3.0, 'H': 0.0, 'I': -4.0, 'K': 3.0, 'L': -3.0, 'M': -2.0, 'N': -1.0, 'P': -3.0, 'Q': 1.0, 'R': 7.0, 'S': -1.0, 'T': -1.0, 'V': -3.0, 'W': -3.0, 'Y': -1.0},
 'S': {'A': 1.0, 'C': -1.0, 'D': 0.0, 'E': -1.0, 'F': -3.0, 'G': 0.0, 'H': -1.0, 'I': -3.0, 'K': 0.0, 'L': -3.0, 'M': -2.0, 'N': 1.0, 'P': -1.0, 'Q': 0.0, 'R': -1.0, 'S': 5.0, 'T': 2.0, 'V': -2.0, 'W': -4.0, 'Y': -2.0},
 'T': {'A': 0.0, 'C': -1.0, 'D': -1.0, 'E': -1.0, 'F': -2.0, 'G': -2.0, 'H': -2.0, 'I': -1.0, 'K': -1.0, 'L': -1.0, 'M': -1.0, 'N': 0.0, 'P': -1.0, 'Q': -1.0, 'R': -1.0, 'S': 2.0, 'T': 5.0, 'V': 0.0, 'W': -3.0, 'Y': -2.0},
 'V': {'A': 0.0, 'C': -1.0, 'D': -4.0, 'E': -3.0, 'F': -1.0, 'G': -4.0, 'H': -4.0, 'I': 4.0, 'K': -3.0, 'L': 1.0, 'M': 1.0, 'N': -3.0, 'P': -3.0, 'Q': -3.0, 'R': -3.0, 'S': -2.0, 'T': 0.0, 'V': 5.0, 'W': -3.0, 'Y': -1.0},
 'W': {'A': -3.0, 'C': -5.0, 'D': -5.0, 'E': -3.0, 'F': 1.0, 'G': -3.0, 'H': -3.0, 'I': -3.0, 'K': -3.0, 'L': -2.0, 'M': -1.0, 'N': -4.0, 'P': -4.0, 'Q': -1.0, 'R': -3.0, 'S': -4.0, 'T': -3.0, 'V': -3.0, 'W': 15.0, 'Y': 2.0},
 'Y': {'A': -2.0, 'C': -3.0, 'D': -3.0, 'E': -2.0, 'F': 4.0, 'G': -3.0, 'H': 2.0, 'I': -1.0, 'K': -2.0, 'L': -1.0, 'M': 0.0, 'N': -2.0, 'P': -3.0, 'Q': -1.0, 'R': -1.0, 'S': -2.0, 'T': -2.0, 'V': -1.0, 'W': 2.0, 'Y': 8.0}}

After defining this, you can look up scores in the 2D dictionary as follows::

    print blosum50['Y']['W']
    print blosum50['D']['W']
    print blosum50['A']['A']

We'll use this matrix to score some alignments and to explore the Needleman-Wunsch and Smith-Waterman alignment algorithms.

Nested for loops
================

Sometimes one for loop isn't enough. For example, maybe you have you two lists and you need to perform some operation on all pairs of elements in those two lists. One application of this is in sequence alignment, where we need to compare all pairs of positions to compute alignment scores. In this example we'll look at how that might be computed.

Imagine we're starting with two sequences and we want to compute a scoring matrix to use for aligning those two sequences::

    # Define the sequences we want to align
    seq1 = "HEAGAWGHEE"
    seq2 = "PAWHEAE"

    # Initialize a matrix to use for storing the scores
    match_matrix = []
    # Iterate over the amino acids in sequence two (which will correspond 
    # to the vertical sequence in the matrix)
    for aa2 in seq2:
        # Initialize the current row of the matrix
        current_row = []
        # Iterate over the amino acids in sequence one (which will 
        # correspond to the horizontal sequence in the matrix)
        for aa1 in seq1:
            # score each position in the matrix according to it's value in
            # blosum50
            current_row.append(blosum50[aa1][aa2])
        # append the current row to the matrix
        match_matrix.append(current_row)

You can now print out ``match_matrix``. You can do that in a simply way with the following code::

    for row in match_matrix:
        print row

Or you can get fancy and print it in a prettier way::

    # define a format string that will be used to format each line - 
    # since seq1 is the 'horizontal' sequence in our matrix we'll 
    # have len(seq1) + 1 entries on each line to print the scores and 
    # seq2 base associated with each row
    line_format = "%6s" * (len(seq1) + 1)
    
    # print seq1 (start the line with an empty string)
    print line_format % tuple([' '] + map(str,list(seq1)))
    
    # iterate over the rows and print each (starting with the 
    # corresponding base in sequence2)
    for row, base in zip(match_matrix,seq2):
        print line_format % tuple([base] + map(str,row))
        
The formatting sting ``%6s`` prints a string using exactly six characters (padded with spaces), so that allows us to nicely align the columns. 



