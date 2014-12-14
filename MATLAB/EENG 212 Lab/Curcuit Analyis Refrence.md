#Matlab Manual 

----------

This is a Reference for EENG 212 Lab Final 

----------
##Basics

###Simple Arithmetic

```
EDU>> 4+4
ans =

     8
```
###Setting Variables 

```
EDU>> x=4

x =
     4

EDU>> y=7

y =
     7

EDU>> x * y

ans =
    28
```

###Creating a Matrix
````
EDU>> x= [5 3 10; 5 7 4; 0 0 0]
x =
     5     3    10
     5     7     4
     0     0     0
````
###Creating an Algebraic Function 

```
EDU>> x = 7
x =

     7
EDU>> y = 2*x + 7
y =

    21
```

###Stop the flow
Use a semicolon,  **;**  to supress output to the screen

```
*Without a semicolon*
EDU>> q = 5
q =

     5

*With a semicolon*
EDU>> q = 5;

```

##Graphs and Tables

###Creating a Table


````
A = [1 4 7; 2 5 8; 3 6 9]

T = array2table(A)
T = 

    A1    A2    A3
    __    __    __

    1     4     7 
    2     5     8 
    3     6     9 

````

###Plotting
blah blah blah blah
Important commands

- figure: tells Matlab to open a window used for plotting graphs
- hold: tell Matlab to "hold" the plot on the given figure
	- ex. "hold on" or "hold off"	



```
EDU>> x = 0.0:100/pi:2*pi;
EDU>> y = sin(x);
figure
plot(x,y)
```
#####Result
![plot one](https://i.imgur.com/VAzPCSQ.jpg)


###More Plotting
**subplot** is a Matlab function that allows for multiple graphs to be plotted next to each other in one *figure* window

```

```

###Polynomial Curve Fitting
Matlab has a function called **polyfit** and **polyval** for finding the best possible curve to meet a given data set

Example use

```
EDU>> x = [-3 -1 0];
EDU>> y = [3.3 4.5 2.0 1.5 2.5 -1.2];
EDU>> n = 4;
EDU>> p1 = polyfit(x,y,n);
EDU>> x_vals = (-3.5:.1:7.2);
EDU>> p1curve = polyval(p1,x_vals);
% the rest is for plotting the generate curve
hold on
plot(x,y,'o',x_vals,p1curve,'red')
```
Here are data sets are the variables **x** and **y**. Such figures would either be obtained in the field, or provided on a test.<br />

The variable **n** is for **polyfit's** *degree* parameter, where a larger number provides for a curve that better fits the data points. Do know that the degree parameter has to have <= (less than or equal) number of data points.<br />

**p1** is a row vector of length n+1 containing the polynomial coefficients in descending order

- ![polyfit](https://i.imgur.com/2PtT1rH.png)

**x_vals** is a vector for the x-axis of the graph

**polyval** is a Matlab function that returns the value of a polynomial of degree *n* evaluated at *x_vals*

<br />
#####Result
notice the "o's" are data points from the given values
![plot2](https://i.imgur.com/C5GfAzy.jpg)

