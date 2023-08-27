# QuantumComputing_and_Qiskit_Tutorial
This repo is for documenting my Quantum Computing learning journey using Qiskit.org tutorials which uses IBM Quantum Lab environment. I will also attach my handwritten notes and Medium blog links which are part of my submissions for #Quantum30, a quantum computing awareness initiative by Quantum Computing India.
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

## Entangled states (contd.)
### Notes-:
1. Today's lesson explored the famous Heisenberg's uncertainty principle by comparing a classical experiment with its quantum analogy. The experiment involved Charlie packaging objects of certain shape and certain colour to Alice and Bob, one shape to each and the same pair repeatedly. However, Alice and Bob can see only one aspect of the object received: either its colour or its shape.
2. So, after looking over several days, Alice and Bob come to two inferences that both cannot receive a cube and if one doesn't get a blue object, then other would have got a cube. Applying these inferences, they conclude that one of them will always get a blue shape.  Such a deterministic conclusion can be made because both colour and shape of objects are simultaneously well-defined properties. So there are certain constraints on classical correlations.
3. To draw a quantum analogy, the objects are replaced by qubits. So Charlie makes an entangled state and sends one qubit each to Alice and Bob. Here the two kinds of measurements that cannot be done together were defined to be the x and z measurement.
4. z measurement is the normal measurement of a qubit done by the usual measure gate.
5. X measurement refers to applying a H gate to the qubit and then measuring it by a measure gate.
6. I also learnt about the Ry gate that is used to rotate qubits about the y axis by various specified angles.
7. For a 0 qubit and 1 qubit, z measurement yields 0 and 1 with 100 % probability. But x measurement gives random probability of measuring both. Vice versa is true for |+> and |-> states. It is around 50-50 in the random results.
8. This is a manifestation of the Heisenberg uncertainty principle which says that certain pairs of attributes of quantum systems cannot be known with high accuracy simultaneously. This doesn't apply to classical bodies. For example, the outcomes of X and Z measurements cannot be both known with high accuracy.
9. A quantity <z>=P(0)-P(1) is defined. This has max value 1 if qubit is purely 0 and min of -1 if it is 1. However for a purely random state it is 0. This shared accuracy is shown in the uncertainty equation <z>^2+<x>^2<=1. So we have 2 options for encoding a bit of information in qubits-: either in the 0-1 system or in the |+>-|-> system. For the former we use Z, for the latter X. But we cannot do both with an acceptable level of certainty in both.
10. This also reflects in the quantum analogy of the earlier experiment. Alice and Bob conclude that if z base is used by both, then both cannot be 0 (as 00 doesn't come up) and if the x base for one outputs 1, then the z base for other must output 0 as 11 doesn't appear as a likely possibility. Thus, similar to the earlier conclusion, here also they may conclude that if both of them use x base, then they can never get 11 as output. However, their hypothesis when tested turns out incorrect as although less, there is some possibility of 11 coming up. This shows the unique correlations between qubits in an entangled pair which is a special characteristic of such pairs. The results of qubits aren't well defined before measuring (unlike shape and colour) and therefore they are way more random than classical counterparts.

Blog Link-: https://medium.com/@mohorb04/exploring-heisenbergs-uncertainty-principle-through-classical-and-quantum-experiments-9f9bdef7f4d0

## Visualizing Entanglement
### Notes-:
1. Today's lesson was about visualizing qubits, 1 qubit at a time and two at once using the run_puzzle method of hello_qiskit module.
2. The inferences from the visualizations were that when qubit is in a pure 0 or 1 state then Z measurement gives a deterministic result while X measurement yields a random result (50-50 probability ) of 0 and 1 as outcomes.
3. Also, when we start out with + or - qubits then results are swapped for X and Z measurements.
4. When ry gate is applied with pi/4  rotation (repeatedly) and bloch command is used to superimpose the X and Z measurement illustrations, then it is seen that the dot where the probability levels intersect goes through some rotation with each successive ry rotation.

Blog Link-: https://medium.com/@mohorb04/demystifying-qubits-through-visualizations-insights-from-hello-qiskits-run-puzzle-method-e178a0e29a8

## Visualizing Entanglement (contd.)
### Notes-:
1. Today's lesson used the run_puzzle method from hello_qiskit to visualize two qubits at once. Thus a grid with 4 new lines was introduced.
2. Two of the lines corresponded to probability of both qubits disagreeing when both were subjected to x and z measurements.
3. The other 2 lines represented probability of the qubits disagreeing when one is subjected to X and the other to Z.
4. The application of X gate simply flips Z measurment outcome while keeping X unchanged. So performing X gate on one of the qubits affects one whole row in the grid.
5. The application of H gate swaps Z and X measurement outcomes. So applying H gate on one of the qubits swaps whole rows in the grid.

Blog Link-: https://medium.com/@mohorb04/visualizing-2-qubit-dynamics-with-qiskits-run-puzzle-method-39cbe10a8b6b

## Grover's search algorithm
### Notes-:
1. The binary search algorithm is a very efficient classical algorithm with a logarithmic time complexity. But it is constrained in its ability to search only sorted lists. This becomes a bottleneck when looking up unsorted databases.
2. Databases are considered to be like blackboxes that simply give an output when queried with an input (like for searching a certain entry) without concerning the users with the internal workings. Such blackboxes are often called oracles.
3. As the only classical way to look up unsorted lists is random search which grows linearly with list size, indexing of databases becomes paramount even though it is memory intensive to do it.
4. Thus, in such a scenario, the Grover’s quantum search algorithm comes to the rescue by offering a quadratic speedup over its classical counterpart.
5. It guarantees a square root time complexity by enabling the database to input and output quantum superposition states when queried.

Blog Link-: https://medium.com/@mohorb04/introduction-to-grovers-search-algorithm-43b9f7a29b48

## Grover's search algorithm (contd.)
### Notes-:
1. Various computer science problems can be conveniently modelled into database search problems which can further be resolved by quantum search algorithms.
2. One example given was of sudoku. Given a certain solution, we can easily check whether it is valid or not. Thus, we can also look at this problem as a database search problem wherein the solver is querying us (the database) in search of an input ( a certain solution of the grid) that yields the output “valid” if it satisfies the rules of the game.
3. So, such problems deal with “finding an input that gives a certain output”.
4. Boolean Satisfiability Problems, also called SAT problems are a class of problems that are solved in this manner.
5. In fact, a lot of other computational problems can also be treated as SAT problems. The problem is basically a set of clauses (conditions) on the various possible bit combinations. The solution to such a problem is a bit string that satisfies all the clauses.

Blog Link-: https://medium.com/@mohorb04/database-search-problems-50a7630f027b

## Grover's search algorithm (contd.)
### Notes-:
1. We can represent all solution states together as one vector, say A. This vector A is the superposition of all solution state vectors. All other non-solution state vectors are superposed to form another vector B.
2. As vectors A and B don’t have any component in common, they are perpendicular vectors and thus a coordinate plane can be setup with the two vectors as Y and X axes respectively.
3. The initialisation step of the algorithm involves creating an equal superposition state of all computational basis vectors (like by applying an H gate to each qubit).
4. Since each state is either a solution state or a non-solution state, the initial vector can be plotted between the 2 axes on the coordinate plane set up earlier.
5. As there will be generally more non-solution states than solution states, the initial vector will be more closely inclined to the axis B than A.
6. The goal of this algorithm is to get the plotted state vector as close as possible to the A axis (solution state axis) via various geometric manipulations.
7. Such manipulations comprise of rotating the vector about the B axis followed by rotating it again about the very first plotted vector. The resultant vector is closer to the A axis now.
8. If this sequence of manipulations is repeated, then the state vector will keep moving progressively closer to the A axis and finally, we will get the desired solution states.
   
Blog Link-: https://medium.com/@mohorb04/high-level-overview-of-grovers-search-algorithm-668effdc5afc

## Grover's search algorithm (contd.)
### Notes-:
1. The first step in the algorithm requires us to create an equal superposition state of all possible inputs to the oracle.
2. This may be done by applying a H gate to each qubit, suppose if each qubit starts out in the 0 state. This resultant initial vector is called the s vector.
3. This is followed by applying the oracle circuit (U) on all the qubits. This selectively reverses the phases of all solution states in the earlier superposition created.
4. Finally, the diffusion operator is applied.
5. The second and third steps usually need to be repeated sqrtn number of times due to a simple mathematical logic. If the initial angle between s vector and x axis is theta, then each round of the 2nd and 3rd step rotates the s vector towards the y axis (our motive) by 2 times theta. Thus, number of rounds required will be roughly one right angle divided by 2*theta.
6. The theta comes out to be 1/sqrtn radians by simple trigonometry and small angle approximation where n is the number of possible inputs (in a single solution problem). This makes the number of iterations equal to (pi/4)*(sqrtn),i.e proportional to sqrtn.
7. Applying the steps repeatedly thus gets our s vector closer and closer to the y axis which increases the probability of getting the solution states upon measurement at the end.

Blog Link-: https://medium.com/@mohorb04/a-deep-dive-into-grovers-search-5adcbae5a490

## Grover's search algorithm (contd.)
### Notes-:
1. Random guessing strategies grow linearly with increase in input search space size. The input search space increases exponentially with the number of bits (2 power n). Thus, random guessing algorithms also grow exponentially with the number of bits.
2. Drawing from that and the fact that Grover’s search does sqrtN iterations (where N is input search space size), it grows at the rate of 2 power n/2.
3. Another algorithm was mentioned called Schoning’s algorithm. Despite being a classical algorithm, it grows at a rate of roughly 1.3334 power n (for 3-SAT problems) which is faster than even Grover’s search. It exploits the special feature of SAT problems, the fact that SAT problems are simply sets of independent clauses which need to be fulfilled by the correct solution.
4. So if an initial random guess doesn’t work, then that failed guess is not disposed off. Rather, a few bits in it are toggled to make it satisfy the clauses it failed. This may result in it violating a few new clauses but on an average, this kind of iteration strategy proves more efficient.
5. An even more efficient search strategy can be designed by combining the Grover’s search and Schoning’s search algorithms. This uses the latter’s bit toggling strategy in the oracle circuit of the former. This thus makes good use of the inherent structures in SAT problems.

Blog Link-: https://medium.com/@mohorb04/growth-rate-of-search-algorithms-3d896e664d84

## Single systems 
### Notes-:
1. The topic of classical information is seemingly unrelated to quantum information but is actually very essential as an analogy to understand the more advanced ideas in the latter.
2. A system was defined to be an abstraction of a physical entity that stores information.
3. If at every instant, this system is in one of several states (finite number) that can be recognized unambiguously, then those states are called classical states and the system is defined to be classical.
4. For the lesson, we assumed that there could only be a finite number of states and that sigma denoted the set of classical states for a classical system. Few examples of classical systems given were a bit (states 1 and 0), a six sided die, a switch and so on.
5. The idea of probability vectors was introduced as a convenient way to represent the probabilistic state of a classical system. The probabilities of a system being in its different classical states was combined into a vector of dimension equal to the cardinality of the sigma set. This was done to make it easier to use these probabilities later in various vector/matrix calculations.
6. The two intuitive conditions satisfied by any such probability vector were-: each of its entry must a non-negative real number and all the entries must sum up to a total probability of 1.

Blog Link-: https://medium.com/@mohorb04/classical-information-part-1-bf41803fed

## Single systems (contd.)
### Notes-:
1. If a classical system has n total possible classical states that it can exist in, then an n dimensional vector (with each dimension representing a state) with entry as 1 for one state and 0 for the rest is called a standard basis vector.
2. Each n dimensional vector (probability vectors) can be expressed as a linear combination of these n n-dimensional vectors.
3. The main difference between a classical state and a probabilistic state is the extent of our knowledge of the system state. Measurement of a system state involves knowing with certainty that the system is in a certain state (the one in which it is observed when measured). This makes us update both the classical state and probabilistic state to be a standard basis vector with 1 as the entry for the measured state.
4. However, had we not measured the state, the probabilistic vector would have been a linear combination of all possible states with coefficients equal to the square roots of probabilities. The probability of a state would be given by the perceived chance of getting that state upon measurement.
5. This is where quantum behaviour takes a spooky turn. Their measurement properties are considered as unusual in this regard.

Blog Link-: https://medium.com/@mohorb04/probabilistic-states-915be8141b50

## Introduction
### Notes-:
1. Classical Machine Learning algorithms have attained massive speedups recently due to availability of more computationally powerful hardware.
2. If quantum ideas are thrown into the mix, the results might be even more optimistic.
3. There are 4 different kinds of intersections of Quantum Computing and Machine Learning- using Classical or Quantum information and running algorithms on either classical or quantum computers.
4. There are two kinds of Quantum algorithms-: those that need qRAM (access to quantum random access memory, i.e data in superposition) and those that don’t. The ones that require qRAM have the potential to provide exponential speedups over their classical counterparts.
5. However, presently there is no available hardware to realise qRAM.

Blog Link-: https://medium.com/@mohorb04/qml-an-introduction-253d4853dd13

## Parameterized quantum circuits
### Notes-:
1. The 2 key characteristics of parameterized circuits that make them fit to be used for QML are Expressibility and Entangling Capability.
2. The main idea is that any parameterized circuit must be generalized well in order to be used as a machine learning model.
3. So, the circuit must output a large subset of the output Hilbert space ( an extension of the 3-dimensional Euclidean space into n possible dimensions) and should also be able to entangle the qubits to ensure that the quantum advantage over classical computers stays intact and it is not easy to simulate the same on the latter.
4. Expressibility is the property for measuring the first clause- coverage of the Hilbert space while Entangling Capability, as the name suggests, sums up the second clause.

Blog Link-: https://medium.com/@mohorb04/properties-of-parameterized-circuits-9cd23f4acc79





