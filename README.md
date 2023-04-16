# Experiment--03-Half-Subtractor-and-Full-subtractor
## Implementation-of-Half-subtractor-and-Full-subtractor-circuit
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime
## Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

## Half Subtractor Full Subtractor
## Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)


Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

## Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

## Procedure



Write the detailed procedure here 


## Program:
```
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.
Developed by: PRIYA 
```
```
HALF SUBTRACTOR

module HalfSubtractor(A,B,Diff,Borrow);
input A,B;
output Diff,Borrow;
wire x;
xor (Diff, A,B);
not(x,A);
and(Borrow,x,B);
endmodule
```
```
FULL SUBTRACTOR

module FullSubtractor(A,B,C,Diff,Borrow);
input A,B,C;
output Diff,Borrow;
wire p;
assign Diff = ((A^B)^C);
not(p,A);
assign Borrow = ((p&B)|(p&C)|(B&C));
endmodule
````

## Output:
Half Subractor:

![HALF ](https://user-images.githubusercontent.com/121166075/232323420-97f2d01a-5af9-4b79-8a74-db4278ff72e2.png)

## Truthtable
![TT](https://user-images.githubusercontent.com/121166075/232323430-0e9a7dd3-f102-444c-8fb4-e29966748166.png)

##  RTL realization
![RTL](https://user-images.githubusercontent.com/121166075/232323434-6d9730e5-1477-4590-a8c2-6da9ecb85a09.png)

## Timing diagram 
![TD ](https://user-images.githubusercontent.com/121166075/232323447-8c9f9713-9fdd-458e-9f27-439faf081530.png)

Full Subractor:
Gates:

![FS 1](https://user-images.githubusercontent.com/121166075/232323504-40f57c13-b5cf-4447-9f36-d0f0388dd59b.png)

Truthtable :

![FS 2](https://user-images.githubusercontent.com/121166075/232323506-ddc899ac-1cb8-48a1-8974-fd03333738e5.png)

RTL realization:

![FS 3 ](https://user-images.githubusercontent.com/121166075/232323511-9e7a9c72-6d8c-42dd-9f40-842b13aa24b0.png)

Timing diagram :

![FS 4](https://user-images.githubusercontent.com/121166075/232323515-46449387-ea4d-48d6-bc1e-873a9ec54b60.png)


## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
