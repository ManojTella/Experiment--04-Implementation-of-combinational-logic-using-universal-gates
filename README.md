# Experiment--04-Implementation-of-combinational-logic-using-universal-gates
Implementation of combinational logic using universal-gates
 
## AIM:
To implement the given logic function using NAND and NOR gates and to verify its operation in Quartus using Verilog programming.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')' using NAND gate
F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')' using NOR gate
## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime


## Theory
Logic gates are electronic circuits which perform logical functions on one or more inputs to produce one output. 

## Using NAND gates
NAND gate is actually a combination of two logic gates i.e. AND gate followed by NOT gate. So its output is complement of the output of an AND gate.This gate can have minimum two inputs, output is always one. By using only NAND gates, we can realize all logic functions: AND, OR, NOT, X-OR, X-NOR, NOR. So this gate is also called as universal gate. First note that the entire expression is inverted and we have three terms ANDed. This means that we must use a 3-input NAND gate. Each of the three terms is, itself, a NAND expression. Finally, negated single terms can be generates with a 2-input NAND gate acting as an inverted.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')'

## Logic Diagram

Using NOR gates
NOR gate is actually a combination of two logic gates: OR gate followed by NOT gate. So its output is complement of the output of an OR gate. This gate can have minimum two inputs, output is always one. By using only NOR gates, we can realize all logic functions: AND, OR, NOT, Ex-OR, Ex-NOR, NAND. So this gate is also called universal gate. Designing a circuit with NOR gates only uses the same basic techniques as designing a circuit with NAND gates; that is, the application of deMorgan’s theorem. The only difference between NOR gate design and NAND gate design is that the former must eliminate product terms and the later must eliminate sum terms.

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')'

## Logic Diagram
## Procedure
## Program:
Program to implement the given logic function using NAND and NOR gates and to verify its operations in quartus using Verilog programming.

Developed by: Manoj Guna Sundar Tella.

RegisterNumber:  212221240026.
```
USING NAND
module comblogic(a,b,c,d,f);
input a,b,c,d;
output F;
wire f1,f2,f3;
assign f1 = (~c&~b&~a);
assign f2 = (~d&~c&~a);
assign f3 = (c&~(~b)&~a);
assign F= f1&~f2&~f3;
endmodule

USING NOR
module comblogic(a,b,c,d,f);
input a,b,c,d;
output F;
wire f1,f2,f3,f4;
assign f1 = c&(~b)&a;
assign f2 = d&(~c)&a;
assign f3 = c&(~b)&a;
assign f4 = ~(f1|f2|f3);
not(F,f4);
endmodule
```
## RTL realization
## Output:
### Program1:
### RTL
![comb1rtl](https://user-images.githubusercontent.com/94883876/192535032-6090395f-a761-419b-8f47-db35c144fa5c.jpg)

### Timing Diagram
![comb1time](https://user-images.githubusercontent.com/94883876/192535193-39b71bae-4cdd-4d09-ac07-97dc3e49ebd0.jpg)

### Truth Table
![comb1tru](https://user-images.githubusercontent.com/94883876/192535307-2220e4ce-ad1f-435a-bf7a-b49812c5d96a.jpg)

### Program2:
### RTL
![comb2rtl](https://user-images.githubusercontent.com/94883876/192535367-31b82494-58f7-47df-aa80-0e72ebac4292.jpg)

### Timing Diagram
![comb2time](https://user-images.githubusercontent.com/94883876/192535468-14cf07df-60f1-4b71-95d3-49535ba9f8f4.jpeg)

### Truth Table
![comb2tru](https://user-images.githubusercontent.com/94883876/192535507-5e25c1ef-6654-4cb3-af31-6e25f0c794ce.jpg)

## Result:
Thus the given logic functions are implemented using NAND and NOR gates and their operations are verified using Verilog programming.
