# Name:Aneesbasha J
# Register Number: 23003943
# Experiment 03:Half Subtractor and Full subtractor
## Implementation of Half subtractor and Full subtractor circuit
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
Connect the supply (+5V) to the circuit Switch ON the main switch If the output is 1, then the led glows.

## Program:
(i)
```
module HalfSubstractor (a,b,diff,borrow);
input a,b;
output diff,borrow;
xor (diff,a,b);
and (borrow,~a,b);
endmodule
```
(ii)
```
module FullSubstractor(a,b,c,diff,borrow);
input a,b,c;
output diff,borrow;
xor(diff,a,b,c);
assign borrow=~a&b|c&~(a^b);
endmodule
```
## Truthtable
### (i)
![Screenshot 2023-12-18 132657](https://github.com/Aneesbasha18/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/154219883/4d3d145b-a8af-4ac3-81db-d958597decac)
### (ii)
![Screenshot 2023-12-18 133231](https://github.com/Aneesbasha18/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/154219883/984a5d4d-9934-4520-af31-6fb901e2a768)

##  RTL realization
### (i)
![Screenshot 2023-12-18 111552](https://github.com/Aneesbasha18/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/154219883/16158da1-b3a5-4cda-a183-ef4bbe748239)
### (ii)
![Screenshot 2023-12-18 130942](https://github.com/Aneesbasha18/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/154219883/103b163a-7c8c-469e-b2d7-bf34e4b9260a)

## Timing Diagram
### (i)
![Screenshot 2023-12-18 112054](https://github.com/Aneesbasha18/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/154219883/155736ea-fba9-4521-a105-779d1cbc08f3)
### (ii)
![Screenshot 2023-12-18 131319](https://github.com/Aneesbasha18/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/154219883/1b94d1d1-663e-45aa-9a61-66659da88fc9)

## Result
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
