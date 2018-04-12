Validation of CEA network model
===============================

:Author: Lennart Rogenhofer
:Date: 11.04.2018

Multiprocessing is implemeted to speed up program run time.


Validation Method
=================

Compare the simulated results from CEA network model against the identical thermal network
model from the master branch and to the new program with multiproessing turned off. 


Comparison of Results from CEA and Simulink
===========================================


+-------------------------------------------+-------------------------------------------+------------+----------------+-----------------------+
| Branch				    | Parameter                                 | N5 DH      | N7 DC	      | Zug DH                |
+===========================================+===========================================+============+================+=======================+
| Master				    | Plant heat requirement			| 1671 MW    | -92 MW         | 8591 MW               |
|					    | Total pressure loss                       | 1009 MPa   | 78 MPa         | 573 MPa               |
+-------------------------------------------+-------------------------------------------+------------+----------------+-----------------------+
|Branch with MultiP			    | Plant heat requirement			| 1666 MW    | -92 MW         | 8688 MW               |
|                                           | Total pressure loss                       | 1010 MPa   | 78 MPa	      | 567 MPa		      |
+-------------------------------------------+-------------------------------------------+------------+----------------+-----------------------+
|Branch no MultiP			    | Plant heat requirement			| 1666 MW    | -92 MW         | 8688 MW		      |
|					    | Total pressure loss			| 1010 MPa   | 78 MPa	      | 567 MPa		      |
+-------------------------------------------+-------------------------------------------+------------+----------------+-----------------------+

Absolute Difference:
+-------------------------------------------+-------------------------------------------+------------+----------------+-----------------------+
| Branch with MultiP			    | Plant heat requirement			| 4 MW	     | 0 MW	      | -97 MW		      |
|					    | Total pressure loss			| -1 MPa     | 0 MPa	      | 6 MPa		      |
+-------------------------------------------+-------------------------------------------+------------+----------------+-----------------------+
| Branch no MultiP			    | Plant heat requirement			| 4 MW	     | 0 MW	      | -97 MW		      |
|					    | Total pressure loss			| -1 MPa     | 0 MPa	      | 6 MPa		      |
+-------------------------------------------+-------------------------------------------+------------+----------------+-----------------------+

Relative Difference:
+-------------------------------------------+-------------------------------------------+------------+----------------+-----------------------+
| Branch with MultiP			    | Plant heat requirement			| 0.26%      | -0.02%         | -1.13%		      |
|					    | Total pressure loss			| -0.10%     | 0.05%	      | 1.11 %		      |
+-------------------------------------------+-------------------------------------------+------------+----------------+-----------------------+
| Branch no MultiP			    | Plant heat requirement			| 0.26%      | 0.00%	      | -1.13%		      |
|					    | Total pressure loss			| -0.10%     | 0.04%	      | 1.11%		      |
+-------------------------------------------+-------------------------------------------+------------+----------------+-----------------------+

Conclusion
==========

Small deviations can be seen in the results. These are due to a change in the rounding of small mass flows between the branch and master. 
The deviations are most pronounced for the Zug case, since here more small mass flows appear, for which rounding makes a relatively larger difference.
