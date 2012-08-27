================================================================================================
Lecture 8: Simple model of evolution and introduction to sequence alignment
================================================================================================

Sequence alignment: each position in a sequence is treated as an independent character state. Alignments represent a hypothesis about homology of the sequences themselves, and positional homology across the sequences. Alignments are used in generating input for phylogenetic tree construction and database searching.
 - Local versus global alignments
 - Primary structure alignments: De novo alignment, Reference-based alignment
 - Secondary/tertiary structure alignments: Structure-based alignment


Challenges in Phylogenetic Inference:
 - homoplasy: occurrence of similarities not due to common ancestry (convergent and parallel evolution)
 - unequal rates of evolution: mutations may occur more in certain branches of "the tree"
 - nonvertical evolution: a branching tree is often an oversimplification of actual evolutionary processes (e.g., due to horizontal gene transfer)

Why molecular sequence data rather than morphological data?
 - cost of sequencing has dropped: now the cheapest data to collect for inferring phylogeny
 - discrete character states (4 nucleotides, 20 amino acids) makes molecular sequence data more straight-forward to work with than morphological data


.. _sequence-evolution-script:

Script to model sequence evolution
==================================

Here we'll apply some of the above techniques to create a very basic model sequence evolution. You can copy and paste this code to run it on your own::

    # import some functions from python's random module - these will
    # be used in the modeling process
    from random import choice, randint
    # import some math functions from the numpy library (note that this 
    # isn't part of the python standard library)
    from numpy import log10, average
    # import argv from the sys module to support basic command line 
    # control of this script
    from sys import argv

    #####
    # Start of function definitions
    #####

    def count_differences(sequence1,sequence2):
         """Count the number of differences between two sequences of the same length
         """
         # confirm that the two sequences are the same length and throw
         # an error if they aren't
         assert len(sequence1) == len(sequence2), "Sequences differ in length"
         # initiate a counter for the number of differences
         result = 0
         # iterate over the two sequences and count the number of
         # positions which are not identical
         for base1,base2 in zip(sequence1,sequence2):
             if base1 != base2:
                 # this is a commonly used shortcut for incrementing a count
                 # and is equivalent to the following statement
                 # result = result + 1 
                 result += 1
         return result
 
    def evolve_seq(sequence,
                   substitution_probability=0.01,
                   mutation_choices=['A','C','G','T']):
        """Return two child sequences simulating point mutations
    
           An error occurs with probability substitution_probability 
            independently at each position of each child sequence.
        """
        # Generate two lists for storing the resulting sequences
        r1 = []
        r2 = []

        range_length = 10 ** (-1 * log10(substitution_probability))

        for base in sequence:
            if randint(0,range_length) == 0:
                # a point mutation will occur at this position
                # what's wrong with the following statement?
                r1.append(choice(mutation_choices))
            else:
                # no point mutation at this position
                r1.append(base)
            if randint(0,range_length) == 0:
                # a point mutation will occur at this position
                # what's wrong with the following statement?
                r2.append(choice(mutation_choices))
            else:
                # no point mutation at this position
                r2.append(base)
        # convert the lists to strings and return them
        return ''.join(r1), ''.join(r2)

    def main(root_sequence,generations,verbose=False):
        # initial some values and perform some basic error checking
        assert generations > 0, "Must simulate one or more generations."
        # can you simplify the following test?
        for base in root_sequence:
            assert base != 'A' or base != 'C' or base != 'G' or base != 'T',\
             "Invalid base identified: %s. Only A, C, G, or T are allowed." % base
        # initialize a list of the previous generations sequences - this gets used
        # in the for loop below. since we'll start with the first generation of 
        # children, root_sequence is the previous generation's sequence
        previous_generation_sequences = [root_sequence]

        # iterate over each generation (why do we add one to generations?)
        for i in range(1,generations+1):
            # print the generation number and the current number of sequences
            print "Generation: %d (Number of child sequences: %d)" % (i,2**i)
            # create a list to store the current generation of sequences
            current_generation_sequences = []
            # create a list to store the differences in each current generation 
            # sequence from the root sequence
            difference_counts = []
            # iterate over the sequences of the previous generation
            for parent_sequence in previous_generation_sequences:
                # evolve two child sequences
                r1, r2 = evolve_seq(parent_sequence)
                # count the differences in the first sequence (from root_sequence)
                r1_diffs = count_differences(root_sequence,r1)
                # append the count of differences to the list of difference counts
                difference_counts.append(r1_diffs)
                # add the new sequence to the list of this generation's sequences
                current_generation_sequences.append(r1)
                # count the differences in the second sequence (from root_sequence)
                r2_diffs = count_differences(root_sequence,r2)
                # append the count of differences to the list of difference counts
                difference_counts.append(r2_diffs)
                # add the new sequence to the list of this generation's sequences
                current_generation_sequences.append(r2)
                if verbose:
                    # if the caller specified verbose output, print the actual sequences
                    print "  %s %d" % (r1, r1_diffs)
                    print "  %s %d" % (r2, r2_diffs)
            # print summary information: the average number of differences in the current
            # generation from root_sequence
            print "Mean differences %1.3f\n" % average(difference_counts)
            # current_generation_sequences becomes the next generation's 
            # previous_generation_sequences
            previous_generation_sequences = current_generation_sequences
    
        # upon completion of all generations, return the last generation's sequences
        return previous_generation_sequences

    #####
    # End of function definitions
    #####

    #####
    # Start main execution block
    #####

    script_name, sequence_length, num_generations, output_filepath = argv

    # generate a random sequence composed of ['A', 'C', 'G', 'T'] 
    # of length sequence_length
    root_sequence = []
    for i in range(int(sequence_length)):
        root_sequence.append(choice(list('ACGT')))
    root_sequence = ''.join(root_sequence)

    # run the simulation and get the final generation of sequences
    sequences = main(root_sequence,int(num_generations))

    # write the final generation of sequences to a fasta file
    output_f = open(output_filepath,'w')
    for i,s in enumerate(sequences):
        output_f.write('>seq%d\n%s\n' % (i,s))
    output_f.close()

    #####
    # End main execution block
    #####


