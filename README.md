# Quantum_Algorithms_ORNL_2025
ORNL Internship (2025) - Quantum Computing Algorithm Efficiency

In the summer of 2025, I completed the Next Generation Pathways to Computing (NGP) Internship at Oak Ridge National Laboratory. I worked with a fellow student, Kaiser Ramjee, and a postdoctorate researcher, Dr. Anshumitra Baul for a period of five weeks. This project introduced the fundamentals of quantum computing and contributed to discussions in the field about the efficiency of quantum algorithms.

## Goal <br>
1. Examine the use of a variational quantum eigensolver (VQE) through the application to a transverse field Ising model
2. Compare the accuracy of a VQE to exact diagonzalization solutions and analyze VQE limitations
<br>

## Method <br>
Detailed background required for this project can be found in the paper file in the Github Repo. <br>
1. Learn Quantum background by completing IBM Basics of Quantum Information Course <br>
2. Determine most efficient ansatz for VQE and efficient simulations <br> 
3. Analyze a two-qubit Ising model by looking at ground state convergence and magnetization values <br>
4. Complicate the model to four-qubits, performing similar analyses, to determine limitations of VQE algorithms <br>

## Results
### Ansatz Comparison <br>
In a variational quantum eigensolver, a particular ansatz (quantum circuit) must be utilized. To ensure future simulations were as efficient as possible, a comparison of the percent error and the average iterations required for convergence was completed on the following ansatzes: TwoLocal, EfficientSU2, QAOA, RealAmplitudes. <br>

The QAOA Ansatz was determined to be the most optimal due to its low percent error and relatively low number of iterations required to converge. <br>

### Two-Qubit Ising Model <br>
#### Ground State Energy Convergence <br>
The two-qubit model was initially run without a transverse magnetic field imposed to ensure proper convergence. Then, simulations with varying field strengths were implemented to determine the accuracy of the VQE while still solving for ground state energies in more complex systems.<br>

<img width="578" height="455" alt="Figure 15 - gse and vqe with h vary two qubit" src="https://github.com/user-attachments/assets/44be5f98-1110-4747-b6cf-90be3b290e2e" />

While there was still some variation between the VQE and theoretical solution, the general shape is nearly identical.<br>

#### Magnetization with Varying Field
The model was expanded to solve for the magnetization of the two-qubit model in the Z-direction (identifying spin directions). The VQE was identical to the theoretical solution, highlighting the algorithms' strengths on small systems.<br>

### Four-Qubit Ising Model <br>
#### Ground State Eenrgy Convergence <br>
The four-qubit Ising model underwent a similar ground-state energy convergence calculation process. However, it was yielding erratic results so an averaged simulation result across five simulations per field strength was utilized as the final result. <br>

<img width="610" height="455" alt="Figure 20 - 5iters gse vs h 4 qubit" src="https://github.com/user-attachments/assets/4a174bb1-f15b-4b00-9379-605a2c08c1cd" />


The variation between the VQE and theoretical ground-state energies varied significantly more. This behaviour is interpreted as the result of a more complex model that utilized a fairly simple algorithm for computation. <br>

#### Magnetization with Varying Field <br>
The four-qubit model was expanded to solve for the magnetization in the Z-direction (identifying spin directions). The VQE had a similar shape to the theoretical solution, but its accuracy varied wildly across field strengths.<br>

## Conclusions
- More complex systems require more computational power that is difficult to achieve with Python
- VQE algorithms have difficulty converging around a phase transition state

## Extensions
- Include simulation of noise within models to determine potential impacts of using VQE on real quantum computer
- Simulate different spin models with varying interactions

## Files
*2_Qubit_Ising_Looped_GroundState_Conv_CODE.ipynb* - Python file containing the initial two-qubit model convergence to ground-state energies (code file 1/4 for project) <br>
*2_Qubit_Ising_Magnetization_CODE.ipynb* - Python file containing two-qubit Ising model where magnetization values determined (code file 2/4 for project)<br>
*4_Qubit_Ising_Looped_GroundState_Conv_CODE.ipynb* - Python file containing a four-qubit Ising model and investigation into ground-state convergence (code file 3/4 for project) <br>
*4_Qubit_Ising_Magnetization_CODE.ipynb* - Python file containing four-qubit Ising model where magnetization values determined and investigated (code file 4/4 for project) <br>
*Variational Quantum Eigensolver Simulations for Multi-Qubit Ising Models - Harrison, Ramjee, NGP (1).pdf* - official ORNL Internship poster product <br>
