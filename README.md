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

## What is quantum?
### Notes-:
1. Today's lesson started with a deep dive into quantum physics and how it is different from classical physics. Classical physics refer to sets of rules made for macroscopic bodies. But these rules cannot explain behaviours of electrons/light/microscopic entities. So quantum physics came into being
2. Two instrumental experiments were Ultraviolet catastrophe ( hinted that light has particle nature) and Double-slit experiment( hinted that light had wave nature)
3. 2 common ways used in past to represent bits are punched cards and compact discs. Electron orbitals can also be used. Scientists began wondering if they could design their bits to follow laws of quantum physics instead of classical ones, i.e use qubits.
4. Code written in a classical computer can be used to simulate quantum behaviour to some extent for few qubits only (around till 30) as with increasing qubit requirement, it becomes computationally expensive to store all information about them.
5. Unlike traditional logic gates which are deterministic ( same input always yields same output), probabilistic operations were introduced for example Hadamard gates (H-gates) which can only be applied on qubits.
6. A H-gate applied on a 0 qubit yield 1 and 0 with 50-50 probability. Similarly, when applied on 1. But anomalous behaviour surfaces when 2 H-gates are used sequentially. Then the final output is deterministic, i.e 0 is yielded with 100 percent probability. This shows that normal probability measure cannot be used to model this phenomenon.
7. So probability in quantum jargon is replaced by probability amplitude which has a magnitude and a phase ( direction which cannot be physically seen). Square of magnitude is probability of the state. This as well as the magnitude-phase concept is a mathematical trick which sits so well with the observed phenomena that scientists are convinced of its physical existence too although it is not so conspicuous. It is basically a complex number/vector. Having direction enables interference, i.e 2 qubits with opposite phases can cancel each other to have net 0 magnitude.
8. So the H-gate basically keeps phases of 1 and 0 at the output same when input is 0 but reverts phase of 1 (output)when input is 1. This results in net probability of 1 to be 0 and that of 0 to be 1.
9. Reversal in phase can be represented by a minus sign. It is actually an angle.
10. So the advantage that quantum computers give over classical counterparts is that they can simply conduct experiments on physical qubits to find out the outcome instead of having to spend a lot of memory for keeping track of a lot of amplitudes the quantity of which doubles for each new qubit introduced

Blog link-: https://medium.com/@mohorb04/exploring-the-world-of-quantum-computing-a-journey-into-qubits-and-quantum-gates-106dd074c054





