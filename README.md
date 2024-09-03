# 2ECE-B-Experiment-2
# NORMALIZATION PROBLEM
```
#Import numpy library to be able to use arrays
import numpy as np
#Create a placeholder 5x5 array
X = np.random.random((5,5))
#store the mean of array X to variable Y
Y = X.mean()
#store the standard deviation of array X to variable W
W = X.std()
#complete the normalization formula 
Z = (X-Y)/W
print(Z)
#save array Z using file name X_normalized'
np.save('X_normalized', Z)
```

# DIVISIBLE BY 3 PROBLEM
```
#Import numpy library to be able to use arrays
import numpy as np
#Create a placeholder 5x5 array
a = np.zeros((10,10))
#create a for loop the creates a 10x10 array from 1 - 100
i = 1
for j in range(10):
    for k in range(10):
        a[j,k] = i
        i += 1
# squares the elements inside the array
a = a**2
# change the data type of the elements inside the array
b = a.astype(int)
#find all elements that are divisible by 3
modulo = b%3==0
#slices the only elements that are found 'True' by the modulo
div_by_3 = b[modulo]
print(div_by_3)
#save array using file name 'div_by_3'
np.save('div_by_3', div_by_3)
```
