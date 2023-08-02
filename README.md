# QuantumComputing_and_Qiskit_Tutorial
This repo is for documenting my Quantum Computing learning journey using Qiskit.org tutorials which uses IBM Quantum Lab environment. I will also attach my handwritten notes and Medium blog links which are part of my submissions for #Quantum30, a quantum computing awareness initiative by Quantum Computing India
## Why Quantum Computing
### Notes-:
1. Algorithms are measured by their complexity which basically means the resources( time and space) consumed by it as a function of the scale of the input( input/problem size)
2. Many real-world computer science problems are intractable, i.e they can be solved in theory but are too computationally expensive to solve in reality- for example, factorization of huge numbers- more specifically RSA numbers which form the basis of cryptography.
3. Quantum computers can carry out more efficient algorithms unlike classical ones and bring down computation time
4. Right now, QCs available are very small and resource-limited so it doesn't make sense to invest money in performing simple tasks using them instead of using usual computers.
5. But the quantum advantage is not too far away with development in technology.
6. One problem with QC is data representation which needs lot of qubits.
7. Second problem is quantum error rates and noisy results which demand lot of error correction
8. Quantum phenomenon are usually very delicate and are done in laboratories. So when performing the same in computers, a lot of precision is required to eradicate noise.
9. I had the opportunity to borrow runtime from an actual quantum computer hosted by IBM (not simulation) and plot the probabilistic results of a quantum circuit made using Qiskit software package.
10. 4000 iterations were ran. The plot was supposed to have 000 half of the time and 111 the other half. But due to noisy results, there were some other unexpected values too in the plot.

Blog Link-: https://medium.com/@mohorb04/quantum-computing-challenges-possibilities-a850911730df

## The atoms of computation
### Notes-:
1. Today's learning involved coding in qiskit using IBM Quantum Lab Environment. We started with understanding binary (bit) representation and extending that to the quantum space.
2. We first imported the QuantumCircuit class from qiskit to set up a basic quantum circuit. It had two arguments to be passed into it-: number of input qubits (mandatory) and number of classical bits( optional) to hold the qubit measurements.
3. This was followed by usage of NOT gate to flip the by-default 0 valued input gates. This was achieved using .x method of quantum circuit class.
4. All these circuits were run using a quantum simulator. It is a simulation of an ideal quantum computer by a traditional computer. But this is limited to only operations involving few qubits ( about 30) as it gets difficult to model too many qubits. We used a Aer simulator.
5. This was followed by analysis of how a half adder circuit functions to add 2 numbers ( represented in bits). A half adder circuit can add 2 bits at a time and uses column wise addition and carry over bits to accomplish addition of multi bit numbers.
6. A half adder circuit uses another kind of gate called CNOT gate ( controlled-not gate) implemented using .cx method.
7. CNOT is quantum equivalent of A XOR B where A is control qubit and B is target qubit. Control qubit stays unchanged and target one inverts iff control qubit is 1. This is used to find the rightmost digit of the sum( if we consider the case of adding 2 two-bit numbers)
8. The third gate used by half adders is the Toffoli gate which is equivalent to AND gate. It is a 3 input gate with 2 control qubits and one target qubit. So it is implemented using .ccx (controlled-controlled-not). It is a universal and reversible gate.
9. The Toffoli gate is the simplest element using which any kind of program can be made.
10. This half adder circuit can be used to add any set of numbers of any size.

Blog Link-: https://medium.com/@mohorb04/todays-learning-session-involved-delving-into-the-fascinating-world-of-quantum-computing-using-762686baf7f1





