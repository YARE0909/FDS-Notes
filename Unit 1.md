# Reshaping Arrays

```python
arr.reshape();
```

```python
arr = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
arr.reshape(1, 9)
```

**Output:**
```bash
[1, 2, 3, 4, 5, 6, 7, 8, 9]
```

# List And Array

### List
- List can have elements of different data types
- Elements of a list are not stored contiguously in memory
- List do not support element wise operations like addition, multiplication etc
- Takes up more space in memory compared to arrays
- Part of core python library

### Array
- All elements are of the same data type
- Array elements are stored in contagious memory
- Arrays support element wise operations
- NumPy arrays takes up less space in memory as compared to lists
- Arrays are part of NumPy library

# Linear Algebra Module
Offers various methods to apply linear algebra on any NumPy array


```python
import numpy as np

A = np.array([[6, 1, 1], [4, -2, 5], [2, 8, 7]])

# Rank of matrix
print("Rank of A: ", np.linalg.martix_rank[A])

# Trace of matrix
print("\nTrace of A: ", np.trance[A])

# Determinant of matrix
print("\nDeterminant of A: ", np.linalg.det[A])

# Inverse of matrix
print("\nInverse of A: ", np.linalg.inv[A])

# Raise matrix to a power
print("\nMatrix A raised to power 3: ", np.linalg.matrix_power(A, 3))
```

# Eigen Values and Eigen Vectors
NumPy linear algebra package can find the eigen values and eigen vectors of a matrix

```python
import numpy as np
from numpy import linalg as LA

np.array([[1, 2, 3], [3, 2, 1], [1, 0, -1]])
w, v, = LA.eig(A) # Here w is eigen value, v is eigen vector
print(w)
```

# Generating Random Numbers using NumPy
Random numbers does not mean a different number every time. Random means something that cannot be predicted

### Generate Random Int

```python
from numpy import random

x = random.randint(100)

print(x)
```

**Output:**
```bash
69
```

### Generate Random Float

```python
from numpy import random

x = random.rand()

print(x)
```

**Output:**
```bash
0.20583403938393483
```

### Generate Random Array

In NumPy we work with arrays, and you can use the two methods above to make random arrays

```python
from numpy import random

x = random.randint(100, size[5])

print(x)
```

**Output:**
```bash
[61 66 32 13 16]
```

# Data Distribution

- List of all possible values
- Important when working with statistics and data science
- Random module offer methods that returns randomly generated data distributions

### Random Distribution 

- A random distribution is a set of random numbers that follow a certain **probability density function**
- Probability Density Function: A function that describes a continuous probability in an array
- The probability set is a number between 0 and 1

**Example:** 

Generate 1D array containing 100 values, where each value has to be 3, 5, 7 or 9
Probability for: 
- 3 is 0.1
- 5 is 0.3
- 7 is 0.6
- 9 is 0
The probabilities above can be defined as we wish

```python
from numpy import random

x = random.choice([3, 5, 7, 9], p = [0.1, 0.3, 0.6, 0.9, 0.0], size = (100))
print(x)
```

**Output:**
```bash
[3, 7, 7, 7, 5, 7, 5, 3, ...] # continues till 100 values are there in the array
```

```python
from numpy import random

x = random.choice([3, 5, 7, 9], p = [0.1, 0.3, 0.6, 0.9, 0.0], size = (3, 5))
```

**Output:**
```bash
[[7 7 7 7 7], [3 5 7 3 7], [7 5 5 7 7]]
```

### Normal Distribution

- Also called Gaussian Distribution
- Distribution can be described by the mean and standard deviation
- Mean(loc) is location parameter and standard deviation(scale) is scale parameter
- Use `random.normal()` method to get a **Normal Data Distribution**

```python
from numpy import random

x = random.normal(loc = 1, scale = 2, size = (2, 3))
```

**Output:**
```bash
[[-2.4545454 2.634343434 2.343423423], [1.02323232 2.12323722 2.23432432432]]
```

### Exponential Distribution

- Used for describing time till next event like failure/success etc.
- It is a graph of probability density function which shows the distribution of distance or time taken between two events
- The two terms used here are lambda (scale) and x(size)
- scale - inverse of rate ( see lam in Poisson distribution ) defaults to 1.0
- size - The shape of the returned array

```python
import numpy from random

x - random.exponential(scale = 2, size = (2, 3))

print(x)
```

**Output:**
```bash
[[0.123123212 5.223212312 1.2231232322] [2.422334334 5.342343433 1.243423423]]
```

### Binomial Distribution

- A binomial distribution can be thought of as simply the probability of a SUCCESS or FAILURE outcome in an experiment or survey that is repeated multiple times
- The binomial is a type of distribution that has two possible outcomes

```python
from numpy import random
import matplotlib.pyplot as plt
import seaborn as sns

sns.distplot(random.binomial(n=10, p=0.5, size=1000),
hist=True, kde=False)
plt.show()
```

**Output:**
An array that can be visualised as shown below
![[Pasted image 20230731102112.png]]

### Poisson Distribution

- Estimates how many times an event can happen in a specified time
- Example: If someone eats twice a day what is the probability he will eat thrice
- Poisson Distribution is a Discrete Distribution
- It has two parameters:
	- lam - rate or known number of occurrences
	- size - The shape of the returned array

```python
from numpy import random

x = random.poisson(lam=2, size=10)
print(x)
```

### Uniform Distribution

- Used to describe probability where every event has equal chances of occurring
- E.g. Generation of random numbers
- It has three parameters:
	- a - lower bound - default 0.0
	- b - upper bound - default 1.0
	- size - The shape of the returned array

```python
from numpy import random

x = random.uniform(size=(2, 3))
print(x)
```

**Output:**
```bash
[[0.21295952 0.57512648 0.39384297] [0.7543237 0.80233051 0.53264002]]
```

### Chi Square Distribution

- Chi Square distribution is used as a basis to verify the hypothesis
-  For categorial data
- It has two parameters:
	- df - (degree of freedom)
	- size - The shape of the returned array

```python
from numpy import random

x = random.chisquare(df=2, size=(2, 3))
print(x)
```

**Output:**
```bash
[[0.01738909 9.73650152 0.87953635] [0.14366152 0.98102103 2.72668685]]
```

# Join, split, search and sort

### Joining

![[Pasted image 20230803082921.png]]

Joining means putting contents of two or more arrays into one array. Functions offered by NumPy to join arrays:

**concatenate()**

```python
import numpy as np

arr1 = np.array([1, 2, 3])
arr2 = np.array([4, 5, 6])
arr = np.concatenate((arr1, arr2))

print(arr)
```

**Output:**
```bash
[1 2 3 4 5 6]
```
```python
import numpy as np

arr1 = np.array([[1, 2], [3, 4]])
arr2 = np.array([[5, 6], [7, 8]])
arr = np.concatenate((arr1, arr2), axis=1)

print(arr)
```

**Output:**
```bash
[[1 2 5 6] [3 4 7 8]]
```

**stack()**

Stacking is same as concatenation, the only difference is that stacking is done along a new axis. We can concatenate two 1-D arrays along the second axis which would result in putting them one over the other, i.e. stacking.

```python
import numpy as np

arr1 = np.array([1, 2, 3])
arr2 = np.array([4, 5, 6])
arr = np.stack((arr1, arr2), axis=1)

print(arr)
```

**Output:**
```bash
[[1 4] [2 5] [3 6]]
```

**hstack()**

![[Pasted image 20230803082633.png]]

```python
import numpy as np

arr1 = np.array([1, 2, 3])
arr2 = np.array([4, 5, 6])
arr = np.hstack((arr1, arr2))

print(arr)
```

**Output:**
```bash
[1 2 3 4 5 6]
```

**vstack()**

![[Pasted image 20230803082756.png]]

```python
import numpy as np

arr1 = np.array([1, 2, 3])
arr2 = np.array([4, 5, 6])
arr = np.vstack((arr1, arr2))

print(arr)
```

**Output:**
```bash
[[1 2 3] [4 5 6]]
```

### Split

Splitting is reverse operation of Joining.

**split():**

We also have the method split() available but it will not adjust the elements when elements are in
array for splitting like in example

```python
import numpy as np

arr = np.array([1, 2, 3, 4, 5, 6])
newarr = np.split(arr, 3)

print(newarr)
```

**Output:**
```bash
[array([1, 2]), array([3, 4]), array([5, 6])]
```

![[Pasted image 20230803083556.png]]

**array_split():**

```python
import numpy as np

arr = np.array([1, 2, 3, 4, 5, 6])
newarr = np.array_split(arr, 3)

print(newarr)
```

**Output:**
```bash
[array([1, 2]), array([3, 4]), array([5, 6])]
```

![[Pasted image 20230803083634.png]]

**hsplit()**

```python
import numpy as np

arr = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9], [10, 11, 12], [13, 14, 15], [16, 17, 18]])
newarr = np.hsplit(arr, 3)

print(newarr)
```

![[Pasted image 20230803083653.png]]

**vsplit():**
![[Pasted image 20230803083714.png]]

### Searching

You can search an array for a certain value, and return the indexes that get a match. To search an array, use the where() method.

```python
import numpy as np

arr = np.array([1, 2, 3, 4, 5, 4, 4])
x = np.where(arr == 4)

print(x)
```

**Output:**
```bash
(array([3, 5, 6]))
```

### Sorting

Sorting means putting elements in an ordered sequence. Ordered sequence is any sequence that an order corresponding to elements, like numeric or alphabetical, ascending or descending.
The NumPy ndarray object has a function called sort(), that will sort a specified array. 
Note: This method returns a copy of the array, leaving the original array unchanged.

```python
import numpy as np

arr = np.array([3, 2, 0, 1])

print(np.sort(arr))
```

**Output:**
```bash
[0 1 2 3]
```


