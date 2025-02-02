# iQuHACK 2025 - Moody's Challenge : Our Solution

We chose our team name to be Icarus knowing well enough that choosing this challenge without any prior exposure to topology was us literally being "Icarus". But the challenge problem seemed so interesting that we had to atleast try and thus, we tried our best, learnt topological structures, understood different quantum algorithms and also brainstormed ideas of how we could replace quantum phase estimation with Algorithmic Shadow Spectroscopy and found ways of doing transforming a Laplacian matrix to a unitary matrix using different techniques. 

First, we computed a point cloud by embedding the provided time series data. We used Taken's embedding method. 

We constructed simplicial complex and had a simplex tree made to determine our boundary operators. Using the boundary operators, we calculated a Laplician matrix. 

After that, we used the Quantum Phase Estimation to calculate the betti numbers of our simplicial complex, which we were supposed to compute with the help of varying epsilon, which is our resolution threshold to determine how the betti numbers change over a certain proximity and the threshold. 

We then moved to the actual dataset for the computation of part 2 and 3. The protocols which were working for test dataset didn't work for the actual data set we were supposed to analyze to detect market crash. So, we moved to understanding why this was happening. 

Bonus questions: 

2. We studied the Variational Quantum Eigensolver Algorithm and also the Algorithmic Shadow Spectroscopy in order to replace the Quantum Phase Estimation part for the above-mentioned protocol because QPE is primarily theoretical, and we found interesting insights about them. 

3. The two ways we found for transforming the Laplacian matrix to a unitary matrix was:
- Transforming the Laplacian into a Hamiltonian operator by a linear combination of tensor products of the Pauli operators. 
- Using the Laplacian normalization equation and finding D^-1/2 L D^-1/2 where D is the matrix representing he degrees of our simplicial complex and L is the Laplacian matrix.

