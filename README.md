## 1. Introduction to NumPy

Full form: Numerical Python

Use: Efficient handling of arrays (lists of numbers in multiple dimensions).

Why NumPy?

Normal Python lists are slow.

NumPy arrays are much faster (written in C).

Provides built-in functions for mathematical, logical, and statistical operations.




---

## 2. NumPy Array (ndarray)

Core of NumPy = ndarray (N-dimensional array).

Think of it as a super-powered list with fixed size and type.

---

## 1. Installing & Importing NumPy
```bash
# Install (if not installed)
# pip install numpy

import numpy as np
```
## 2. Creating Arrays

NumPy arrays are faster and more efficient than Python lists.

```bash
# 1D array
arr1 = np.array([1, 2, 3, 4, 5])
print("1D Array:", arr1)

# 2D array (Matrix)
arr2 = np.array([[1, 2, 3], [4, 5, 6]])
print("\n2D Array:\n", arr2)

# 3D array
arr3 = np.array([[[1, 2], [3, 4]], [[5, 6], [7, 8]]])
print("\n3D Array:\n", arr3)
```

## Output:

```bash
1D Array: [1 2 3 4 5]

2D Array:
 [[1 2 3]
  [4 5 6]]

3D Array:
 [[[1 2]
   [3 4]]

  [[5 6]
   [7 8]]]
```
## 3. Array Attributes

```bash
print("Shape:", arr2.shape)   # (rows, columns)
print("Dimensions:", arr2.ndim)
print("Size:", arr2.size)     # total elements
print("Data Type:", arr2.dtype)
```

## Output:

```bash
Shape: (2, 3)
Dimensions: 2
Size: 6
Data Type: int64
```


---

## 4. Special Arrays

```bash
print("Zeros:\n", np.zeros((2, 3)))
print("\nOnes:\n", np.ones((3, 3)))
print("\nIdentity:\n", np.eye(3))
print("\nArange:", np.arange(0, 10, 2))   # like range()
print("\nLinspace:", np.linspace(0, 1, 5)) # evenly spaced numbers
```

## Output:

```bash
Zeros:
 [[0. 0. 0.]
  [0. 0. 0.]]

Ones:
 [[1. 1. 1.]
  [1. 1. 1.]
  [1. 1. 1.]]

Identity:
 [[1. 0. 0.]
  [0. 1. 0.]
  [0. 0. 1.]]

Arange: [0 2 4 6 8]
Linspace: [0.   0.25 0.5  0.75 1.  ]
```


---

## 5. Indexing & Slicing

```bash
arr = np.array([10, 20, 30, 40, 50])
print("Element at index 2:", arr[2])
print("Slice 1:4:", arr[1:4])

mat = np.array([[1,2,3],[4,5,6],[7,8,9]])
print("\nElement (2nd row, 3rd col):", mat[1, 2])
print("First row:", mat[0])
print("Last column:", mat[:, -1])
```

# Output:

```bash
Element at index 2: 30
Slice 1:4: [20 30 40]

Element (2nd row, 3rd col): 6
First row: [1 2 3]
Last column: [3 6 9]
```


---

# 6. Mathematical Operations

```bash
a = np.array([1, 2, 3, 4])
b = np.array([5, 6, 7, 8])

print("Addition:", a + b)
print("Subtraction:", a - b)
print("Multiplication:", a * b)
print("Division:", b / a)
print("Power:", a ** 2)
```

# Output:

```bash
Addition: [ 6  8 10 12]
Subtraction: [-4 -4 -4 -4]
Multiplication: [ 5 12 21 32]
Division: [5.   3.   2.33 2.  ]
Power: [ 1  4  9 16]
```


---

## 7. Aggregation Functions

```bash
mat = np.array([[1,2,3],[4,5,6],[7,8,9]])

print("Sum:", mat.sum())
print("Row-wise Sum:", mat.sum(axis=1))
print("Column-wise Sum:", mat.sum(axis=0))
print("Mean:", mat.mean())
print("Max:", mat.max())
print("Min:", mat.min())
print("Standard Deviation:", mat.std())
```

## Output:

```bash
Sum: 45
Row-wise Sum: [ 6 15 24]
Column-wise Sum: [12 15 18]
Mean: 5.0
Max: 9
Min: 1
Standard Deviation: 2.581988897
```


---

## 8. Reshaping & Flattening

``` bash
arr = np.arange(1, 13)
print("Original:", arr)

reshaped = arr.reshape(3, 4)
print("\nReshaped 3x4:\n", reshaped)

flattened = reshaped.flatten()
print("\nFlattened:", flattened)
```

## Output:

```bash
Original: [ 1  2  3  4  5  6  7  8  9 10 11 12]

Reshaped 3x4:
 [[ 1  2  3  4]
  [ 5  6  7  8]
  [ 9 10 11 12]]

Flattened: [ 1  2  3  4  5  6  7  8  9 10 11 12]
```


---

## 9. Stacking & Splitting

```bash
a = np.array([[1,2],[3,4]])
b = np.array([[5,6],[7,8]])

print("Vertical Stack:\n", np.vstack((a,b)))
print("\nHorizontal Stack:\n", np.hstack((a,b)))

arr = np.arange(1, 10)
print("\nSplit:", np.split(arr, 3))
```

## Output:

```bash
Vertical Stack:
 [[1 2]
  [3 4]
  [5 6]
  [7 8]]

Horizontal Stack:
 [[1 2 5 6]
  [3 4 7 8]]

Split: [array([1, 2, 3]), array([4, 5, 6]), array([7, 8, 9])]
```


---

## 10. Linear Algebra

```bash
import numpy as np

mat1 = np.array([[1,2],
                 [3,4]])

mat2 = np.array([[5,6],
                 [7,8]])

print("Matrix 1:\n", mat1)
print("Matrix 2:\n", mat2)

# Dot Product
print("\nDot Product:\n", np.dot(mat1, mat2))

# Transpose
print("\nTranspose of mat1:\n", mat1.T)

# Inverse of mat1
print("\nInverse of mat1:\n", np.linalg.inv(mat1))

# Determinant
print("\nDeterminant of mat1:", np.linalg.det(mat1))
```
## output

```bash
Matrix 1:
 [[1 2]
  [3 4]]

Matrix 2:
 [[5 6]
  [7 8]]

Dot Product:
 [[19 22]
  [43 50]]

Transpose of mat1:
 [[1 3]
  [2 4]]

Inverse of mat1:
 [[-2.   1. ]
  [ 1.5 -0.5]]

Determinant of mat1: -2.0000000000000004
```


