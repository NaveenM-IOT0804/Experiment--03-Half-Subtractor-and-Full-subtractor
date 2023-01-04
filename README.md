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
The half subtractor is also a building block for subtracting two binary numbers. It has two inputs and two outputs. This circuit is used to subtract two single bit binary numbers A and B. The 'diff' and 'borrow' are two output states of the half subtractor.
A full subtractor is formed by two half subtractors, which involves three inputs such as minuend, subtrahend and borrow, borrow bit among the inputs is obtained from subtraction of two binary digits and is subtracted from next higher order pair of bits, outputs as difference and borrow.


## Program:

Half subtractor:

module halfsub(output b,d,input x,y);

assign d=(x^y);

assign b=(~x&y);

endmodule

Full subtractor:

module fullsub(x,y,z,b,d);

input x,y,z;

output b,d;

assign d=(x^y^z);

assign b=(~x&(y^z)|(y&z));

endmodule

Developed by: NAVEEN M

RegisterNumber: 22000748

## Output:

## Truthtable
Half subtractor :

![half-subtractor](https://user-images.githubusercontent.com/117974950/210540183-58683d2e-0b42-4506-99b2-5f6c5bed954b.png)

Full subtractor:

![full-subtractor-truth-table](https://user-images.githubusercontent.com/117974950/210540262-6a8ccd68-9757-4c76-a15c-281f97c80dbb.jpg)



##  RTL realization
Half subtractor:

![halfsub](https://user-images.githubusercontent.com/117974950/210539551-ecf47753-43e3-4a66-82f6-ca53521b5d48.png)

Full subtractor:

![fullsub](https://user-images.githubusercontent.com/117974950/210539690-533a14e8-ee8c-41ec-81fd-31f40330ffb7.png)


## Timing diagram 

## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
