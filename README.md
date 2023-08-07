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

Blog Link-: https://medium.com/@mohorb04/exploring-the-world-of-quantum-computing-a-journey-into-qubits-and-quantum-gates-106dd074c054

## Describing quantum computers
### Notes-:
1. Quantum states are represented by state vectors which are a list of 2^n numbers ( probability amplitudes)representative of the 2^n possible outcomes/states of a n qubit system.
2. State vectors are denoted using ket notation.
3. Quantum states are also represented by complex numbers as the latter have magnitude and direction (phase) both like the former.
4. All vectors aren't valid state vectors as the sum of the amplitude squares of all outcomes must be 1.
5. The |00>,|01>,|10> and |11> vectors are the 4 basis vectors as any 2 qubit system can be represented as their combination. They comprise the computational basis.
6. |+> and |-> are also basis vectors for one qubit systems and are equal to (1/sqrt2)[1 1] and (1/sqrt2)[1 -1] respectively.
7. Phases aren't physically interpretable so even if we rotate all amplitudes by same phase, the behavior of the system will be unchanged. We can only gauge the phase differences between amplitudes of various outcomes/states. As long as that is same, 2 systems may be mathematically different but are physically identical.
8. Quantum gates can be represented using matrices containing transition amplitudes which show probability of one state changing into another on application of the gate.
9. Only those transition matrices are valid which result in total probability of 1 in the outcomes when applied to any initial state. For this to be valid, the condition is that the quantum gate must be reversible,i.e we should be able to undo the gate application to get back the initial state from the outcome. Such matrices are called unitary and so quantum gates are called unitaries and are denoted by U.
10. To get the outcome of a quantum operation, we simply carry out matrix multiplication of the gate's transition matrix with the given initial state vector.

Blog Link-: https://medium.com/@mohorb04/understanding-quantum-states-and-quantum-gates-4d2463cf78f2

## Entangled states
### Notes-:
1. Today's lesson was about product states and entangled states- explained through the example of various 2-qubit states. The addition of two state vectors is known as superposition.
2. A multi-qubit state is known as product state if it can be expressed as a simple combination of various independant states of multiple single-qubit systems. For example, (1/sqrt2)[1 0 1 0] is a product state which can be expressed as the combination of 2 single qubits with state vectors (1/sqrt2)[1 1] and [1 0]. In qiskit code, the qubits are indexed right to left,i.e |01> means qubit 0 is |1> and qubit 1 is |0>. This is so that they naturally reflect the power of 2 according to their position.
3. This concept of product state is in accordance to rules of combinations of probabilities. This means that the net probability of two unrelated independant events is simply the product of their respective probabilities. Probability is just replaced by amplitude in the context of quantum mechanics.
4. However some 2 qubit states cannot be expressed as a combination of 2 one-qubit systems. These are known as entangled states. For example-: [1 0 0 1].
5. It is impossible to find single qubit systems that can combine using the laws of probability to yield an entangled state

Blog Link-: https://medium.com/@mohorb04/understanding-product-states-and-entangled-states-6b3f2b2b45f3

## Entangled states (contd.)
### Notes-:
1. Today's lesson was about creating entanglement using various quantum gates. Most quantum operations start out with a product state, most commonly |00>.
2. But if we keep applying singe qubit gates like the H gate to them, they will remain in product state irrespective of the single qubit systems turning into complex superpositions (independently)
3. Entanglement can be generated using multi-qubit gates like controlled gates (cx and cz)
4. One standard interpretation of cx gate is controlled-x or controlled-NOT gate, which means that x operation(bit flip) will happen on the target bit iff control bit is 1.
5. Entanglement is created when the control qubit is in the superposition state instead of pure 1 or 0. For instance, |+0>. Here the cx gate when applied with bit 1 as control, will act parallely on both states to create an entangled state |psi superscript +>.
6. The standard interpretation of cz gate is that iff control bit is 1, then it does z operation of target. z operation means that if bit is 0, then nothing changes and if 1, then it is imparted a phase of -1. So, a cz gate has some visible impact only when both the initial qubits are in 1 state. In all other cases, it leaves things unchanged irrelative to what has been labelled as control and target.
7. In a similar manner, CNOT gate can be interpreted in 2 contradictory ways. In contrast to standard way, we can look at it as doing a z gate operation on the control bit iff target is |-> and doing nothing if it is |+>
8. This is the phase kickback phenomenon in which if both control and target bits are superpositions then some features of the target gets fed back into the control qubit.

Blog Link-: https://medium.com/@mohorb04/understanding-quantum-entanglement-and-gates-daa8857eab32

## Entangled states (contd.)
### Notes-:
1. Today's lesson was entirely about quantum entanglement and was pretty confusing. It started with why we need to harness the power of entanglement. If we just settle for using product states then we will have to just maintain 2n amplitudes for n qubits, something which is achievable even by a classical computer. But to get the quantum advantage, we need to be able to achieve something more, which cannot be done by classical systems. (like maintaining 2powern records). This can be done by leveraging quantum entanglement.
2. Here, entanglement was dealt with by using quantum communication protocol. In classical system, n bits can transfer only n bits of info. In quantum, same rule applies, i.e at the most n bits of info can be encoded and retrieved from n qubits. But we can transfer just one qubit to send across a 2bit message using entanglement.
3. Standard way of communicating a 2 bit message by just encoding it on one end and then sending across to be measured at the other end doesn't entail any entanglement. But entanglement can be introduced by using h and cx gates after encoding and disentangling at the other end by applying h and cx gates again in opposite sequence before measuring. But even this doesn't really give any edge over the previous method.
4. So, we explored the relationship between the 4 entangled states which result from the 4 kinds of encoded messages-: 11,00,01 and 10. It was found that they all be obtained from psi + using z and x gates and thus, can be rotated into each other quite easily. Also, the z and x gates can be applied on either of the 2 qubits involved. So an alternate modus operandi for the sending party would be to first make the entangled state from 00 and then encode it according to the actual message string to be sent using x and z gates.
5. The key point here is that the x and z gates can be applied on any of the 2 qubits. So the sender can send one of the qubits to the receiver at first only, once the entangled pair has been set up. This can be done even before the sender knows what message is to be sent. This can be harnessed if there was a third person who was encoding the entangled pair first and  then sending out one bit to sender and other to receiver. the sender can then encode the message by just manipulating the single bit he/she gets. Because this single bit is part of an entangled pair, manipulating it affects a larger set of 4 possible 2 qubit quantum states( involving the bit with the sender and the one with the receiver). Thus, sender ultimately sends this manipulated bit the destination where it is measured with the already present bit to decode the message. Thus, sender sent out one qubit to send a 2 bit info using entanglement.
   
Blog Link-: https://medium.com/@mohorb04/harnessing-quantum-entanglement-for-efficient-information-transmission-1040aa463868
