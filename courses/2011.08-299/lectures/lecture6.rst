=============================================
Lecture 6: Molecular evolution
=============================================

Three features of evolutionary processes: descent, variation, and selection.

Basic principals of sequence evolution: new genes generated from old genes - `point mutations, insertion/deletions <http://www.nature.com/scitable/topicpage/dna-replication-and-causes-of-mutation-409>`_.

Duplications, crossing over, horizontal gene transfer.


Not all variation is adaptive (suggested reading: `The Spandrels of San Marco and the Panglossian Paradigm: A Critique of the Adaptationist Programme, by Stephen Jay Gould and Richard C. Lewontin <http://condor.wesleyan.edu/courses/2004s/ees227/01/spandrels.html>`_)






Coding: loops and lists
-----------------------

Importing functions from other files
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

A useful topic to briefly cover here is how to import functions, objects, etc. from other python files. To do that you can use the ``import`` statement. Today we're going to look at this to import from the ``random`` module and the ``__future__`` module, and model the idea of genetic drift. 

Start a python terminal and enter the following line::

    from __future__ import division

This performs floating point division when starting with integers, so ``1/2`` will equal ``0.5`` (a floating point value) rather than ``0`` (an integer value). 

.. warning:: It's a good idea to `always` add ``from __future__ import division`` to the top of your python scripts. Python 3 will include `true division`, but until then not adding this import statement can lead to bugs. Note that in python's default division *values are truncated, not rounded* so, for example, ``11/4 == 2``, not ``3`` as you would expect if python were rounding.

Genetic drift programming example
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

This example illustrates the concept of genetic drift in a population of genotypes. Imagine we start with four genotypes, ``A``, ``B``, ``C``, and ``D`` and 10,000 individuals. First, let's define a starting population with the following genotype frequencies::

     genotype_frequencies = ['A'] * 5000 + ['B'] * 2500 + ['C'] * 1250 + ['D'] * 1250

This syntax may be new to you. Break this apart to individual addends to figure out what the full statement is doing.

Next, let's define a function that will conveniently allow us to summarize this population::

    def summarize_composition(population):
        population_size = len(population)
        print 'A: %0.4f' % (population.count('A') / population_size)
        print 'B: %0.4f' % (population.count('B') / population_size)
        print 'C: %0.4f' % (population.count('C') / population_size)
        print 'D: %0.4f' % (population.count('D') / population_size)

Now run this function on the population that was just created::

    summarize_composition(genotype_frequencies)

You should get the following result -- if not, you did something wrong so go back and figure out what it was.

::

    A: 0.5000
    B: 0.2500
    C: 0.1250
    D: 0.1250


Next we're going to import the ``sample`` function from the ``random`` module. Given a list (``population``) and a number of elements (``k``) to select, ``sample`` randomly samples (without replacement) ``k`` elements from the list and returns those as a new list. So, if we sample the full population and summarize the genotype composition, we should get the same result -- let's test it out::

    from random import sample
    new_genotype_frequencies = sample(genotype_frequencies,10000)
    summarize_composition(new_genotype_frequencies)

Now, let's simulate genetic drift. Imagine we have a population of organisms with the genotype frequencies represented in our ``genotype_frequencies`` list. Regardless of which of these genotypes confers the most selective advantage a random removal of a large component from the population has the ability to affect the resulting genotypic composition. 

Simulate an event that randomly kills off 10% of the total population, and look at the resulting genotype composition::

    
    new_genotype_frequencies = sample(genotype_frequencies,9000)
    summarize_composition(new_genotype_frequencies)

Do this a few times. You should notice that the frequencies don't change a lot. What happens if instead of this relatively small dying off, there is a near-extinction event. Simulate an event that randomly kills off 99.9% of the population. What happens now? Run this simulation several times and explain the results of this experiment.

Working with loops: the for loop
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

In the next set of assignments you'll be introduced to loops. These allow you to perform an operation many times using a slightly different input each time. To continue our sequencing processing script, let's add a few new features that make use of a ``for`` loop.  We'll add a feature to our sequence processing script that allows a user to pass several sequences on the command line::

    from sys import argv
    script_name, sequences = argv

    sequences = sequences.split(',')

    def reverse_complement(sequence):
        return sequence.replace('A','t').replace('T','a').replace('G','c').replace('C','g').upper()[::-1]

    # iterate over the sequences and print the reverse complement 
    # of each to the command line
    for sequence in sequences:
        print reverse_complement(sequence)


