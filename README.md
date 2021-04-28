# Truel
"Truel" problem solver (math and simulation), with 2D visualization functions, using Python/numba, in Jupyter notebook.

Truel problem is an old problem/puzzle which can be summarized as :

**Several people are doing duel. Given their probabilities to hit, what are probability of each of them to win and who should they choose as optimal initial target ?**

Files in this project:
- **Truel.ipynb** : main Jupyter document, contains python code and analysis of Truel options 
- Truel.html : HTML representation of document. Not necessary - can be recreated from ipynb  [optional]

This document presents solutions and analysis of different scenarios for "classical truel" problem - one where players can have different probabilities to hit, shoot sequentially with infinite number of bullets, and where missing is allowed. 

It contains several notable elements:
* **solving for optimal targets**: solutions that not only find/show win probabilities for predefined targets, but are able to find optimal targets
* **interactive reusable solution**: interactive Python functions for fast solution and visualization, with flexible configurable parameters
* **random choice analysis**: demonstration that "random" target choice can be optimal for some players in certain scenarios
* **four players analysis**: analyze optimal targets in "four players" truel scenarios

Solution is fast enough to be interactive even for visualization ( where millions of individual pixels/solutions need to be calculated in short time to present AB graph with all possible hit probabilities for players A and B ). That speed was achieved by implementing default solution using mathematical calculations, while still providing option for conventional solution using simulation. Solutions support not only finding win probabilities for players with predefined initial targets, but also finding actual optimal targets. 

Mathematical solution is around 400 times faster than simulation when solving for predefined targets, and over 2000 times faster when finding optimal targets in truel scenarios. To improve speed, Numba accelerated Python functions are used, along with 'smart' optimizations for AB graph that use dynamic interpolation/calculation. 

To further improve speed and allow interactivity, 2D visualization functions can cache their results in truelCache.npz (using preCalc). Initial 'run all cells' in Jupyter notebook will need around 20 min to calculate entire document when cache does not exist. Future 'run all cells' would need just around minute, mostly for numba (re)compilation, since large data for 2D graphs will be used from cache.


Language used in JupyterLab document is Python ( **Python 3.8** ), and only used package that was sensitive to version is Numba ( updated for **numba 0.53.1** )

Code and resulting analyses from this document are free for use, as long as original source is mentioned.
