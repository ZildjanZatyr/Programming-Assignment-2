# Programming Assignment 2: Numerical Python
##### This repository contains three problems emphasizing different aspects of Python programming, including ndarrays, storing, and extracting files. Each problem presents unique challenges that enhance understanding of data structures and algorithmic thinking in Python.

## 1. Normalization Problem
###### This code create a random 5 x 5 ndarray and store it to variable X, namely "Normalize X", and saves it as an npy file.
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
```Ruby
# Loads the array and calculates the standard deviation of "X" and rounds it to 4 decimal places
X_normalized = np.load("X_normalized.npy")
rounded_std = round(np.std(X),4)

# Prints the mean, standard deviation, and normalized matrix
print("Mean:", X.mean())
print("\nStandard Deviation:", rounded_std)
print("\nNormalized Matrix:\n\n", X_normalized)
```

## 2. Divisible by 3 Problem
###### This code creates a 10 x 10 ndarray and stores it to a variable A, namely "A div3", and saves it as an npy file. It then loads the npy file and pulls numerical values divisibly by 3 from the 10 x 10 ndarray.
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
```Ruby
# Load saved array "div_by_3.npy" into a new array 
div3_matrix = np.load("div_by_3.npy")

# Prints the elements divisibly by 3
print("The Elements that are divisible by 3:\n\n",div3_matrix)
```
