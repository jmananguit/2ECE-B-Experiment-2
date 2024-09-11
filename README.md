# 2ECE-B-Experiment-2
# NORMALIZATION PROBLEM
#### This code normalizes a random 5x5 array element-wise using the normalization formula Z=(X - mean)/(std) and saves the normalized array.
#### It also lets users decide the range from which the random numbers are taken from.
##### Example Input:
#####     Input Lower Range of Value: 1
#####     Input Higher Range of Value: 10
```
##Normalization Problem
#Import numpy library to be able to use arrays
import numpy as np
#informs user about the function of the code
print('This program lets the user input the range of integers that fills a 5x5 array randomly using the inputted range')
#create a function which lets the user input the range of numbers where random integers fills the array
def isint(val): 
    #create a loop that checks if user input is int
    while True: #checks if the value inputed is an integer
        try:  
            a = int(input(val))
            return a
        except: #prompts the user that the inputed value is not an integer
            print('Input Invalid Try Again!')
#assign the user inputs into a varible and call the function isint
i = isint('Input Lower Range of Value: ')
j = isint('Input Higher Range of Value: ')
#check if the lower range is less than higher range
while i >= j:
    print("The higher range must be greater than the lower range.")
    j = isint('Input Higher Range of Value: ')
#creates a random 5x5 array based from the inputted ranges
X = np.random.randint(i,j,(5,5))
print ('Random Array: ')
print (X)
#store the mean of array X to variable Y and print the array
Y = X.mean()
print ('Mean: ',Y)
#store the standard deviation of array X to variable W and print the value
W = X.std()
print ('Standard Deviation:', W)
#complete the normalization formula and print the array
Z = (X-Y)/W
print('Normalized Array:')
print(Z)
#save array Z using file name X_normalized'
np.save('X_normalized', Z)
```

# DIVISIBLE BY 3 PROBLEM
#### This code creates a 10x10 array ranging from the squares of 1 to 100 and finds every element divisible by 3 and stores the resulting array
##### Expected Output:
##### [  9   36   81  144  225 ... n]
```
##DIVISIBLE BY 3 PROBLEM
#Import numpy library to be able to use arrays
import numpy as np
#Inform the user about the purpose of the program
print('This program creates a 10x10 array ranging from the squares of 1 to 100 and finds every element divisible by 3')
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
print ('Original Array: ') 
print (b)
#find all elements that are divisible by 3
modulo = b%3==0
#slices the only elements that are found 'True' by the modulo
div_by_3 = b[modulo]
print ('Elements Divisible by 3:')
print(div_by_3)
#save array using file name 'div_by_3'
np.save('div_by_3', div_by_3)
```
