# EXPERIMENT-2---NUMERICAL-PYTHON

## Objective:

> To learn the use of NumPy functions for creating, reshaping, normalizing, and filtering arrays.

> To be able to apply centering, scaling, and masking techniques in Python.

## Problem 1: Normalization Problem

### Expected Behavior:

> Create a random 5×5 ndarray X.

> Save the normalized ndarray as X_normalized.npy.

### Approach:

> Use np.random.rand(5,5) to generate a random matrix.

> Compute the mean with .mean() and standard deviation with .std().

> Apply the normalization formula element-wise.

> Save the result using np.save().

#### Start of Code:

```
import numpy as np

#function to create a random 5x5 ndarray
X = np.random.rand(5,5)

#original array
print ("Original Array (X):\n", X)

#.mean and .std calls
mean_X = X.mean()
std_X = X.std()

#normalization expression
X_normalized = (X- mean_X) / std_X

#normalize the array
print("\nNormalized Array (X_normalized):\n", X_normalized)

#save noramlized ndarray as npy
np.save('X_normalized.npy', X_normalized)


### Generated Output:

Original Array (X):
 [[0.28686405 0.13500523 0.91804272 0.0320217  0.02183962]
 [0.09936953 0.37149395 0.57507955 0.67440282 0.5587366 ]
 [0.32365083 0.87676855 0.26681513 0.2005527  0.77234392]
 [0.19587087 0.4453143  0.61145343 0.95621327 0.08963091]
 [0.77445151 0.23085862 0.29064879 0.69059698 0.8940495 ]]

Normalized Array (X_normalized):
 [[-0.55333211 -1.06315436  1.56566833 -1.40889189 -1.44307528]
 [-1.18279094 -0.26921164  0.41426835  0.74771761  0.3594016 ]
 [-0.42983112  1.4271022  -0.6206406  -0.84309761  1.07652661]
 [-0.85881552 -0.02138109  0.53638316  1.69381495 -1.21548556]
 [ 1.08360225 -0.74135423 -0.54062596  0.80208484  1.48511803]]

```

## Problem 2: Divisible by 3 Problem

### Expected Behavior:

> Create a 10×10 ndarray of the squares of the first 100 positive integers.

> Find all elements divisible by 3.

> Save the result as div_by_3.npy.

### Approach:

> Use np.arange(1,101) to generate numbers 1–100.

> Square them using **2.

> Reshape into a 10×10 array with .reshape(10,10).

> Use boolean indexing A % 3 == 0 to extract divisible elements.

> Save with np.save().

### Start of Code

```
import numpy as np

#creating a 10x10 ndarray with squares of first 100 positive integers
A = np.arange (1, 101)**2

#reshaping array into 10x10
A = A.reshape ((10,10))

#original 10x10 array
print ("10 x 10 Array (A):\n", A)

#finding elements divisible by 3
div_by_3 = A[A % 3 == 0]

#elements divisible by 3
print ("\nElements divisible by 3 (div_by_3):\n", div_by_3)

#saving elements into npy file
np.save('div_by_3.npy', div_by_3)

```

### Generated Output: 

10 x 10 Array (A):
 [[    1     4     9    16    25    36    49    64    81   100]
 [  121   144   169   196   225   256   289   324   361   400]
 [  441   484   529   576   625   676   729   784   841   900]
 [  961  1024  1089  1156  1225  1296  1369  1444  1521  1600]
 [ 1681  1764  1849  1936  2025  2116  2209  2304  2401  2500]
 [ 2601  2704  2809  2916  3025  3136  3249  3364  3481  3600]
 [ 3721  3844  3969  4096  4225  4356  4489  4624  4761  4900]
 [ 5041  5184  5329  5476  5625  5776  5929  6084  6241  6400]
 [ 6561  6724  6889  7056  7225  7396  7569  7744  7921  8100]
 [ 8281  8464  8649  8836  9025  9216  9409  9604  9801 10000]]

Elements divisible by 3 (div_by_3):
 [   9   36   81  144  225  324  441  576  729  900 1089 1296 1521 1764
 2025 2304 2601 2916 3249 3600 3969 4356 4761 5184 5625 6084 6561 7056
 7569 8100 8649 9216 9801]

