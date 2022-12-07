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
Function random(min,max): outputs a random integer between min and max with uniform distribution. Uses the Fast Dice Roller Algorithm with Rejection Sampling. This takes an input of some integer n and returns an unbiased integer, called c, from the set {0, 1, 2, ..., n-1}. To get an output from the set {min, min+1, ..., max-1, max}, we simply define n = (max+1)-min first, and at the end, redefine c such that c = c+min. This only works for series of number with length 2^k, so this uses rejection sampling, adding a loop such that if c>max, reset c and v and rerun the loop
