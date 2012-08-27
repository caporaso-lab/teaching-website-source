=============================================================
Lecture 13: Introduction to PyCogent: Building a tree of life
=============================================================

Assignment of groups for application presentations

Organization of study sessions: organizers will earn participation points

Discussion of homework assignment

Amazon Web Services: Will be accessible for projects in the second half of this semester

Python modules
 - matplotlib: graphing functionality
 - PyCogent: Bioinformatics toolkit

Steps in constructing a phylogeny based on molecular sequence data
 1. Select a sequence of interest: why might you choose a particular sequence? 
 2. Identify homologs: sequencing or database searching (we'll search for sequences in NCBI)
 3. Align sequences: performing a multiple sequence alignment (we'll use muscle)
 4. Calculate phylogeny: phylogeny reconstruction methods (we'll use FastTree)

Coding example
--------------

matplotlib
^^^^^^^^^^

matplotlib is a graphing module that is not included in the Python Standard Library. To use matplotlib you'll need to install it. 

This module provides a good illustration of the functionality that is available to you via python which you don't have to implement yourself. This code here allows you to visualize a set of randomly generated scatter plots - look through the plots that are generated and think about how many you would consider the x and the y values to appear correlated. I find it alarming how many of these randomly generated plots look correlated. Keep this in mind as you read papers and analyze data.

::
    
    from pylab import scatter, figure, show
    from random import randrange

    def get_n_random_values(n,range_min=0,range_max=200):
        result = []
        for i in range(n):
            result.append(randrange(range_min,range_max))
        return result


    for i in range(20):
        figure(i)
        scatter(get_n_random_values(10),
                get_n_random_values(10))
        show()


PyCogent
^^^^^^^^

The Python Comparative GENomics Toolkit (PyCogent) is a python module that supports many bioinformatics applications, and is the basis for many other bioinformatics software packages. We'll work through an example that illustrates some powerful features of PyCogent, and will spend more time on specific components later in the semester and in Bio/CS 399 next semester.

You can find my PyCogent tree of life demo `here <http://dl.dropbox.com/u/2868868/pycogent_160dev_docs/cookbook/building_a_tree_of_life.html>`_.




