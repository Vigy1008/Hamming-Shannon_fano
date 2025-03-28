# Huffman-Shannon_fano
Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. 
Apply the Huffman and Shannon-Fano to this source. 
Show that draw the tree diagram, the average code word length, Entropy, Variance, Redundancy, Efficiency.

## Aim
To compute the Average Codeword Length, Entropy, Efficiency, Redundancy, and Variance for a discrete memoryless source using Huffman
and Shannon-Fano coding based on the given probabilities and codeword lengths.
## Tools Required
python IDE with Numpy and Scipy.
## Program
```
import numpy as np
import math 
L  = 0
hs = 0
p = []
lk = []
n = int(input("Enter the number of Samples : "))
for i in range (n): 
    pr = float(input(f"Enter the probability of sample values {i + 1}: "))  
    p.append(pr)
for j in range (n): 
    l = float(input(f"Enter the length of the sample values {j + 1}: "))  
    lk.append(l)

for k in range (n):
    Avg1 = p[k] * lk[k]
    L = L + Avg1

for k in range (n):
    e = p[k] * math.log(1 / p[k], 2)
    hs = hs + e
hs = round(hs,3)

eff = hs / L
eff = round(eff,3)

red =  round(1 - eff,3) 

var = 0
for k in range(n):
    var1 = p[k] * (lk[k]-L)**2
    var = var + var1
var = round(var,3)
print()
print(f"Average Codeword Length is : {L}")
print(f"Entropy is : {hs}")
print(f"Efficiency is : {eff*100} %")
print(f"Redudancy is : {red}")
print(f"Variance is : {var}")
```

## Calculation
![image](https://github.com/user-attachments/assets/7f00b9b9-6019-4827-9f11-02287d3225b6)
![WhatsApp Image 2025-03-28 at 21 04 52_dd8433cc](https://github.com/user-attachments/assets/68b707ad-96c0-4298-859b-3b762de46044)
![WhatsApp Image 2025-03-28 at 21 04 53_942779c3](https://github.com/user-attachments/assets/cdd7822c-1802-4c9d-b8d4-69f57d9e42ea)

## Results.
For the given probabilities 0.125,0.0625,0.25,0.0625,0.125,0.125,0.25
Average Codeword Length is : 2.625 Entropy is : 2.625 Efficiency is : 100.0 % Redudancy is : 0.0 Variance is : 0.484
