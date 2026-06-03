#  Mean and variance of a discrete  distribution


# Aim : 

To find mean and variance of arrival of objects from the feeder using probability distribution


# Software required :  

Python and Visual components tool

# Theory:

The expectation or the mean of a discrete random variable is a weighted average of all possible
values of the random variable. The weights are the probabilities associated with the corresponding values. 
It is calculated as,

![image](https://user-images.githubusercontent.com/103921593/192938463-e34177f4-f188-48a0-bda2-8f6d1d660ed2.png)

The variance of a random variable shows the variability or the scatterings of the random variables.
It shows the distance of a random variable from its mean. It is calcualted as

![image](https://user-images.githubusercontent.com/103921593/192938695-99fedc01-34d5-4d36-84df-5880e766ed0c.png)


# Procedure :

1. Construct frequency distribution for the data

2. Find the  probability distribution from frequency distribution.

3. Calculate mean using 
   
   ![image](https://user-images.githubusercontent.com/103921593/192940431-03b81777-c54d-4286-b4f4-82dfe7666b4c.png)

4. Find  
   
      ![image](https://user-images.githubusercontent.com/103921593/192940255-2d9dd746-6875-4a6d-877b-6da6cdb96ab1.png)

5.  Calculate variance using 
  
      ![image](https://user-images.githubusercontent.com/103921593/192942852-913550a9-fabe-4a55-b956-0487b18bbd97.png)



# Program :
```py
import numpy as np

# Input arrival data
L = [int(i) for i in input("Enter arrival data: ").split()]

# Total number of observations
N = len(L)

# Maximum arrival value
M = max(L)

# Lists for X and frequency
X = []
f = []

# Frequency distribution
for i in range(M + 1):
    count = 0
    for j in range(N):
        if L[j] == i:
            count += 1
    X.append(i)
    f.append(count)

# Probability distribution
p = np.array(f) / np.sum(f)

# Mean E(X)
mean = np.sum(np.array(X) * p)

# E(X^2)
EX2 = np.sum((np.array(X) ** 2) * p)

# Variance Var(X)
variance = EX2 - (mean ** 2)

# Standard Deviation
SD = np.sqrt(variance)

# Display probability distribution
print("\nX\tP(X)")
for i in range(M + 1):
    if f[i] > 0:
        print(f"{X[i]}\t{p[i]:.3f}")

# Final Results
print(f"\nMean = {mean:.3f}")
print(f"Variance = {variance:.3f}")
print(f"Standard Deviation = {SD:.3f}")
```


# Output : 

<img width="521" height="246" alt="image" src="https://github.com/user-attachments/assets/12c26bff-f010-43cb-9951-752139e209ad" />

## Developed by : Harish R
## Register No : 212224230085
# GitHub Link : 

https://github.com/Harish5127/Mean-and-Variance/tree/main

# Results :
The mean and variance of arrivals of objects from feeder using probability distribution are calculated.

