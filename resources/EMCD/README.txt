
###################################################################
### EMCD code (DAMI 20217)
###
### DIMES, University of Calabria
### v. P. Bucci 44, 87036 Rende (CS), Italy
### 
### Copyright A. Tagarelli, 2017 
###
### TERMS OF USAGE:
### 1. The following paper is to be cited in any research product 
### whose findings are based on the data here distributed:
### 
### Andrea Tagarelli, Alessia Amelio, Francesco Gullo. 
### Ensemble-based Community Detection in Multilayer Networks. 
### Data Mining and Knowledge Discovery, Springer, 
### Vol. 31, Issue 5, pp. 1506–1543, 2017. 
### DOI: https://doi.org/10.1007/s10618-017-0528-8
###
### 2. The code cannot be redistributed.
###################################################################



QSG --- for detailed instructions refer to the manual "emcd_documentation.pdf"
==============================================================================

INPUT:

For a multilayer network <netw_name>, with 'l' layers, store the following files into a folder <netw_name>: 
* files adj0, ..., adj{l-1}, which correpond to the per-layer adjacency lists;
* files class0, ..., class{l-1}, which correspond to the layer-by-layer community structure (precomputed by a conventional community detection method for simple networks).

Command:   java -jar generateGreedy.jar #layers #nodes theta <input-path>/<netw_name>


OUTPUT (stored into a subfolder of <netw_name> named with the value of the theta parameter): 

* multilayer modularity of the community structure produced by M-EMCD;
* M-EMCD graph;
* consensus.txt, which stores for each node the membership community id (each row of the file corresponds to a node, and the value is the community id).


EXAMPLE USAGE (on AUCS network):

java -jar -Xmx16G generateGreedy.jar 5 61 0.4 "./aucs”.
