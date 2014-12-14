#Project 2

---------------

This Document is out of date please refer to Documentation 

---------------------

##Problem 1: Loop Control
 Make function called loopTest(N) that loops through the values 1 through N and for each
number n it should display ‘n is divisible by 2’, ‘n is divisible by 3’, ‘n is divisible by 2 AND 3’ or ‘n is NOT
divisible by 2 or 3’. Use a for loop, the function mod or rem to figure out if a number is divisible by 2 or
3, and num2str to convert each number to a string for displaying. You can use any combination of if,
else, and elseif. 

```
n = input('Input the number of terms n = ');
loops = 1:n;
disp(loops);
a = 2;
b = 3;
for i = n:-1:1;
    c = rem(i,a);
    d = rem(i,b);
    
%If statement to analyze input for n to see if divisible by 2 AND (or) 3 or NOT     
    if c==0 && d ==0
    disp('n is divisible by 2 AND 3')
elseif  c~=0 && d~=0
    disp('n is NOT divisible by 2 or 3')
elseif c == 0
    disp('n is divisible by 2')
elseif d == 0
    disp('n is divisible by 3')
    end 
end
```

##Problem 2:  Quadratic Equation

Make function Quadratic (A,B,C) that will solve the quadratic equation
 A*x2 +B*x +C= 0
The function will return the solution vector [x1 x2 ]. Now you all know how to solve this
equation and that depending on the sign of the discriminant Δ, the solution x1 , x2 can be real, real and
equal or complex; so much sure to consider all those cases in the body of the function. You can use if
and elseif statements in the body of the function.
function [ x1 x2 ] =quadratic( A,B,C)

%Create a Quadratic (A,B,C) Eqution A*x^2 +B*x +C= 0

````

A = input('Please input the value for A:'); 
B = input('Please input the value for B:'); 
C = input('Please input the value for C:'); 
x1 = (-B + sqrt((B^2) - 4*A*C))/(2*A); 
x2 = (-B - sqrt((B^2) - 4*A*C))/(2*A); 
disp(x1) 
disp(x2) 

````
##Problem 3: Mesh Current Analysis #3

Consider the circuit in figure 1. Use mesh current analysis method to obtain the necessary equations to
solve for the currents I1, I2 and I3. Next , use Matlab to determine the numerical value of the same
currents. All the values below should be netered through keyboard.

````

a = [11 -1 -10; 0 7 -7; -10 -4 19];% create matrix A
b = [10; 0; 0];                    %create vector b


det_a = det(a);                    % find the determinant
x = a\b                            % find x 

````


##Problem 4: Working with a data file 
Refer to the data table 1 on page 3 .
In that table, the amino acids in proteins molecules of oxygen ( O), carbon (C ), nitrogen ( N ), sulfur ( S)
and hydrogen (H) are listed.
a/ create a data file elements.dat to save the table.
b/ write a Matlab program to compute the molecular weight of each amino acid in table 1, assuming
that the numeric information in the table can be reloaded .
c/ generate a new data file named weights.dat that contains the molecular weights of the amino acids.
Use matrix operations to compute the molecular weigths.

```
%Set the Atomic Weights 

Oxygen = 15.994; 
Carbon = 12.011; 
Nitrogen = 14.00674; 
Sulfur = 32.066; 
Hydrogen = 1.00791;
t = ['O'; 'C'; 'N'; 'S'; 'H'];
v = [15.9994, 12.011, 14.00674, 32.066, 1.00791];
disp('Molecular Weights')
disp(t)
disp(v')



save weight.dat 
alanine = v*[2; 3; 1; 0; 7]; 
arginine = v*[2; 6; 4; 0; 15]; 
aspargine = v*[3; 4; 2; 0; 8]; 
arpartic = v*[4;4;1;0;6];
cysteine = v*[2;3;1;1;7]; 
glutamic = v*[4;5;1;0;8]; 
glutamine = v*[3;5;2;0;10]; 
glycine = v*[2;2;1;0;5];
histidine = v*[2;6;3;0;10]; 
isoleucine= v*[2;6;1;0;13]; 
leucine = v*[2;6;1;0;13];
lysine = v*[2;6;1;0;13]; 
methionine = v*[2;5;1;1;11]; 
phenylanlanine = v*[2;9;1;0;11];
proline = v*[2;5;1;0;10]; 
serine = v*[3;3;1;0;7]; 
threonine = v*[3;4;1;0;9]; 
tryptophan = v*[2;11;2;0;11];
valine = v*[2;5;1;0;11];
Aweights = [alanine; arginine; aspargine; arpartic; cysteine; glutamic; 
glutamine; glycine;histidine; isoleucine; leucine; 
			lysine; methionine; phenylanlanine; proline; 	
			serine;threonine; tryptophan; valine];
 
disp(Aweights)
```
##Problem 5:

A small rocket is being designed to make wind shear measurements in the vicinity of
thunderstorms. Before testing begins, the designers are developing a simulation of the rocket’s
trajectory. They have derived the following equation that they believe will predict the
performances of the test rocket, where t is the elapsed time in seconds.

"height= 60 + 2.13t2 -0.0013t4+ 0.000034t4.751"
 
The equation gives the height above ground level at time t. The first term (60) is the height in feet
above the ground level of the nose of the rocket.
Write a Matlab program that will print the time and height of the rocket from t=0 to the time that it
hits the ground, in increments of 2 seconds.
If the rocket has not hit the ground within 100 seconds, print values only up through 100 seconds.
 
````

for i=2:100   
t(i)=i+2; 
    h(i)=60+(2.13*(t(i))^2)-(0.0013*(t(i))^4)+(0.000034*(t(i))^4.751);
 
 if h(i)>0
    disp('at t=');
    disp(t(i));
    disp('the height is');
    disp(h(i));
    
elseif  h(i)<0
    disp('the rocket has hit ground');
    end 
   
end

````