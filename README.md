# Fitting Poisson  distribution

# date : 04/02/2026

# Aim : 

To fit poisson distribution for the arrival of objects per minute from the feeder

# Software required :  

Python and Visual component tool

# Theory:

The Poisson distribution is the discrete probability distribution of the number of events occurring in a given time period, given the average number of times the event occurs over that time period.

![image](https://user-images.githubusercontent.com/104613195/166248326-fd042076-8b0b-40c4-8b11-1d8e8fcb74db.png)

 Conditions for Poisson Distribution:

1. An event can occur any number of times during a time period.
2. Events occur independently. I
3. The rate of occurrence is constant.
4. The probability of an event occurring is proportional to the length of the time period. 
 
# Procedure :

![image](https://user-images.githubusercontent.com/104613195/166251988-d0c53205-6080-4f7b-ae4c-398178586637.png)

# Experiment :

![image](https://user-images.githubusercontent.com/103921593/230282876-f4a5afbf-cac1-4648-a1b0-c78840638a8e.png)

# Program :

```
# Developed by : Ryan David Prasad
# Register No : 212224040282

import numpy as np
import math

# Input arrival data
L = [int(i) for i in input("Enter arrivals per minute: ").split()]

N = len(L)
mean = np.mean(L)        # λ for Poisson distribution

M = max(L)
x = list(range(M+1))

# Observed frequency
f = [L.count(i) for i in x]

# Expected frequency using Poisson formula
E = []
for i in x:
    p = (math.exp(-mean) * mean**i) / math.factorial(i)
    E.append(N * p)

# Chi-square calculation
chi = sum((f[i] - E[i])**2 / E[i] for i in range(len(x)) if E[i] != 0)

print("Mean (λ) =", round(mean,3))
print("Observed frequencies =", f)
print("Expected frequencies =", [round(i,3) for i in E])
print("Chi-square value =", round(chi,3))
```

# Output : 

![Screenshots](ss_2.png)

# Results

The Poisson distribution is fitted for the objects arrived from feeder per minute and the data is tested using Chi-square test. 
 
