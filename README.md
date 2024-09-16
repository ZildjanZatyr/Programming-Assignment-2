# 📝 Programming Assignment 2: Numerical Python
> [!NOTE]
> #### *This repository contains two problems emphasizing different aspects of Python programming, including ndarrays, storing, and extracting files. Each problem presents unique challenges that enhance understanding of data structures and algorithmic thinking in Python.*

## 1. Normalization Problem
#### *This code create a random 5 x 5 ndarray and store it to variable X, namely "Normalize X", and saves it as an npy file.*
```Ruby
# Imports numpy library and assigns it np
import numpy as np

# Generates a random 5 x 5 matrix "X"
X = np.random.random((5, 5))

# Defines function and calculates the mean, normalized, and standard deviation
def normalization(X):
    normal = (X - np.mean(X))/np.std(X)
    return normal

# Saves the array into file "X_normalized.npy" and prints it
np.save('X_normalized.npy', normalization(X))
X
```
###### *-------------The 5 x 5 ndarray displaying a random array should look like: -------------* 
```Ruby
array([[0.90345154, 0.76418973, 0.64600677, 0.59218466, 0.59919997],
       [0.6427485 , 0.88148967, 0.83195243, 0.50288159, 0.35782585],
       [0.36796953, 0.24944635, 0.29363839, 0.05075701, 0.31048219],
       [0.98642486, 0.54361543, 0.56356058, 0.68117071, 0.83567095],
       [0.76682313, 0.16570682, 0.98443411, 0.45209394, 0.03226127]])
```
###### ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
#### *It then loads the file and normalizes the matrix, and prints the mean, standard deviation, and normalized matrix.*
```Ruby
# Loads the array and calculates the standard deviation of "X" and rounds it to 4 decimal places
X_normalized = np.load("X_normalized.npy")
rounded_std = round(np.std(X),4)

# Prints the mean, standard deviation, and normalized matrix
print("Mean:", X.mean())
print("\nStandard Deviation:", rounded_std)
print("\nNormalized Matrix:\n\n", X_normalized)
```
###### *-----The final output for this code displays the mean, standard deviation, and normalized matrix: -----*
```Ruby
Mean: 0.5602394389562219

Standard Deviation: 0.2731

Normalized Matrix:

 [[ 1.256552    0.74669323  0.31400733  0.11695635  0.14264047]
 [ 0.3020783   1.17614626  0.99478282 -0.20999586 -0.74106712]
 [-0.70392955 -1.13786105 -0.97606724 -1.86529312 -0.91439952]
 [ 1.56033003 -0.06086305  0.01215919  0.44274788  1.00839692]
 [ 0.75633449 -1.44444428  1.5530416  -0.39593721 -1.93300887]]
```
###### ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

## 2. Divisible by 3 Problem
#### *This code creates a 10 x 10 ndarray and stores it to a variable A, namely "A div3", and saves it as an npy file.*
```Ruby
# Imports numpy library and assigns it np
import numpy as np

# Creates array "A", generates function, and reshapes the array into a 10 x 10 matrix
A = np.arange(1, 101, 1)**2
A = A.reshape(10, 10) 

# Defines function "div3" and uses numpy's boolean indexing to select elements divisibly by 3
def div3(array):
    return array[array % 3 == 0]

# Flatten the array "A" and saves it to a file named "div_by_3.npy"
A_div3 = div3(A.flatten())
np.save("div_by_3.npy", A_div3)

# Prints the array "A" containing the squares of the first 100 positive 100 integeres
print("The Squares of the First 100 Positive Integers:\n\n", A)
```
###### *-----The 10 x 10 ndarray displaying the square of the first 100 positive integers should look like: -----*
```Ruby
The Squares of the First 100 Positive Integers:

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
```
###### ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
#### *It then loads the npy file and pulls numerical values divisibly by 3 from the 10 x 10 ndarray.*
```Ruby
# Load saved array "div_by_3.npy" into a new array 
div3_matrix = np.load("div_by_3.npy")

# Prints the elements divisibly by 3
print("The Elements that are divisible by 3:\n\n",div3_matrix)
```
###### *-----The final output for this code displaying integers divisible by 3 based from the square of the first 100 positive integers: -----*
```Ruby
The Elements that are divisible by 3:

 [   9   36   81  144  225  324  441  576  729  900 1089 1296 1521 1764
 2025 2304 2601 2916 3249 3600 3969 4356 4761 5184 5625 6084 6561 7056
 7569 8100 8649 9216 9801]
```
###### ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

## 👨‍💻 Author
#### *Zildjan Zatyr C. Ponce | 2ECE - A* 
#### *University of Santo Tomas*
#### *September 10, 2024*

## 🔑 Version History
- 1.01
  - REAADME file was completed
  - File containing the codes was added
  - About section was added
- 1.00
  - This repository was established
  - README.md was created
