================================================================================================
Lecture 7: Molecular evolution and introduction to sequence searching and phylogenetic inference
================================================================================================

Return and review quiz 2.

Homework due 9/27: BLASTing through Kingdom of Life.

Three features of evolutionary processes: descent, variation, and selection.

Why might a deleterious mutation propagate through a population? `Sickle-cell anemia example <http://www.nature.com/scitable/topicpage/sickle-cell-anemia-a-look-at-global-8756219>`_. 

Working with lists and for loops: an example based on simulating sequence evolution.


Working with lists
==================

Defining lists
^^^^^^^^^^^^^^

Lists can be defined directly, or using a few different functions as follows::
    
    # direct creation of a list
    l1 = [0,2,3,5,6]
    # create a list of the numbers 0-9
    l2 = range(10)
    # create a list of the numbers 25-49
    l3 = range(25,50)
    # create a list of the characters in the word "darwin"
    l4 = list("darwin")

Try each of these and print the list (``print l``) to see what the resulting list looks like. How would you create a list like ``l2`` or ``l3`` with the items in reverse order? There are a few ways -- google this and try out of them.

Adding an element to a list
^^^^^^^^^^^^^^^^^^^^^^^^^^^

You can add an element to a list using the ``append`` method of the list. For example, to add to list ``l1``::

    l1.append(42)
    
If you ``print l1`` before and after running this command you'll see that you added a new entry to the end of ``l1``.

Accessing elements of a list
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Once you've created a list you can access the `elements` of that list by their `index` in the list. These indexes begin at zero, so the first element in ``l1`` is accessed as ``l1[0]``. What happens if you access an element that doesn't exist? For example, ``l1[99]``. Try it out. You can also access the end of the list by using negative indices such as ``l1[-1]``, ``l1[-2]``, and so on.

Working with for loops
======================

We briefly talked about ``for`` loops at the end of our last class. These are useful for applying the same piece of code several times.

Common methods for acting on lists with for loops
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Frequently you need to iterate over all entries in a list and apply some operation to that entry. Here's a common way to do that::

    l = range(10)
    for i in range(len(l)):
        l[i] = l[i] * -1
    print l

What does the ``len`` function do here? What does this block of code do as a whole? ``i`` is commonly used to represent the index in a list, as in the above example.


If you don't need to actually modify a list, you can access the entries with a ``for`` loop directly. For example::

    l = range(10)
    for entry in l:
        print entry

Here ``e`` is iteratively set to each entry in l, and an operation (``print`` in this case) is applied to that entry. In this example I'm referring to each element in the list as ``entry``. You should always pick a descriptive name like this for your variables -- it makes reading your code easier. 

Iterating over multiple lists at the same time
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

There are cases where you may want to iterate over two (or more) lists with the same number of entries at the same time. The ``zip`` function is useful for this. For example, imagine you wanted to iterate over two sequences to count the number of positions they differed in::

    sequence1 = 'ACCTT'
    sequence2 = 'AGCTA'
    difference_count = 0
    for base1, base2 in zip(sequence1,sequence2):
        if base1 != base2:
            difference_count += 1
    return difference_count

If this doesn't make sense try typing the above but adding a print statement just after the ``for`` loop begins that will print ``base1`` and ``base2``. That should clear up what is happening. 

Related python idioms
=====================

Converting strings to lists and lists to strings
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Frequently you'll need to convert a string to a list. This is easy::

    dna_string = 'ACCGGT'
    dna_list = list(dna_string)
    

The opposite is a little trickier::

    dna_list = ['A','C','C','G','T']
    dna_string = ''.join(dna_list)
    
This tells python to join all the elements in the list with the `empty string` (i.e., a string of length zero). (You could also use this to generate a comma-separated string, for example. How would you do that?)

Enumerating the entries in a list
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Another common thing you'll need to do is enumerate the entries in a list and iterate over the entries and the index of that entry. You can do this using the ``enumerate`` function in your ``for`` loop. For example::

    for sequence_number,sequence in enumerate(sequences):
        print ">seq%d\n%s\n" % (sequence_number,sequence)

The result of this block of code should be familiar to you - what is it?

