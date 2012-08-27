=================================================
Lecture 2: The Central Dogma of Molecular Biology
=================================================

**Additional discussion on the structure of the course**

* NAU Bioinformatics Track.

* QIIME Virtual Machine: a way to work with python if you don't want to deal with Windows. Details `here <http://qiime.org/install/virtual_box.html>`_.

* Programming notebooks: A lot of questions about what is expected here. I put a page together with notes on these `here <../assignment_details.html>`_. Graded homework assignments will also be posted to this page.

**The Central Dogma of Molecular Biology (DNA to RNA to Protein)**

* What is the `Central Dogma` and what is the role of each component?
* Transcription, translation, and the genetic code (note that genomic sequences `are not` the genetic code).
* Redundancy in the genetic code; start and stop codons.

.. note:: 
    Nucleic acid and protein sequences have an inherent orientation. The standard is to always write nucleic acid sequences from their ``5'`` (pronounced `five-prime`) end to their ``3'`` (pronounced `three-prime`) end and protein sequences from their N-terminus to their C-terminus. You should always do this, but if for some technical reason you can't (e.g., a figure in a paper that requires a specific orientation) you should make it very clear what the orientation is. A good way to write out nucleic acid sequences that explicitly incorporates the orientation of the sequence is like this:
    
    ``5'- GTTTATCCATCGTGCGTC -3'``


**Let's write some code...**

First, let's look at how you would convert a DNA sequence to an RNA sequence. Remember that RNA uses uracil (``U``) and DNA uses thymine (``T``). You can convert a DNA sequence to an RNA sequence as follows::

    "GTTTATCCATCGTGCGTC".replace('T','U')

This illustrates the process of transcription from DNA to RNA. 

Now, how did I know that I could call ``replace`` on this string? Check out the python documents on strings by going to `www.python.org <www.python.org>`_ and searching for ``string``. You can also access python's built-in help by running::

    help(str) 

Or, you can access help on specific methods in either of these ways::

    help("ACCG".replace)
    help(str.replace)

Next let's do something a little harder. Given a DNA sequence, how would convert to the sequence that it pairs with? You'd need to apply a few steps - first you'd need to complement the sequence, meaning that ``A`` is converted to ``T``, ``T`` to ``A``, ``G`` to ``C``, and ``C`` to ``G``. You could do this as follows::

	"GTTTATCCATCGTGCGTC".replace('A','u').replace('T','a').replace('G','c').replace('C','g')

What is going on with this series of replace statements? Break the code apart and try to figure it out.

You'll notice that our sequence is now lowercase. Why did I do that? To convert it to uppercase, you could run the following::

	"GTTTATCCATCGTGCGTC".replace('A','u').replace('T','a').replace('G','c').replace('C','g').upper()

So now we have the complement of our sequence, but we don't want to report the sequence this way because the orientation is backwards. (Since the starting sequence ran from ``5'`` to ``3'``, this sequence runs in the opposite orientation: ``3'`` to ``5'`. What we really want is the `reverse complement` of the sequence (commonly abbreviated `RC`). So the second step in this process is to reverse the complemented sequence to give us the reverse complement. To do that we need to include what will look like a bit of magic right now::

	"GTTTATCCATCGTGCGTC".replace('A','u').replace('T','a').replace('G','c').replace('C','g').upper()[::-1]

The ``[::-1]`` syntax makes use of what is known as ``Extended Slices`` (google it if you'd like more details). Don't worry about this too much for right now - we'll come back to it later in the course when we start working with lists. For now, treat it like magic.

The next thing we might want to do is code translation of an mRNA sequence to a protein. This is a little more complicated: we need to use something called a dictionary here (see LPTHW exercise 40), so we'll come back to this a little bit later.


.. Possibly "Basic principals of sequence evolution" from lecture 3, so prep that material for Thursday.

