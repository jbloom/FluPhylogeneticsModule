=============================================
FluPhylogeneticsModule
=============================================

``README`` for the `FluPhylogeneticsModule`_ GitHub repository.

This repository contains information for a high-school level educational module that uses phylogenetics to understand a flu pandemic.

This module was created by `Jesse Bloom`_, `Trevor Bedford`_, and `Greg Ballog`_


Making the slides
---------------------

These slides are written in `reStructuredText`_ and compiled with `hieroglyph`_ (a `Python`_ package).

To compile the slides, you need to first install `hieroglyph`_ on your computer::

    easy_install hieroglyphy

and then make the slides with::

    make slides

The slides are in the home directory, while the source is in the ``./source/`` subdirectory.

When this repository is pushed to the ``gh_pages`` branch of the `FluPhylogeneticsModule`_ GitHub repository, the slides will become available on ``GitHub Pages``. 

For example, a file named ``./source/slides.rst`` will compile to ``slides.html`` with the ``make slides`` command, and after the pushing to the `FluPhylogeneticsModule`_ repository, the slides will be available for viewing at http://jbloom.github.io/FluPhylogeneticsModule/slides.html.

Advance through the slides with the arrow keys.

.. _`hieroglyph`: http://docs.hieroglyph.io/en/latest/index.html
.. _`reStructuredText`: http://docutils.sourceforge.net/rst.html
.. _`Python`: https://www.python.org/
.. _`FluPhylogeneticsModule`: https://github.com/jbloom/FluPhylogeneticsModule
.. _`Jesse Bloom`: http://research.fhcrc.org/bloom/en.html
.. _`Trevor Bedford`: http://bedford.io/blog/
.. _`Greg Ballog`: http://www.sw.wednet.edu/page/581
