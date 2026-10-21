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

<img width="579" height="281" alt="image" src="https://github.com/user-attachments/assets/5ac500e2-e19a-49b3-b9d2-a5c17fab0347" />


<img width="623" height="480" alt="image" src="https://github.com/user-attachments/assets/0b4c4d9b-8189-4308-9aca-87e90b68dd9a" />



