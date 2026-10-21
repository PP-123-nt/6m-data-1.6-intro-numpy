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
