# BIOMD0000000006: BIOMD0000000006

## Installation

Download this repository, and install with distutils

`python setup.py install`

Or, install using pip

`pip install git+https://github.com/biomodels/BIOMD0000000006.git`

To install a specific version (in this example, from the 2014-09-16 BioModels release)

`pip install git+https://github.com/biomodels/BIOMD0000000006.git@20140916`


# Model Notes


Tyson1991 - Cell Cycle 2 var

Mathematical model of the interactions of cdc2 and cyclin.

Description taken from the original Cellerator version of the model ( [Tyson
(1991, 2 variables)](http://www.cellerator.org/notebooks/Tyson2.html) at
[http://www.cellerator.org](http://www.cellerator.org/) ).

This model is described in the article:

[Modeling the cell division cycle: cdc2 and cyclin
interactions.](http://identifiers.org/pubmed/1831270)

Tyson JJ.

Proc. Natl. Acad. Sci. U.S.A. 1991; 88(16); 7328-32

Abstract:

The proteins cdc2 and cyclin form a heterodimer (maturation promoting factor)
that controls the major events of the cell cycle. A mathematical model for the
interactions of cdc2 and cyclin is constructed. Simulation and analysis of the
model show that the control system can operate in three modes: as a steady
state with high maturation promoting factor activity, as a spontaneous
oscillator, or as an excitable switch. We associate the steady state with
metaphase arrest in unfertilized eggs, the spontaneous oscillations with rapid
division cycles in early embryos, and the excitable switch with growth-
controlled division cycles typical of nonembryonic cells.

This is a two variable reduction of the larger 6-variable model published in
the same paper. The equations are:

u'= k4(v-u)(alpha+u^2)-k6*u  
v'=kappa-k6*u  
z= v-u  
with kappa = k1[aa]/[CT]

In the present implementation, an additional variable z is introduced with z =
v-u is made, so that the different variables be interpreted as follows:

u=[activeMPF]/[CT]  
v=([cyclin]+[preMPF]+[activeMPF])/[CT]  
z=([ cyclin]+[preMPF])/[CT]  
with [CT]=[CDC2]+{CDC2P]+[preMPF]+[aMPF].

The reactions included are only to show the flows between z and u, and do not
influence the species, as they all are set to _boundaryCondition=True_ ,
meaning, that they are only determined by the rate rules (explicit
differential equations) and assignment rules.

If you set _boundaryCondition=False_ and remove the rate rules for v, u and
the the assignment rule for z, you get the more symmetrical, but equivalent,
version from the Cellerator repository:

u'= k4*z*(alpha+u^2)-k6*u  
z'=kappa-z*(alpha+u^2)

This model is hosted on [BioModels Database](http://www.ebi.ac.uk/biomodels/)
and identified by:
[BIOMD0000000006](http://identifiers.org/biomodels.db/BIOMD0000000006) .

To cite BioModels Database, please use: [BioModels Database: An enhanced,
curated and annotated resource for published quantitative kinetic
models](http://identifiers.org/pubmed/20587024) .

To the extent possible under law, all copyright and related or neighbouring
rights to this encoded model have been dedicated to the public domain
worldwide. Please refer to [CC0 Public Domain
Dedication](http://creativecommons.org/publicdomain/zero/1.0/) for more
information.


