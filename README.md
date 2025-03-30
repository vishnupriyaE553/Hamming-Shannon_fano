# Huffman-Shannon_fano
Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. Apply the Huffman and Shannon-Fano to this source. Show that draw the tree diagram, the average code word length, Entropy, Variance, Redundancy, Efficiency.

AIM: 
    To compute the Average Codeword Length, Entropy, Efficiency, Redundancy, and Variance for a discrete memoryless source using Huffman and Shannon-Fano coding based on the given probabilities and codeword lengths.

TOOLS REQUIRED: 

  Python: A versatile programming language used for scientific computing and signal processing. 
  NumPy: A powerful numerical library in Python for performing array-based operations and mathematical computations. 
  Matplotlib: A plotting library for generating high-quality graphs and visualizations of data, essentialfor demonstrating the sampling process.

PROGRAM:
~~~
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
# Avg length of the code word
for k in range (n):
    Avg1 = p[k] * lk[k]
    L = L + Avg1
# Entropy
for k in range (n):
    e = p[k] * math.log(1 / p[k], 2)
    hs = hs + e
hs = round(hs,3)
# Efficiency
eff =  hs / L
eff = round(eff,3)
# Redundancy 
red =  round(1 - eff,3) 
# Variance
var = 0
for k in range(n):
    var1 = p[k] * (lk[k]-L)**2
    var = var + var1
var = round(var,3)
print(f"Average Codeword Length is : {L}")
print(f"Entropy is : {hs}")
print(f"Efficiency is : {eff}")
print(f"Redudancy is : {red}")
print(f"Variance is : {var}")
~~~

OUTPUT:

![image](https://github.com/user-attachments/assets/b654cd57-b303-42fb-8108-3413ed0b3b83)

CACULATIONS:

![WhatsApp Image 2025-03-30 at 19 26 51_99f007cb](https://github.com/user-attachments/assets/15ea4692-3097-4646-9a19-c0eb224d7621)
![WhatsApp Image 2025-03-30 at 19 26 52_9858893b](https://github.com/user-attachments/assets/fb4c9266-7e42-4b16-af8e-e5c56076538d)
![WhatsApp Image 2025-03-30 at 19 26 52_5f2c39bc](https://github.com/user-attachments/assets/eb5f2c33-a6cd-45fa-aa34-f4cb89647957)

RESULT: 

For the given probabilities 0.125,0.0625,0.25,0.0625,0.125,0.125,0.25

Average Codeword Length is : 2.625 
Entropy is : 2.625 
Efficiency is : 100.0 % 
Redudancy is : 0.0 
Variance is : 0.484
