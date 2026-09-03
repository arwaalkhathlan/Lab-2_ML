## Lab Tasks

### Group Members

| Names | ID |
| --- | --- |
| Arwa Alkhathlan | 2250030009 |
| Noor Albuainain | 2250030050 |
| Zainab Alharbi | 2250030246 |
| Joud Albeijan | 2250030261 |
| Sheehana Alghamdi | 2250030084 |
| Reem Alshehab | 2250030257 |

### 3.1 Create the Image Matrix
Generate a 6×6 NumPy array with values from 0 to 35.


```python
import numpy as np
img = np.arange(36).reshape(6, 6)
print("Original Image:\n", img)
```

    Original Image:
     [[ 0  1  2  3  4  5]
     [ 6  7  8  9 10 11]
     [12 13 14 15 16 17]
     [18 19 20 21 22 23]
     [24 25 26 27 28 29]
     [30 31 32 33 34 35]]
    

### 3.2 Extract the Center Region
Extract the central 4×4 region of the image.
    


```python
center = img[1:5, 1:5]
print("Center Region:\n", center)
```

    Center Region:
     [[ 7  8  9 10]
     [13 14 15 16]
     [19 20 21 22]
     [25 26 27 28]]
    

### 3.3 Apply Brightness Enhancement
Increase the brightness of the center region by 10 units.


```python
bright_center = center + 10
print("Brightened Center:\n", bright_center)
```

    Brightened Center:
     [[17 18 19 20]
     [23 24 25 26]
     [29 30 31 32]
     [35 36 37 38]]
    

### 3.4 Update the Original Image
Replace the original center region with the brightened version.
    


```python
img[1:5, 1:5] = bright_center
print("Updated Image:\n", img)
```

    Updated Image:
     [[ 0  1  2  3  4  5]
     [ 6 17 18 19 20 11]
     [12 23 24 25 26 17]
     [18 29 30 31 32 23]
     [24 35 36 37 38 29]
     [30 31 32 33 34 35]]
    

### 3.5 Compute Image Statistics
Calculate the following:

•	Mean pixel intensity


```python
print("Mean Intensity:", img.mean())
```

    Mean Intensity: 21.944444444444443
    

•	Maximum pixel intensity


```python
print("Max Intensity:", img.max())
```

    Max Intensity: 38
    

•	Minimum pixel intensity


```python
print("Min Intensity:", img.min())
```

    Min Intensity: 0
    

## 5.4 to 5.5

### 5.4 Modify the code to decrease brightness of border pixels by 5 units


```python
img[0, :] = img[0, :] - 5         # Top border
img[-1, :] = img[-1, :] - 5       # Bottom border
img[1:-1, 0] = img[1:-1, 0] - 5   # Left border
img[1:-1, -1] = img[1:-1, -1] - 5 # Right border

print("Image with Darkened Borders:\n", img)
```

    Image with Darkened Borders:
     [[-5 -4 -3 -2 -1  0]
     [ 1 17 18 19 20  6]
     [ 7 23 24 25 26 12]
     [13 29 30 31 32 18]
     [19 35 36 37 38 24]
     [25 26 27 28 29 30]]
    

### 5.5 Compute the standard deviation of the final image matrix


```python
print("Standard Deviation:", img.std())
```

    Standard Deviation: 12.785625609340444
    


