================================================================
Using phylogenetics to understand a virus pandemic 
================================================================

These slides are available at http://jbloom.github.io/FluPhylogeneticsModule/slides.html

Advance through the slides using the arrow keys.

These slides are for the high-school level class, and were created by `Jesse Bloom`_, `Trevor Bedford`_, and `Greg Ballog`_.


A new flu virus appears in the U.S.
======================================
On April 15, 2009, doctors in California detect a new strain of influenza in a 10-year old child. A few days later, a similar virus is found in another child in California.

A new flu virus appears in the U.S.
======================================
A week later, the `Centers for Disease Control (CDC) <http://www.cdc.gov/>`_ publishes an `article in Morbidity and Mortality Weekly Report <http://www.cdc.gov/mmwr/preview/mmwrhtml/mm5815a5.htm>`_ describing these infections:

    *On April 17, 2009, CDC determined that two cases of febrile respiratory illness occurring in children who resided in adjacent counties in southern California were caused by infection with a swine influenza A (H1N1) virus. The viruses from the two cases are closely related genetically... and contain a unique combination of gene segments that previously has not been reported among swine or human influenza viruses in the United States or elsewhere. Neither child had contact with pigs; the source of the infection is unknown.*


The virus spreads in the U.S.
======================================
On April 23, 2009, it is discovered that the virus has also infected people in Texas, as described in this `New York Times article <http://www.nytimes.com/2009/04/24/us/24flu.html>`_.

.. image:: images/2014-04-24_NYTimes.png

The virus is also in Mexico
======================================
It quickly becomes apparent that the virus is already circulating fairly extensively in Mexico, as described in this `New York Times article <http://www.nytimes.com/2009/04/25/world/americas/25mexico.html>`_.

.. image:: images/2014-04-25_NYTimes.png

The U.S. declares a public health emergency
==============================================
A few days later, the U.S. declares a health emergency, as described in this `New York Times article <http://www.nytimes.com/2009/04/27/world/27flu.html>`_.

.. image:: images/2014-04-27_NYTimes.png

The World Health Organization (WHO) declares a pandemic
=========================================================
Within six weeks, the virus has spread to at least 74 countries. The `WHO issues a declaration <http://www.who.int/mediacentre/news/statements/2009/h1n1_pandemic_phase6_20090611/en/>`_  that the virus is a `pandemic <http://en.wikipedia.org/wiki/Pandemic>`_, as reported in
this  `New York Times article <http://www.nytimes.com/2009/06/12/world/asia/12flu.html>`_.

.. image:: images/2014-06-12_NYTimes.png

Your goal
=========================================================
You will use techniques from `computational biology <http://en.wikipedia.org/wiki/Computational_biology>`_ to address two questions that scientists needed to answer when faced with this infection:

1) Is the virus resistant to the drug `Tamiflu <http://en.wikipedia.org/wiki/Oseltamivir>`_?

2) Where did the virus come from?

Some background on flu pandemics
=========================================================
"Flu" is the common name for `influenza <http://en.wikipedia.org/wiki/Influenza>`_, which is a virus that infects many species including birds, pigs, horses, humans, and dogs.

Watch `this video <http://www.niaid.nih.gov/topics/Flu/understandingFlu/Pages/pandemicVideo.aspx>`_ for some background on influenza `pandemics <http://en.wikipedia.org/wiki/Pandemic>`_.

Back to your goal
=========================================================
You will use techniques from `computational biology <http://en.wikipedia.org/wiki/Computational_biology>`_ to address two questions that scientists needed to answer when faced with this infection:

1) Is the virus resistant to the drug `Tamiflu <http://en.wikipedia.org/wiki/Oseltamivir>`_?

2) Where did the virus come from?

Is the virus resistant to Tamiflu?
=========================================================

One of the first questions scientists asked was whether the virus was resistant to `Tamiflu (also known by the chemical name oseltamivir) <http://en.wikipedia.org/wiki/Oseltamivir>`_, which is the most commonly used drug against influenza.

.. image:: images/Tamiflu.JPG

Is the virus resistant to Tamiflu?
=========================================================

`Earlier studies <http://www.ncbi.nlm.nih.gov/pmc/articles/PMC2671453/>`_ had shown that influenza of this type was resistant if it had a mutation of from His to Tyr at position 275 of the virus's neuraminidase protein (this mutation is called *His275Tyr*).

So did the new 2009 pandemic virus have the *His275Tyr* mutation? To answer this question, we need to learn a little bit about influenza's genes.

Background on influenza's genes
=========================================================
Influenza is an `RNA virus <http://en.wikipedia.org/wiki/RNA_virus>`_ that encodes its genes in the `negative sense <http://en.wikipedia.org/wiki/Sense_(molecular_biology)#Negative-sense>`_. This means that its genes are made of RNA (rather than the DNA used to make our genes) that needs to be copied into mRNA (positive sense) before it can be translated into protein::

    viral RNA -> mRNA -> protein

Using this knowledge, we will look at the neuraminidase gene for the strain A/California/07/2009 to see if it contains the Tamiflu-resistance mutation *His275Tyr*.

Is the virus resistant to Tamiflu?
=========================================================

Use the portion of the sequence below for neuraminidase to see whether `virus A/California/07/2009 <http://www.ncbi.nlm.nih.gov/nuccore/507593927>`_ has *His275* (Tamiflu will work) or the resistance mutation *His275Tyr* (Tamiflu will not work). To go from viral RNA to mRNA, using the base-pair rules (*A - U* and *C - G*). To go from mRNA to protein, use the `genetic code <http://en.wikipedia.org/wiki/Genetic_code#RNA_codon_table>`_::

    viral RNA: 3'-...  cgg gga uua aua gug aua cuc cuu acg agg ...-5'
    mRNA:      5'-...  gcc ccu ??? ??? ??? ??? ??? ??? ??? ??? ...-3'
    protein:      ...  Ala ??? ??? ??? ??? ??? ??? ??? ??? ??? ...
    number:       ...  271 272 273 274 275 276 277 278 279 280 ...


**Exercise 1: Is this virus resistant to Tamiflu? If yes, what is a single-nucleotide mutation that would make it non-resistant? If no, what is a single-nucleotide mutation that would make it resistant?**

Where did the virus come from?
=========================================================
To answer this question, we will use `phylogenetics <http://en.wikipedia.org/wiki/Phylogenetics>`_.

A `phylogenetic tree <http://en.wikipedia.org/wiki/Phylogenetic_tree>`_ represents evolutionary histories.

Phylogenetic trees
============================
Geneology of the royal family.

.. image:: images/royalty_tree.png

Phylogenetic trees
============================
`Haeckel's tree of life <http://en.wikipedia.org/wiki/Tree_of_life_(biology)#Haeckel.27s_Tree_of_Life>`_ (1879).

.. image:: images/Haeckel_tree.jpg
   :width: 58%

Phylogenetic trees
============================
Tree of `eutherian mammals <http://en.wikipedia.org/wiki/Eutheria>`_ from `this paper <http://openi.nlm.nih.gov/detailedresult.php?img=3198400_pone.0026436.g004&req=4>`_.

.. image:: images/eutherian_tree.png
   :width: 47%

Phylogenetic trees
============================
Tree of influenza viruses taken from `here <http://jbloom.github.io/phyloExpCM/example_2014Analysis_Influenza_H1_HA.html>`_.

.. image:: images/influenza_tree.jpg
   :width: 120%

Using phylogenetics to determine the origin of the 2009 pandemic
==================================================================
You will build a phylogenetic tree to determine the origins of the 2009 pandemic virus.

You will do this using the `Influenza Research Database <http://www.fludb.org/>`_.

Register with the Influenza Research Database
==================================================================
1) Go to the webpage for the `Influenza Research Database <http://www.fludb.org/>`_.

2) Click on the button on the upper right that says ``Sign Up!`` to create an account (or if you already created an account, click ``Sign In``).

3) You are now officially registered with the `Influenza Research Database <http://www.fludb.org/>`_!

Assemble a set of virus sequences
==================================================================
1) After signing in, go to the homepage of the `Influenza Research Database <http://www.fludb.org/>`_.

2) Click on the option under ``Search`` that says ``Sequences & Strains``.

3) Click on the ``ADVANCED OPTIONS`` button at lower left.

4) Select the option that says ``Keyword search``.

5) In the box on the right that says ``in All``, change this to ``in Unique Sample Identifier``.

6) Enter the following list identifiers (separated by commas) in the empty white search box::
    
    FJ966082, CY121680, EU604689, CY022477, CY022333, CY036799, 
    CY026283, FJ986620, CY021725, AB671289, CY014968, EU735802    

Saving your sequence set
=================================
1) You should now have a set of sequences that like this:

.. image:: images/SequenceSet.png
   :align: right
   :width: 90%

2) Click on ``Select all 12 segments``, and then click ``Add to Working Set`` and save them as ``flu sequences``. You have now saved the sequences on your workbench.

Examining your sequence set
================================
1) Click on the ``Workbench`` button at the top of the `Influenza Research Database <http://www.fludb.org/>`_.

2) On the list of analyses, click on ``View`` next to the ``flu sequences`` sequence set that you saved.

3) Look at the names. Flu sequences from humans are named like this::

    A/Location/Number/Date (such as A/California/04/2009)

   while sequences from other species are named like this::
       
    A/Species/Location/Number/Date (such as A/swine/Iowa/17672/1988)

Examining your sequence set
================================
We will now look at the composition of the sequence set that you have saved.

**Exercise 2: How many of the sequences come from humans? How many from pigs? How many from birds? What is the date of the earliest sequence?**

Building a phylogenetic tree
================================
In your sequence set, there are two sequences from the 2009 outbreak in California. These sequences are ``A/California/04/2009`` and ``A/California/07/2009``.

The rest of the sequences are from pigs, from birds, or from another earlier strain of flu that was already infecting humans.

**Exercise 3: Based on the news articles we discussed earlier, make a hypothesis about the phylogenetic tree. To which sequence(s) do you think the 2009 sequences from California will be most closely related?**

    
More details
============================
The exercises that you have just performed are a simpler version of the studies that scientists actually performed to understand the 2009 swine-origin H1N1 influenza pandemic.

If you are interested, you can read about the similar but more complex analyses that scientists actually performed to study this virus outbreak by looking at `this paper <http://www.nature.com/nature/journal/v459/n7250/full/nature08182.html>`_ and `this website <http://tree.bio.ed.ac.uk/groups/influenza/>`_.



.. _`Jesse Bloom`: http://research.fhcrc.org/bloom/en.html
.. _`Trevor Bedford`: http://bedford.io/blog/
.. _`Greg Ballog`: http://www.sw.wednet.edu/page/581
