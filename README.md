# QRNG
Examples of quantum random number generators using Qiskit

# InstallQiskit
Run this first, allows you to run quantum simulations in GoogleColab or JupyterNotebook

# ImportLibraries
All the libraries in Qiskit and Python needed to run this

# 1QubitCircuit
A quantum circuit using 1 qubit. Start in state 0 or 1, doesn't matter which, then apply Hadamard gate to put it into superposition (|0>+|1>)/sqrt{2}, then measure the state. This will give 0 or 1 randomly and with equal probability.

# 4QubitCircuit
A quantum circuit using 4 qubits. Start in state 0000 or 1111, doesn't matter which, then apply Hadamard gate to put each bit into superposition (|0>+|1>)/sqrt{2}, then measure the state. This will give 2^4 = 16 possible states randomly and with equal probability.

# CoinFlip
Function coin_flip(): Runs the 1 qubit circuit on the quantum simulator. If state = |1>, output the string 'heads', and if state = |0>, output the string 'tails'.
Function coin_flip01(): The same, except it returns the number 1 or 0 instead.

# RandomMinMax
Function random(min,max): Outputs a random integer between min and max with uniform distribution. Uses the Fast Dice Roller Algorithm with Rejection Sampling. This takes an input of some integer n and returns an unbiased integer, called c, from the set {0, 1, 2, ..., n-1}. To get an output from the set {min, min+1, ..., max-1, max}, we simply define n = (max+1)-min first, and at the end, redefine c such that c = c+min. Steps for the algorithm: start with placeholder variables v=1 and c=0. Create a loop which is always true, so that it only ends once it gets to the 'return' statement. Within the loop, multiply v by 2 and redefine c = 2xc + 0 or 1, depending on the result of the coin flip from the function coin_flip01(). This loops keeps running until v >= n, then returns c as the random integer. This only works for series of number with length 2^k, so this uses rejection sampling, adding a loop such that if c>n, reset c and v and reruns the loop.

# Random09
Function random09(): Outputs a random integer between 0 and 9 with uniform distribution. Runs the 4 qubit circuit on quantum simulator. Contains a series of if-else statements within a loop such that the specific states are assigned integers within the set {0,1,2,3,4,5,6,7,8,9} and if the output is not one of these states, the loop restarts.

# RandomNumDigits
Function random(num_digits): Outputs a random integer between 0 and 9...9, depending on value of num_digits, with uniform distribution. Creates loop while i<num_digits, placeholder = random09()x10^i. Random number = random09()x10^0 + random09()x10^1 + ... + random09()x10^(num__digits-1).
