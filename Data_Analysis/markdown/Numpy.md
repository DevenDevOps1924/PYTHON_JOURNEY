# **Numpy**

Numpy is a python library used to working with multidimentional arrays.

Numpy is used to perfrom a lot of scientific and mathematical tasks.


```python
import numpy as np
```


```python
arr=np.array([1,2,3,4,5])
print(arr)
```

    [1 2 3 4 5]
    

# Why Numpy?

1) Numpy arrays are **faster** than python lists. Why?
  - Because numpy is written in C and not python. And C language is faster than python.

2) Numpy arrays can contain data of only one type ( they are **homogeneous**). But python lists can contain data of multiple type(**hetrogeneous**). Helps us perfrom maths and science operations, because data is of the same type and not mixed.

3) **Better memory allocation**-> Numpy arrays consume less memory than python lists, because numpy arrays the items are stored in a sequence( contiguous memory allocation- one after the other, elements are arranged in a line). But in python list all the elements are stored in different memoery locations, we just have the refrence or the address of the items. So lists are a little slower and consume more memory.


```python
l1=[1,2,3,"A",False]
l2=["Apple","Banana",4,5,6]

# We can't perfrom mathematical tasks like sum, add, mean, median, mode, max,etc
# If the data is of a mixed type
```

Creating numpy arrays


```python
a=np.array([1,2,3,4,5,6])
print(a)
print(type(a)) # ndarray-> n dimentional array
```

    [1 2 3 4 5 6]
    <class 'numpy.ndarray'>
    


```python
a=np.array([1, 2, 3.2, 4, 5.6, 6])
print(a)
```

    [1.  2.  3.2 4.  5.6 6. ]
    


```python
a=np.array([1, 2, 3.2, 4, 5.6, 6,"Apple"])
print(a)
```

    ['1' '2' '3.2' '4' '5.6' '6' 'Apple']
    

**How to check the type of elements in the array**

**arr.dtype**


```python
arr=np.array([1,2,3,4,5])
print(arr.dtype)
```

    int64
    


```python
arr=np.array([1.5,2.2,3.78,4.90,5.05])
print(arr.dtype)
```

    float64
    


```python
arr=np.array([True,False,True,False,True])
print(arr.dtype)
```

    bool
    


```python
arr=np.array(["Apple","Banana","Cherry","Mango"])
print(arr.dtype)  #U -> unicode ( String are represented as Unicode character in numpy)
```

    <U6
    

**How to convert the data type of the elements**

.astype()


```python
arr=np.array([1.5,2.2,3.78,4.90,5.05])
print(arr.dtype)
print(arr)
```

    float64
    [1.5  2.2  3.78 4.9  5.05]
    


```python
new_arr=arr.astype(int)
print(new_arr)
```

    [1 2 3 4 5]
    


```python
arr=np.array([1.5,2.2,0.0,4.90,0])
print(arr.dtype)
print(arr)
```

    float64
    [1.5 2.2 0.  4.9 0. ]
    


```python
new_arr=arr.astype(bool)
print(new_arr)
```

    [ True  True False  True False]
    

**Maths on arrays**



```python
a=np.array([1,2,3,4,5])
b=np.array([-1,-2,-3,-4,-5])

print(a+b)

print("Operation \"+\" :",a+b)
print("Operation \"-\" :",a-b)
print("Operation \"*\" :",a*b)
print("Operation \"%\" :",a%b)
print("Operation \"/\" :",a/b)
print("Operation \"//\" :",a//b)
 # -, *, %, / , //, ** Homeowork
```

    [0 0 0 0 0]
    Operation "+" : [0 0 0 0 0]
    Operation "-" : [ 2  4  6  8 10]
    Operation "*" : [ -1  -4  -9 -16 -25]
    Operation "%" : [0 0 0 0 0]
    Operation "/" : [-1. -1. -1. -1. -1.]
    Operation "//" : [-1 -1 -1 -1 -1]
    

Quiz Question-> https://drive.google.com/file/u/1/d/15nruC3_96mEJgk5olcMEnoZtRGz1aSnk/view

Answer documnet submit here-> https://docs.google.com/forms/d/e/1FAIpQLSfSbuEljWiOCUTAW6DlMHxohGhDQUn4k37RwAT88BQW6r8TdA/viewform


```python
# Create .doc or .pdf, and submit in the google form

# NO COLAB FILES ACCEPTED
```

# Dimensions

Dimensions are the depth of an array.

(Boxes inside boxes)


```python
arr=np.array([1,2,3,4,5]) # 1d
arr=np.array([ [1,2,3],[4,5,6],[7,8,9]])# 2d
arr=np.array([ [[1,2],[3,4]], [[5,6],[7,8]] ]) #3d

```

**arr.ndim**-> tells the number of dimention of an array




```python
# 0D-> a single element without aby box
arr=np.array(10)
print(arr)
print("No* of Dimensions: ",arr.ndim)
```

    10
    No* of Dimensions:  0
    


```python
#1D-> a single box without any boxes inside
arr=np.array([1,2,3,4,5,6,7,8])
print(arr)
print("No* of Dimensions: ",arr.ndim)
```

    [1 2 3 4 5 6 7 8]
    No* of Dimensions:  1
    


```python
# 2d-> boxes inside a box
arr=np.array([[1,2,3,4],[5,6,7,8],[9,10,11,12]])
print(arr)
print("No* of Dimensions: ",arr.ndim)
```

    [[ 1  2  3  4]
     [ 5  6  7  8]
     [ 9 10 11 12]]

    
    No* of Dimensions:  2
    


```python
# 3d
arr=np.array([ [ [1,2],[3,4] ],[ [5,6],[8,9] ],[ [10,11],[12,13] ] ])
print(arr)
print("No* of Dimensions: ",arr.ndim)
```

    [[[ 1  2]
      [ 3  4]]
    
     [[ 5  6]
      [ 8  9]]
    
     [[10 11]
      [12 13]]]
    

    No* of Dimensions:  3
    

**Shape->**

Tells the number of elements in each dimention.

Note: Tells us the number or rows and columns in 2d


```python
arr=np.array([1,2,3,4,5])
# 1d-> 5
print(arr.shape)
```

    (5,)
    


```python
arr=np.array([ [1,2,3,4],[5,6,7,8],[9,10,11,12] ])
# 1D-> 3
# 2D-> 4
# Shape-> (3,4)
print(arr)
print(arr.shape)
```

    [[ 1  2  3  4]
     [ 5  6  7  8]
     [ 9 10 11 12]]
    (3, 4)
    


```python
arr=np.array([ [[1],[2]] ,[[3],[4]] ,[[5],[6]] ,[[7],[8]] ])
# 1d-> 4
# 2d-> 2
# 3d-> 1
# shape=> (4,2,1)
print(arr.shape)
```

    (4, 2, 1)
    

**reshape**-> used to change the shape of an array.

Basically change the number of elements in dimentions, we can change the number of dimentions as well.


```python
arr=np.array([1,2,3,4,5,6,7,8,9,10,11,12])
print(arr.shape)
```

    (12,)
    


```python
new_arr=arr.reshape(4,3)
print(new_arr)
```

    [[ 1  2  3]
     [ 4  5  6]
     [ 7  8  9]
     [10 11 12]]
    


```python
# 12-> 4x3, 3x4, 6x2, 2x6, 4x3x1, 6x2x1...........

new_arr=arr.reshape(6,2)
print(new_arr)
```

    [[ 1  2]
     [ 3  4]
     [ 5  6]
     [ 7  8]
     [ 9 10]
     [11 12]]
    


```python
new_arr=arr.reshape(4,3,1)
print(new_arr)
```

    [[[ 1]
      [ 2]
      [ 3]]
    
     [[ 4]
      [ 5]
      [ 6]]
    
     [[ 7]
      [ 8]
      [ 9]]
    
     [[10]
      [11]
      [12]]]
    

**Rule of reshape**

Number of elements(the numbers 1,2,3,4,.......) should remain same before and after reshape


```python
arr=np.array([ [1,2,3,4,4],[5,6,7,7,7],[9,10,11,11,11] ])
print(arr)
```

    [[ 1  2  3  4  4]
     [ 5  6  7  7  7]
     [ 9 10 11 11 11]]
    


```python
# 15-> 3x5, 5x3, 5x3x1, 1x5x3.....1x1x1x5x3
```


```python
new_arr=arr.reshape(5,1,3)
print(new_arr)
```

    [[[ 1  2  3]]
    
     [[ 4  4  5]]
    
     [[ 6  7  7]]
    
     [[ 7  9 10]]
    
     [[11 11 11]]]
    

# Indexing and slicing


```python
arr=np.array([1,2,3,4,5])
#             0 1 2 3 4

# 4
print(arr[3])
# 3,4,5
print(arr[2:])
print(arr[2:5]) # access from 2 to 5-1-> 4
```

    4
    [3 4 5]
    [3 4 5]
    


```python
#               0     1     2
#              0 1   0 1   0 1
arr=np.array([[1,2],[3,4],[5,6]])
# 5
print(arr[2,0])
# 4
print(arr[1,1])
```

    5
    4
    


```python
#                    0             1               2
#                 0     1       0     1        0      1
#                0 1   0 1     0 1   0 1     0   1   0  1
arr=np.array([ [[1,2],[3,4]],[[5,6],[8,9]],[[10,11],[12,13]] ])

# 9
print(arr[1,1,1])
# 11
print(arr[2,0,1])
```

    9
    11
    

Slicing


```python
#              0 1 2   0 1 2   0 1 2
arr=np.array([[1,2,3],[4,5,6],[7,8,9]])
#                0       1       2
# [1,2,3],[4,5,6]
print(arr[0:2]) # 0 to 2-1 = 1, 0 to 1
print()
# [2, 5]
# 2 -> 0 , 1
# 5 -> 1,  1
print(arr[0:2,1])
```

    [[1 2 3]
     [4 5 6]]
    
    [2 5]
    


```python
#              0 1 2   0 1 2   0 1 2
arr=np.array([[1,2,3],[4,5,6],[7,8,9]])
#                0       1       2

#  [6, 9]
print(arr[1:,2])
# [2,8]
print(arr[0:3:2,1]) # go from start to end , step 2, access 1
print()

# [2,3], [5,6]
print(arr[0:2,1:])
```

    [6 9]
    [2 8]
    
    [[2 3]
     [5 6]]
    


```python
#              0 1 2   0 1 2   0 1 2
arr=np.array([[1,2,3],[4,5,6],[7,8,9]])
#                0       1       2
# 3,6,9
print(arr[:,2])
# [8,9]
print(arr[2,1:])

# [1,2],[4,5],[7,8]
# [1,3],[4,6],[7,9] # use step or jump
# [1,3],[7,9]  # use step or jump
```

    [3 6 9]
    [8 9]
    


```python
import numpy as np
```

**arange()**

Used to create an array which contains numbers from a range(start to end-1).


arange(start,end)-> start to end-1





```python
arr=np.array([1,2,3,4,5,6,7,8,9,10])
```


```python
# 1-> 10

arr=np.arange(1,11) # 1 to 10
print(arr)
```

    [ 1  2  3  4  5  6  7  8  9 10]
    


```python
# 5->15

arr=np.arange(5,16)
arr
```




    array([ 5,  6,  7,  8,  9, 10, 11, 12, 13, 14, 15])




```python
# 2,4,6,8,.....20

arr=np.arange(2,21,2) # start 2, end=20, jump=2
print(arr)
```

    [ 2  4  6  8 10 12 14 16 18 20]
    


```python
# 5,10,15....100

arr=np.arange(5,101,5)
print(arr)
```

    [  5  10  15  20  25  30  35  40  45  50  55  60  65  70  75  80  85  90
      95 100]
    

**linspace()**

Creates an array , with n equally spaced number between a start point and a end point.


```python
'''0 1 2 3 4 5 6 7 8 9 10
S   -   -   -   -   E
frist               last

# I need 6 numbers bw 0 to 10 ( equally distance)
0  2   4  6  8  10
'''

```




    '0 1 2 3 4 5 6 7 8 9 10\nS   -   -   -   -   E\nfrist               last\n\n# I need 6 numbers bw 0 to 10 ( equally distance)\n0  2   4  6  8  10\n'




```python
arr=np.linspace(0,10,6)
# 0 start 10 end , need 6 numbers between 0 to 10(0 and 10 included) such that the difference is same
print(arr)
```

    [ 0.  2.  4.  6.  8. 10.]
    


```python
arr=np.linspace(0,10,5)
print(arr)
```

    [ 0.   2.5  5.   7.5 10. ]
    


```python
arr=np.linspace(0,10)
print(arr)
print(len(arr))
```

    [ 0.          0.20408163  0.40816327  0.6122449   0.81632653  1.02040816
      1.2244898   1.42857143  1.63265306  1.83673469  2.04081633  2.24489796
      2.44897959  2.65306122  2.85714286  3.06122449  3.26530612  3.46938776
      3.67346939  3.87755102  4.08163265  4.28571429  4.48979592  4.69387755
      4.89795918  5.10204082  5.30612245  5.51020408  5.71428571  5.91836735
      6.12244898  6.32653061  6.53061224  6.73469388  6.93877551  7.14285714
      7.34693878  7.55102041  7.75510204  7.95918367  8.16326531  8.36734694
      8.57142857  8.7755102   8.97959184  9.18367347  9.3877551   9.59183673
      9.79591837 10.        ]
    50
    


```python
arr=np.linspace(0,20)
print(arr)
print(len(arr))
```

    [ 0.          0.40816327  0.81632653  1.2244898   1.63265306  2.04081633
      2.44897959  2.85714286  3.26530612  3.67346939  4.08163265  4.48979592
      4.89795918  5.30612245  5.71428571  6.12244898  6.53061224  6.93877551
      7.34693878  7.75510204  8.16326531  8.57142857  8.97959184  9.3877551
      9.79591837 10.20408163 10.6122449  11.02040816 11.42857143 11.83673469
     12.24489796 12.65306122 13.06122449 13.46938776 13.87755102 14.28571429
     14.69387755 15.10204082 15.51020408 15.91836735 16.32653061 16.73469388
     17.14285714 17.55102041 17.95918367 18.36734694 18.7755102  19.18367347
     19.59183673 20.        ]
    50
    

# Creating arrays with specific numbers

**zeros**

Creates array filled with 0.


```python
z=np.zeros(5)
print(z)
```

    [0. 0. 0. 0. 0.]
    


```python
z=np.zeros((4,5))
print(z)
```

    [[0. 0. 0. 0. 0.]
     [0. 0. 0. 0. 0.]
     [0. 0. 0. 0. 0.]
     [0. 0. 0. 0. 0.]]
    

**Ones**


```python
o=np.ones(10)
print(o)
```

    [1. 1. 1. 1. 1. 1. 1. 1. 1. 1.]
    


```python
o=np.ones((2,3))
print(o)
```

    [[1. 1. 1.]
     [1. 1. 1.]]
    

**full** -> creates an array filled with the element that we tell


```python
f=np.full(10,7)
f
```




    array([7, 7, 7, 7, 7, 7, 7, 7, 7, 7])




```python
f=np.full((5,5),"Apple")
print(f)
```

    [['Apple' 'Apple' 'Apple' 'Apple' 'Apple']
     ['Apple' 'Apple' 'Apple' 'Apple' 'Apple']
     ['Apple' 'Apple' 'Apple' 'Apple' 'Apple']
     ['Apple' 'Apple' 'Apple' 'Apple' 'Apple']
     ['Apple' 'Apple' 'Apple' 'Apple' 'Apple']]
    

**identity**

Its a square matix with all the diagonal elements as 1


```python
i=np.identity(5)
print(i)
```

    [[1. 0. 0. 0. 0.]
     [0. 1. 0. 0. 0.]
     [0. 0. 1. 0. 0.]
     [0. 0. 0. 1. 0.]
     [0. 0. 0. 0. 1.]]
    


```python
i=np.identity(3)
print(i)
```

    [[1. 0. 0.]
     [0. 1. 0.]
     [0. 0. 1.]]
    

**eye**

creates **n x m** matix with diagonal elements as 1.

Can create a **rectangular matirx**, identity(n) only creates a square matrix **n x n** but eye can create **n x m**


```python
e=np.eye(4,5)
print(e)
```

    [[1. 0. 0. 0. 0.]
     [0. 1. 0. 0. 0.]
     [0. 0. 1. 0. 0.]
     [0. 0. 0. 1. 0.]]
    


```python
e=np.eye(5)
print(e)
```

    [[1. 0. 0. 0. 0.]
     [0. 1. 0. 0. 0.]
     [0. 0. 1. 0. 0.]
     [0. 0. 0. 1. 0.]
     [0. 0. 0. 0. 1.]]

    
    

# Random

Helps you generate random numbers

**1) np.random.rand()**

Generate a random number between 0 to 1 range.


```python
# SIngle Random number( bw 0 to 1)
n=np.random.rand()
print(n)
```

    0.8403274029406291
    


```python
# Array of random numbers between 0 to 1
arr=np.random.rand(5)
print(arr)
```

    [0.98003365 0.81689751 0.49866525 0.17109644 0.79206654]
    


```python
arr=np.random.rand(2,3)
print(arr)
```

    [[0.63856942 0.95622437 0.00520452]
     [0.42171368 0.88472914 0.40587946]]
    

**2) np.random.randint()**

Generates random integers between a starting point to ending point. ( range)


```python
# Single number between 1 to 100

n=np.random.randint(1,100)
print(n)
```

    13
    


```python
arr=np.random.randint(1,100,size=10)
print(arr)
```

    [91 75 19 97 14 80 20 92  1 11]
    


```python
arr=np.random.randint(50,80,size=(4,5))
print(arr)
```

    [[70 70 71 61 57]
     [69 52 73 75 67]
     [62 72 58 75 62]
     [51 76 57 70 65]]
    

**3) np.random.choice()**

Randomly selects some elements from an array


```python
data=np.array([1,2,3,4,5,6,7,8,9,10])

# Single choice from arr
n=np.random.choice(data)
print(n)
```

    10
    


```python
n=np.random.choice(data,size=5)
print(n)

# replace=True, by default-> so numbers can repeat
```

    [10  5  2  2  6]
    


```python
# Dont choose the same things again.
# Unique choice
n=np.random.choice(data,size=5,replace=False)
print(n)
```

    [10  2  7  8  3]
    


```python
n=np.random.choice(range(1,100),size=10)
print(n)
```

    [86 16 63 26 54 58 96 74 54 10]
    


```python

```

**np.random.seed()**

Used to fix the randomness


```python
np.random.seed(42)
n=np.random.randint(1,100)
print(n)
```

    52
    


```python
np.random.seed(42)
otp=np.random.randint(1000,9999)
print(otp)
```

    8270
    


```python
np.random.seed(40)
n=np.random.choice(range(1,100),size=10)
print(n)
```

    [71 92  8 38 57 51 66 13 72 20]
    

**np.random.shuffle()**

Used to shuffle the array- change the order or arrangement randomly.


```python
arr=np.array([1,2,3,4,5,6,7,8,9,10])
print(arr)
print()
np.random.shuffle(arr)
print(arr)
```

    [ 1  2  3  4  5  6  7  8  9 10]
    
    [ 5  3  7  6  1  2 10  9  4  8]
    

**Filtering**


```python
marks=np.random.randint(20,100,size=40)
print(marks)
```

    [28 72 50 99 34 78 94 42 23 91 75 48 33 57 70 99 87 50 80 64 66 63 55 51
     25 85 27 61 45 78 90 77 77 56 83 94 20 21 53 72]
    


```python
# Filter marks<33,

# Filter out numbers less than 33

print(marks[ marks<33 ])
```

    [28 23 25 27 20 21]
    


```python
# Even numbers

# Filter even elements
print(marks[ marks%2==0 ])
```

    [28 72 50 34 78 94 42 48 70 50 80 64 66 78 90 56 94 20 72]
    


```python
# Filter even and greater than than 50

print(marks[(marks%2==0) & (marks>50)])

# & -> and
# | -> or
```

    [72 78 94 70 80 64 66 78 90 56 94 72]

    
    

**Questions- Practice**

**Q1) Index and slice**


```python
import numpy as np

#                0       1       2         3
arr=np.array([[1,2,3],[4,5,6],[7,8,9],[10,11,12]])
#              0 1 2   0 1 2   0 1 2   0   1 2

# Write the code to access these elements
# 1) 9
# 2) 11
# 3) [7,8,9],[10,11,12]
# 4) [4,5,6],[10,11,12]

# Slicing
# 5) 2, 5, 8, 11    -> arr[:,1]
# 6) 3, 9           -> arr[0:3:2,2]
# 7) [8,9], [11,12] -> arr[2:,1:]
# 8) [4,6],[10,12]  -> arr[1::2,0::2]
```


```python
print(arr[2,2])
print(arr[3,1])
print(arr[2:])
print(arr[1::2]) # start:end:step
```

    9
    11
    [[ 7  8  9]
     [10 11 12]]
    [[ 4  5  6]
     [10 11 12]]
    


```python
#                0       1       2         3
arr=np.array([[1,2,3],[4,5,6],[7,8,9],[10,11,12]])
#              0 1 2   0 1 2   0 1 2   0   1 2
```


```python
# 5) 2, 5, 8, 11    -> arr[:,1]
# 6) 3, 9           -> arr[0:3:2,2]
# 7) [8,9], [11,12] -> arr[2:,1:]
# 8) [4,6],[10,12]  -> arr[1::2,0::2]
```


```python
print(arr[1::2,::2])
```

    [[ 4  6]
     [10 12]]
    


```python
print(arr[2:,1:])
```

    [[ 8  9]
     [11 12]]
    


```python
print(arr[0:3:2,2])
```

    [3 9]
    


```python
print(arr[:,1])
```

    [ 2  5  8 11]
    

**Q2) Create an array with random integers between 1000,2000, size=50**

- **Filter out the even numbers from that array**

- **Filter out the numbers > 1500**

- **Numbers divisible by 5 and less than 1200**


```python
arr=np.random.randint(1000,2000,50)
print(arr)
```

    [1072 1057 1546 1270 1245 1718 1839 1184 1717 1214 1596 1338 1603 1268
     1730 1510 1201 1250 1119 1115 1795 1761 1384 1789 1094 1629 1869 1544
     1819 1306 1506 1276 1297 1362 1742 1590 1311 1815 1171 1636 1347 1076
     1511 1925 1557 1007 1906 1573 1915 1708]
    


```python
print(arr[(arr%5==0) & (arr<1200)])
```

    [1115]
    


```python
print(arr[arr>1500])
```

    [1546 1718 1839 1717 1596 1603 1730 1510 1795 1761 1789 1629 1869 1544
     1819 1506 1742 1590 1815 1636 1511 1925 1557 1906 1573 1915 1708]
    


```python
print(arr[arr%2==0])

```

    [1072 1546 1270 1718 1184 1214 1596 1338 1268 1730 1510 1250 1384 1094
     1544 1306 1506 1276 1362 1742 1590 1636 1076 1906 1708]
    

**Q) Create a array of shape 7,10 with all the diagonal elements as 1.**

**Create ana array of shape 2,3,4 with all the elements as 10**

**Create an array filled with 1 , 5 x 5**


```python
print(np.eye(7,10))
```

    [[1. 0. 0. 0. 0. 0. 0. 0. 0. 0.]
     [0. 1. 0. 0. 0. 0. 0. 0. 0. 0.]
     [0. 0. 1. 0. 0. 0. 0. 0. 0. 0.]
     [0. 0. 0. 1. 0. 0. 0. 0. 0. 0.]
     [0. 0. 0. 0. 1. 0. 0. 0. 0. 0.]
     [0. 0. 0. 0. 0. 1. 0. 0. 0. 0.]
     [0. 0. 0. 0. 0. 0. 1. 0. 0. 0.]]
    


```python
print(np.full((2,3,4),10))
```

    [[[10 10 10 10]
      [10 10 10 10]
      [10 10 10 10]]
    
     [[10 10 10 10]
      [10 10 10 10]
      [10 10 10 10]]]
    


```python
print(np.ones((5,5)))
```

    [[1. 1. 1. 1. 1.]
     [1. 1. 1. 1. 1.]
     [1. 1. 1. 1. 1.]
     [1. 1. 1. 1. 1.]
     [1. 1. 1. 1. 1.]]
    

**Q) Casino Game**

**Player starts with 100 rupees, and rolls a dice**

**If 6 comes -> win 20 rupees**

**Else -> Lose 10 rupees**

**Play 30 rounds**

**Find the final balance-> tell the profit or loss amount**



```python
bank=100
money=100
for i in range(30):
  n=np.random.randint(1,7)
  print("Dice=",n)
  if n==6:
    money+=20
    print("Won 20")
  else:
    money-=10
    print("Loss 10")


if money<bank:
  print("Loss=",money-bank)
else:
  print("Profit=",money-bank)
```

    Dice= 2
    Loss 10
    Dice= 5
    Loss 10
    Dice= 6
    Won 20
    Dice= 3
    Loss 10
    Dice= 1
    Loss 10
    Dice= 1
    Loss 10
    Dice= 6
    Won 20
    Dice= 4
    Loss 10
    Dice= 4
    Loss 10
    Dice= 1
    Loss 10
    Dice= 3
    Loss 10
    Dice= 2
    Loss 10
    Dice= 6
    Won 20
    Dice= 3
    Loss 10
    Dice= 6
    Won 20
    Dice= 6
    Won 20
    Dice= 6
    Won 20
    Dice= 4
    Loss 10
    Dice= 5
    Loss 10
    Dice= 1
    Loss 10
    Dice= 4
    Loss 10
    Dice= 4
    Loss 10
    Dice= 5
    Loss 10
    Dice= 2
    Loss 10
    Dice= 3
    Loss 10
    Dice= 6
    Won 20
    Dice= 4
    Loss 10
    Dice= 3
    Loss 10
    Dice= 4
    Loss 10
    Dice= 3
    Loss 10
    Loss= -90
    

**Q) Roll a dice 100 times, and find the probability of each outcome, based on the 100 tries.**


Eg-> if the count or frequency of 1 was 20, so probability=> 20/100

If count of 6 is 10, so probability of 6=> 10/100


Hint-> find the count of each element that comes when dice rolled 100 times.


```python

```
