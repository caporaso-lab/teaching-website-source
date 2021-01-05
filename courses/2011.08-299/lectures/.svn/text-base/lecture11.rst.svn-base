================================================
Lecture 11: Alignments and phylogenetic trees
================================================

Review Needleman-Wunsch python implementation (below).

Discuss homework assignment for Thursday Oct 13th.

Introduce phylogenetic trees and the UPGMA algorithm.

Python coding examples
======================

Needleman-Wunsch implementation in python
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

To run this Needleman-Wunsch implementation, save the copy and paste the code to a new py file. You'll this to :download:`download this file <../py/substitution_matrices.py>` to the same directory to support the importing of the blosum50 matrix.

::

    from __future__ import division
    from random import choice
    from substitution_matrices import blosum50

    ##############
    # Start function and variable definitions
    ##############

    def generate_score_matrix(seq1,seq2,substitution_matrix):
        # Initialize a matrix to use for storing the scores
        score_matrix = []
        # Iterate over the amino acids in sequence two (which will correspond 
        # to the vertical sequence in the matrix)
        for aa2 in seq2:
            # Initialize the current row of the matrix
            current_row = []
            # Iterate over the amino acids in sequence one (which will 
            # correspond to the horizontal sequence in the matrix)
            for aa1 in seq1:
                # score as 1 if the bases are equal and 0 if they're not
                current_row.append(blosum50[aa1][aa2])
            # append the current row to the matrix
            score_matrix.append(current_row)
        return score_matrix

    def generate_nw_and_traceback_matrices(seq1,seq2,gap_penalty,substitution_matrix):

        # Initialize a matrix to use for scoring the alignment and for tracing
        # back the best alignment
        nw_matrix = [[-gap_penalty * i for i in range(0,len(seq1)+1)]]
        traceback_matrix = [[None] + ['-' for i in range(0,len(seq1))]]
        # Iterate over the amino acids in sequence two (which will correspond 
        # to the vertical sequence in the matrix)
        # Note that i corresponds to column numbers, as in the 'Biological Sequence 
        # Analysis' example from class
        for i,aa2 in zip(range(1,len(seq2)+1),seq2):
            # Initialize the current row of the matrix
            current_row = [i * -gap_penalty]
            current_traceback_matrix_row = ['|']
            # Iterate over the amino acids in sequence one (which will 
            # correspond to the horizontal sequence in the matrix)
            # Note that j corresponds to row numbers, as in the 'Biological Sequence 
            # Analysis' example from class
            for j,aa1 in zip(range(1,len(seq1)+1),seq1):
                substitution_score = substitution_matrix[aa1][aa2]
                diag_score = (nw_matrix[i-1][j-1] + substitution_score,'\\')
                up_score = (nw_matrix[i-1][j] - gap_penalty,'|')
                left_score = (current_row[-1] - gap_penalty,'-')
                best_score = max(diag_score,up_score,left_score)
                current_row.append(best_score[0])
                current_traceback_matrix_row.append(best_score[1])
            # append the current row to the matrix
            nw_matrix.append(current_row)
            traceback_matrix.append(current_traceback_matrix_row)
        return nw_matrix, traceback_matrix

    def nw_traceback(traceback_matrix,nw_matrix,seq1,seq2,gap_character='-'):
    
        aligned_seq1 = []
        aligned_seq2 = []
    
        current_row = len(traceback_matrix) - 1
        current_col = len(traceback_matrix[0]) - 1
    
        best_score = nw_matrix[current_row][current_col]
    
        while True:
            current_value = traceback_matrix[current_row][current_col]
        
            if current_value == '\\':
                aligned_seq1.append(seq1[current_col-1])
                aligned_seq2.append(seq2[current_row-1])
                current_row -= 1
                current_col -= 1
            elif current_value == '|':
                aligned_seq1.append('-')
                aligned_seq2.append(seq2[current_row-1])
                current_row -= 1
            elif current_value == '-':
                aligned_seq1.append(seq1[current_col-1])
                aligned_seq2.append('-')
                current_col -= 1
            elif current_value == None:
                break
            else:
                raise ValueError, "Invalid value in traceback matrix: %s" % current_value
        
        return ''.join(aligned_seq1[::-1]), ''.join(aligned_seq2[::-1]), best_score

    def format_score_matrix(seq1,seq2,score_matrix,title):
        # define a format string that will be used to format each line - 
        # since seq1 is the 'horizontal' sequence in our matrix we'll 
        # have len(seq1) + 1 entries on each line to print the scores and 
        # seq2 base associated with each row
        line_format = "%6s" * (len(seq1) + 1)

        print "\n%s" % title

        # print seq1 (start the line with an empty string)
        print line_format % tuple([' '] + map(str,list(seq1)))

        # iterate over the rows and print each (starting with the 
        # corresponding base in sequence2)
        for row, base in zip(score_matrix,seq2):
            print line_format % tuple([base] + map(str,row))

    def format_dynamic_programming_matrix(seq1,seq2,matrix,title):
        print "\n%s" % title

        line_format = "%6s" * (len(seq1) + 2)
        # print seq1 (start the line with two empty strings)
        print line_format % tuple([' ',' '] + map(str,list(seq1)))

        # iterate over the rows and print each (starting with the 
        # corresponding base in sequence2)
        for row, base in zip(matrix,' ' + seq2):
            print line_format % tuple([base] + map(str,row))


    ##############
    # End function and variable definitions
    ##############


    ##############
    # Start main execution block
    ##############
    def main():
        seq1 = "HEAGAWGHEE"
        seq2 = "PAWHEAE"

        score_matrix = generate_score_matrix(seq1,seq2,blosum50)

        format_score_matrix(seq1,
                            seq2,
                            score_matrix,
                            title="Score matrix (based on BLOSUM50)")


        nw_matrix, traceback_matrix = generate_nw_and_traceback_matrices(seq1,
                                                                         seq2,
                                                                         8,
                                                                         blosum50)

        aligned_seq1, aligned_seq2, score = nw_traceback(traceback_matrix,nw_matrix,seq1,seq2)

        format_dynamic_programming_matrix(seq1,
                                          seq2,
                                          nw_matrix,
                                          title="Global dynamic programming matrix")

        format_dynamic_programming_matrix(seq1,
                                          seq2,
                                          traceback_matrix,
                                          title="Traceback matrix")


        print "\nAlignment:"

        print aligned_seq1
        print aligned_seq2
        print '\nAlignment score:'
        print score

    if __name__ == "__main__":
        main()

    ##############
    # End main execution block
    ##############




Example of computing a distance matrix in python for use in UPGMA
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

::

    def count_differences(sequence1,sequence2):
        difference_count = 0
        for base1, base2 in zip(sequence1,sequence2):
            if base1 != base2:
                difference_count += 1
        return difference_count

    def format_dm(dm,title):
        line_format = "%6s" * (len(dm) + 1)
        print "\n%s" % title

        # print seq1 (start the line with an empty string)
        print line_format % tuple([' '] + ['s%d'%i for i in range(1,len(dm)+1)])
    
        # iterate over the rows and print each (starting with the 
        # corresponding base in sequence2)
        for row, row_number in zip(dm,range(1,len(dm)+1)):
            print line_format % tuple(['s%d' % row_number] + map(str,row))

    sequences = ["ACCGTGAAGCCAATAC",
                 "AGCGTGCAACCATTAC",
                 "AGCGTGCAGCCAATAC",
                 "AGGGTGCCGCTAATAC",
                 "AGGGTGCCACTAATAC"]

    dm = []
    for seq1 in sequences:
        current_row = []
        for seq2 in sequences:
            current_row.append(count_differences(seq1,seq2))
        dm.append(current_row)

    format_dm(dm,"Distance matrix")




Functions as values in dictionaries
===================================

This is covered in example 40, so need to cover now...


Chemistry demo: create a function (are we up to functions at this point in LPTHW?) to compute molecular weight from chemical formulas. Would also involve some complex string parsing. 

