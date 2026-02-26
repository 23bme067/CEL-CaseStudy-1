# CEL-CaseStudy-1
Determination of Unknown Reactions in a Statically Determinate Beam System
Author: Kathan Patel
Roll No: 23BME067
Course: Engineering Mathematics / Linear Algebra
Tool Used: MATLAB

1. Project Overview
This case study analyzes a statically determinate simply supported beam subjected to external loading.
The objective is to determine the unknown support reactions using:
	Static equilibrium equations
	Matrix formulation
	MATLAB linear algebra solution
The problem demonstrates how engineering mechanics and linear algebra combine to solve structural systems efficiently.
2. Problem Description
A simply supported beam of length L = 6 m is subjected to a point load of 10 kN located 2 m from the left support (A).


Given:
	Beam length (L) = 6 m
	Point Load (P) = 10 kN
	Distance from A (a) = 2 m
Unknowns:
	R_A→ Reaction at support A
	R_B→ Reaction at support B
Since the structure is statically determinate, the number of unknown reactions equals the number of equilibrium equations.

3. Mathematical Formulation
3.1 Equilibrium Conditions
For a 2D beam system:
∑F_y=0
∑M_A=0


3.2 Force Equilibrium
R_A+R_B-P=0
R_A+R_B=10

3.3 Moment Equilibrium (About A)
R_B⋅L-P⋅a=0
6R_B-10(2)=0
6R_B=20
R_B=3.33" kN"

Substituting:
R_A=10-3.33=6.67" kN"


4. Matrix Formulation
The equilibrium equations can be written in matrix form:
[■(1&1@0&6)][█(R_A@R_B )]=[█(10@20)]

General Linear Algebra Form:
[A][R]=[B]

Where:
	A→ Coefficient matrix
	R→ Reaction vector
	B→ Load vector
Solution:
[R]=A^(-1) B


5. MATLAB Implementation
% 23BME067 - Kathan Patel

clc;
clear;

% Beam Data
L = 6;        % Length (m)
P = 10;       % Load (kN)
a = 2;        % Distance from A (m)

% Coefficient Matrix
A = [1 1;
     0 L];

% Load Vector
B = [P;
     P*a];

% Solve Linear System
R = A \ B;

% Display Results
disp('Support Reactions:')
disp('-------------------')
disp(['Reaction at A (RA): ', num2str(R(1)), ' kN'])
disp(['Reaction at B (RB): ', num2str(R(2)), ' kN'])



Output:
Support Reactions:
-------------------
Reaction at A (RA): 6.6667 kN
Reaction at B (RB): 3.3333 kN



6. Computed Results               
Support	Reaction (kN)
A	6.67
B	3.33

Verification:
	R_A+R_B=10kN 
	Moment equilibrium satisfied 
	
7. Engineering Interpretation
	Left support carries higher load because the point load is closer to A.
	The system satisfies all equilibrium conditions.
	Linear algebra provides a systematic way to solve structural equations.
	This approach can be extended to more complex multi-support systems.

8. Stability Concept
For a statically determinate structure:
	Number of unknown reactions = Number of independent equilibrium equations
	Determinant of coefficient matrix ≠ 0
	Unique solution exists
Since:
det(A)=6≠0

The system has a unique stable solution.

9. Learning Outcomes
	Application of equilibrium equations
	Conversion of physical system into matrix form
	Solving simultaneous equations using MATLAB
	Understanding of statically determinate structures
	Verification of engineering results
 

 10. Future Enhancements
	Extend to Uniformly Distributed Load (UDL) case
	Compute Shear Force and Bending Moment Diagrams
	Perform symbolic solution using MATLAB
	Analyze statically indeterminate beam
	Convert implementation to Python (NumPy)

11. References
	Hibbeler – Engineering Mechanics (Statics)
	Bansal – Engineering Mechanics
	Gilbert Strang – Linear Algebra and Its Applications
	MATLAB Documentation – Matrix Computations

Conclusion
This case study successfully determines the unknown reactions of a statically determinate beam using equilibrium equations and matrix algebra.
By solving the system:
[A][R]=[B]

the support reactions are obtained efficiently using MATLAB.
This demonstrates the powerful application of linear algebra in structural engineering analysis.

