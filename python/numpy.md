## Array creation methods

### np.array - Create an array from list
Create an array with two rows and three columns.
```Python
a = np.array([[1, 2, 3],[1, 2, 3]])
```

### np.zeros - Create an array with zeros
Create an array containing any number of zeros:
```Python
a = np.zeros(5)
```
**Out**: `array([0., 0., 0., 0., 0.])`

Create a two dimension array with zeros:

```Python
a = np.zeros(2, 3)
```
**Out**: `array([[0., 0., 0.],
       [0., 0., 0.]])`

### np.ones - Create an array with ones
```Python
ones = np.ones((2,3))
```
**Out**: `array([[1., 1., 1.],
       [1., 1., 1.]])`

### np.arange - Create an array in a range
This method looks like python **range()**:
```Python
a = np.arange(10)
```
**Out**: `array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])`

Of course, we can indicate *start*, *end*, *step*:
```Python
a = np.arange(0, 10, 2)
```
**Out**: `array([0, 2, 4, 6, 8])`

### np.linspace - Create an array of spaced numbers
```Python
a = np.linspace(0, 1, 5)
```
**Out**: `array([0.  , 0.25, 0.5 , 0.75, 1.  ])`

### np.eye - Create an identity matrix
```Python
a = np.eye(4)
```
**Out**: `array([[1., 0., 0., 0.],
       [0., 1., 0., 0.],
       [0., 0., 1., 0.],
       [0., 0., 0., 1.]])`

Or like this:
```Python
a = np.zeros((3,4))
```
**Out**: `array([[0., 0., 0., 0.],
       [0., 0., 0., 0.],
       [0., 0., 0., 0.]])`

## Array metadata methods

For the following array:
**Out**: `array([[0., 0., 0., 0.],
       [0., 0., 0., 0.],
       [0., 0., 0., 0.]])`

### Dimension of the matrice - Shape:
```Python
a.shape
# Out: (3, 4)
```

### Number of dimensions:
```Python
a.ndim
# Out: 2
```

### Size of the matrice:
```Python
a.size
# Out: 12
```

## Arrays operations

### np.concatenate - Concatenate two arrays
Concatenate two arrays:

```Python
x = np.array([1, 2, 3])
y = np.array([3, 2, 1])
np.concatenate([x, y])
```
**Out**: `array([1, 2, 3, 3, 2, 1])`

### np.vstack & np.hstack - Stack vertically/horizontally
References: [numpy.vstack](https://numpy.org/doc/stable/reference/generated/numpy.vstack.html), [numpy.hstack](https://numpy.org/doc/stable/reference/generated/numpy.hstack.html).

**Vstack**:
```Python
x = np.array([1, 2, 3])
y = np.array([[9, 8, 7], [6, 5, 4]])
np.vstack([x, y])
```
**Out**: `array([[1, 2, 3],
       [9, 8, 7],
       [6, 5, 4]])`

**Hstack**:
```Python
x = np.array((1, 2, 3))
y = np.array((2, 3, 4))
np.hstack([x, y])
```
**Out**: `array([1, 2, 3, 2, 3, 4])`
