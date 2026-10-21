## **1D and 2D Demo**

  ```python
 # [DEMO] Creating arrays from sequences
data1 = [6, 7.5, 8, 0, 1]  # a normal python list of numbers
arr1 = np.array(data1)  # np.array() converts a list into a numpy array

data2 = [[1, 2, 3, 4], [5, 6, 7, 8]]  # a list of lists = 2 rows, 4 columns
arr2 = np.array(data2)  # becomes a 2D array (a grid/table of numbers)

print(f"Array 2:\n{arr2}")
print(f"\nShape: {arr2.shape}, \nDtype: {arr2.dtype}, \nDimensions: {arr2.ndim}")
# shape = (rows, columns), dtype = data type stored, ndim = number of dimensions, these are all attributes of a numpy array object, accessed with dot notation
  ```
<br>

💡💡💡**Real Life Example**💡💡💡

<img width="579" height="281" alt="image" src="https://github.com/user-attachments/assets/5ac500e2-e19a-49b3-b9d2-a5c17fab0347" />


<img width="623" height="480" alt="image" src="https://github.com/user-attachments/assets/0b4c4d9b-8189-4308-9aca-87e90b68dd9a" />



<img width="763" height="709" alt="image" src="https://github.com/user-attachments/assets/afcae1c9-b812-4f4b-a1d3-639cc2588abd" />


## **Data Types and Casting**
  ```python
# [DEMO] Casting arrays
arr = np.array([3.7, -1.2, 0.5, 12.9])  # array of decimal (float) numbers

print("Original:", arr)

print("Casted to int32:", arr.astype(np.int32))  # astype() converts dtype; decimals get cut off (not rounded)
  ```

<img width="584" height="340" alt="image" src="https://github.com/user-attachments/assets/1751499b-154e-469f-927c-e8a1c5ed9380" />

<br>

💡💡💡**Real Life Example**💡💡💡

<img width="575" height="377" alt="image" src="https://github.com/user-attachments/assets/fde541d9-51c3-47ed-bfca-c0cc99f8f3f5" />  

<br>

### 👋 **Exercise 1: Creation & Casting**
 1. Create a 3x4 array of all ones using np.ones().
 2. Cast this array to float32.

<img width="615" height="391" alt="image" src="https://github.com/user-attachments/assets/5d87cd37-ca55-46e6-89b3-0ccf985a0d55" />

<img width="620" height="296" alt="image" src="https://github.com/user-attachments/assets/cf760dce-d152-4135-a043-aeeb0ed7a132" />

<img width="622" height="346" alt="image" src="https://github.com/user-attachments/assets/0fc5dcfb-5911-4085-84ca-63757cce9123" />


 3. Create an array of strings representing numbers: ['1.25', '-9.6', '42']. Cast it to float.

  ```python
adjustments = np.array(['1.25', '-9.6', '42'])

adjustments_float = adjustments.astype(float)
print(adjustments_float, adjustments_float.dtype)  -- [ 1.25 -9.6  42.  ] float64
  ```

## **Part 3: Arithmetic & Broadcasting**

  ```python
# [DEMO] Arithmetic & Broadcasting
arr = np.array([[1., 2., 3.], [4., 5., 6.]])  # 2D array, 2 rows x 3 columns

print("Original array:\n", arr)

print("\nElement-wise multiplication (arr * arr):\n", arr * arr)  # each number multiplied by itself, position by position

print("\nBroadcasting scalar (arr + 10):\n", arr + 10)  # 10 is "stretched" to match arr's shape, then added to every element

print("\nBroadcasting scalar (1 / arr):\n", 1 / arr)  # single number 1 applied to every element automatically
  ```
<img width="326" height="292" alt="image" src="https://github.com/user-attachments/assets/4bbf0500-2622-4bfd-ac2c-4fbd185b45c5" />


💡💡💡**Real Life Example: a café’s prices at two branches**💡💡💡

  ```python
import numpy as np

# rows = Branch A, Branch B; columns = coffee, sandwich, cake
prices = np.array([[2., 3., 5.],
                   [4., 5., 6.]])

quantities = np.array([[10., 4., 2.],
                       [5., 6., 1.]])

print("Revenue (prices * quantities):\n", prices * quantities)
print("\nWith $1 service charge (prices + 1):\n", prices + 1)
print("\nWith 10% tax (prices * 1.1):\n", prices * 1.1)
  ```

  ```python
Price
                  col 0 coffee   col 1 sandwich     col 2 cake  
row 0 Branch A  [    2                3                 5     ]
row 1 Branch B  [    4                5                 6     ]

Quantity
                  col 0 coffee   col 1 sandwich     col 2 cake  
row 0 Branch A  [    10               4                 2     ]
row 1 Branch B  [     5               6                 1     ]

Revenue (Price * Quantity)
                col 0 coffee   col 1 sandwich      col 2 cake
row 0 Branch A  [    20              12                10    ]
row 1 Branch B  [    20              30                 6    ]
  ```

<img width="326" height="221" alt="image" src="https://github.com/user-attachments/assets/c395a5a3-2820-41a6-acc5-c6df6acbcc02" />


## **Part 4: Indexing and Slicing**

  ```python
# [Demo] Slicing patterns
arr = np.arange(10)  # array: 0,1,2,...,9
print("arr:", arr)

print("\narr[2:5]   (index 2 up to 5):", arr[2:5])       # elements at index 2,3,4 - stop index NOT included
print("arr[:4]    (start to index 4):", arr[:4])         # elements at index 0,1,2,3
print("arr[6:]    (index 6 to end):  ", arr[6:])         # elements at index 6,7,8,9
print("arr[::2]   (every 2nd item):  ", arr[::2])        # step of 2 - skips every other element
print("arr[::-1]  (reversed):        ", arr[::-1])       # step of -1 - walks backwards through array
print("arr[-3:]   (last 3 items):    ", arr[-3:])        # negative index counts from the end

arr2d = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])  # 3x3 grid
print("\narr2d:\n", arr2d)
print("\narr2d[1]     (row 1 only):        ", arr2d[1])        # single row -> returned as 1D array
print("arr2d[:, 0]  (column 0 only):     ", arr2d[:, 0])       # single column -> returned as 1D array
print("arr2d[1, 2]  (row 1, col 2):      ", arr2d[1, 2])       # single element
print("arr2d[::-1]  (rows reversed):\n", arr2d[::-1])          # reverses row order, columns unchanged
  ```

  ```python
# [Output]
arr: [0 1 2 3 4 5 6 7 8 9]

arr[2:5]   (index 2 up to 5): [2 3 4]
arr[:4]    (start to index 4): [0 1 2 3]
arr[6:]    (index 6 to end):  [6 7 8 9]
arr[::2]   (every 2nd item):     [0 2 4 6 8]
arr[::-1]  (reversed):          [9 8 7 6 5 4 3 2 1 0]
arr[-3:]   (last 3 items):      [7 8 9]

arr2d:
 [[1 2 3]
 [4 5 6]
 [7 8 9]]

arr2d[1]     (row 1 only):          [4 5 6]
arr2d[:, 0]  (column 0 only):       [1 4 7]
arr2d[1, 2]  (row 1, col 2):        6
arr2d[::-1]  (rows reversed):
 [[7 8 9]
 [4 5 6]
 [1 2 3]]
  ```

💡💡💡**Real Life Example: a café sales**💡💡💡

Daily coffees sold over 10 days:

  ```python
import numpy as np

sales = np.array([12, 15, 11, 18, 20, 25, 30, 14, 16, 19])
#  day:            1   2   3   4   5   6   7   8   9  10
#  index:          0   1   2   3   4   5   6   7   8   9

print("Days 3 to 5:        ", sales[2:5])
print("First 4 days:       ", sales[:4])
print("Day 7 onwards:      ", sales[6:])
print("Every 2nd day:      ", sales[::2])
print("Newest to oldest:   ", sales[::-1])
print("Last 3 days:        ", sales[-3:])
```

Output
  ```python
Days 3 to 5:         [11 18 20]
First 4 days:        [12 15 11 18]
Day 7 onwards:       [30 14 16 19]
Every 2nd day:       [12 11 20 30 16]
Newest to oldest:    [19 16 14 30 25 20 18 11 15 12]
Last 3 days:         [14 16 19]
```

Revenue by branch (rows = Branch A, B, C; columns = coffee, sandwich, cake):
  ```python
#                                item 1      item 2      item 3
#                                coffee      sandwich    cake
#   column index:                  0           1           2
# branch 1 (Branch A) -> row 0    [20          12         10]
# branch 2 (Branch B) -> row 1    [20          30          6]
# branch 3 (Branch C) -> row 2    [15          18          9]

revenue = np.array([[20, 12, 10],
                    [20, 30,  6],
                    [15, 18,  9]])

print("Branch B only:      ", revenue[1])
print("Coffee, all branches:", revenue[:, 0])
print("Branch B cake:      ", revenue[1, 2])
print("Branches reversed:\n", revenue[::-1])
```

Output
  ```python
Branch B only:       [20 30  6]
Coffee, all branches: [20 20 15]
Branch B cake:       6
Branches reversed:
 [[15 18  9]
 [20 30  6]
 [20 12 10]]
```


## **Part 7: Linear Algebra**

<img width="1000" height="304" alt="image" src="https://github.com/user-attachments/assets/cae94e67-d8a1-4aea-9c43-18486146d644" />


💡💡💡**Real Life Example: ingredients needed at each café branch**💡💡💡

  ```python
import numpy as np

#                  coffee  sandwich  cake
orders = np.array([[10,      4,        2],     # Branch A (branch 1) -> row 0
                   [ 5,      6,        1]])    # Branch B (branch 2) -> row 1
# shape (2, 3): 2 branches x 3 items

#                  milk (ml)  flour (g)
recipe = np.array([[200,        0],    # coffee
                   [  0,      100],    # sandwich
                   [100,      250]])   # cake
# shape (3, 2): 3 items x 2 ingredients

needed = orders @ recipe
print(needed)
print(needed.shape)
```

  ```python
# Output
[[2200  900]
 [1100  850]]
(2, 2)
```

<img width="700" height="410" alt="image" src="https://github.com/user-attachments/assets/02c9a85b-2208-4ebb-a705-2497a98097b8" />

Reading the result:

 - needed[0, 0] is Branch A’s milk: 2200 ml

 - needed[1, 1] is Branch B’s flour: 850 g

 - needed[:, 0] is milk needed by all branches: [2200 1100]

🎯🎯🎯 **NOTES** 🎯🎯🎯

Answer will be wrong if the orders are not in the same sequence as the recipe. NumPy matches by position, not by name. It has no idea that column 1 means “sandwich”, so it just multiplies column 1 of orders with row 1 of recipe.

Good habit: keep the item order identical in both tables and write it in a comment above each one, as in your screenshot (coffee, sandwich, cake). If you want the names to be matched automatically, that’s what pandas is for, since it keeps row and column labels. Plain NumPy only stores the numbers.
