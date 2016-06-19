---
layout: default
title: Open-source software
---

# Open-source software

This page describes some of the open-source software which I have released, see my [GitHub](http://github.com/markchil) page for more details and a few other projects.

## gptools: an obsessively complete implementation of Gaussian process regression
There are lots of tools to perform Gaussian process regression in Python. Very few of them can handle constraints on and predictions of the gradients of the fitted curve. Most of them are structured in a way which makes using a non-stationary covariance kernel difficult if not impossible. gptools is the only software I am aware of which can handle both non-stationary covariance kernels and gradient constraints/predictions.

* Project on GitHub: <http://github.com/markchil/gptools>
* Documentation on Read the Docs: <http://gptools.readthedocs.io>
* Releases on PyPI: <http://pypi.python.org/pypi/gptools/>

Here is a picture of the 2D squared exponential covariance kernel and a few of its derivatives, produced using gptools:

![2D SE]({{ site.github.url }}/images/SE2D.png)

This is the posterior distribution for the hyperparameters of a 1D non-stationary covariance kernel fit to density profile data produced by calling [emcee](http://dan.iel.fm/emcee/) from gptools:

![ne marginals]({{ site.github.url }}/images/neMarginalsNew.png)

And here are the associated data and fitted profiles (blue is marginalized with MCMC, red is MAP estimate -- the means are similar, but the uncertainty envelopes are not):

![fitted ne profile]({{ site.github.url }}/images/neFit.png)

## profiletools: making it a little less painful to get profile data out of MDSplus
profiletools is a Python package for grabbing plasma physics profile data from the MDSplus tree (a data storage system used throughout the plasma physics community), removing bad channels, getting it into a consistent data structure, and smoothing profiles with non-stationary Gaussian process regression.

* Project on GitHub: <http://github.com/markchil/profiletools>
* Documentation on Read the Docs: <http://profiletools.readthedocs.io>

Here is an example of fitting a temperature profile with a non-stationary Gaussian process using the gpfit GUI written using profiletools:

![gpfit]({{ site.github.url }}/images/gpfit.png)

## eqtools: everything you ever wanted to do with magnetic equilibrium reconstructions
eqtools is a piece of software I wrote with several of my colleagues to provide a much-needed Python interface to data from magnetic equilibrium reconstructions. It abstracts away the details of data storage so that the user does not have to worry about remembering obtuse MDSplus node names, and allows users to take their analysis codes to any machine -- even if the machines use completely different reconstruction codes and data systems.

* Project on GitHub: <http://github.com/PSFCPlasmaTools/eqtools>
* Documentation on Read the Docs: <http://eqtools.readthedocs.io>
* Releases on PyPI: <http://pypi.python.org/pypi/eqtools/>

Here is a plot of magnetic field lines traced using eqtools. The coloring is proportional to the field strength, which makes the 1/R dependence clear:

![magnetic field lines]({{ site.github.url }}/images/Blines.png)

And here are the flux surfaces and diagnostic locations, plotted using eqtools and profiletools:

![equilibrium reconstruction]({{ site.github.url }}/images/diags_1101014006.png)

## gEEProg: a user-friendly, cross-platform GUI for D'Asaro Designs EEPROM programmers
I wrote the GUI which drives the [EEPROM programmers](http://www.dasarodesigns.com/product-category/rom/) made by [D'Asaro Designs](http://www.dasarodesigns.com/). The software is designed to make it as simple as possible to use these programmers, and provides a built-in hex editor as well as file reading/writing and copy/paste capabilities.

* Stable releases and user manual, including standalone builds for PC and Mac: <http://github.com/markchil/gEEProg/releases>
* Stable source releases on PyPI: <http://pypi.python.org/pypi/gEEProg>
* Development on GitHub: <http://github.com/markchil/gEEProg>

Here is gEEProg being used with [2801Prog](http://www.dasarodesigns.com/product/2801prog-mcm2801-eeprom-programmer/) to program a Motorola MCM2801 EEPROM:

![program complete]({{ site.github.url }}/images/ProgramSuccess.png)
