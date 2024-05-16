EXP.NO- 1

DATE : 06.02.2024

SIMULATION AND IMPLEMENTATION OF LOGIC GATES AND 4 BIT ADDER & SUBTRACTOR

AIM:

To simulate and synthesis Logic Gates, Adders and Subtractor using VIVADO

APPARATUS REQUIRED:

VIVADO 2023.2

PROCEDURE:

STEP:1 Start the Vivado, Select and Name the New project.

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type.

STEP:4 Type the File Name and Click Next and then finish button. Type the code and save it.

STEP:5 Select the Behavioural Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

LOGIC-GATES:

![image](https://github.com/Varshakamaraj/vlsi-expt-1/assets/165577098/3f2ba806-750a-4dbf-8871-16ce29a79b74)

PROGRAM:

module logic_gates(a,b,andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate);

input a,b;

output andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate;

and(andgate,a,b);

or(orgate,a,b);

xor(xorgate,a,b);

nand(nandgate,a,b);

nor(norgate,a,b);

xnor(xnorgate,a,b);

not(notgate,a);

endmodule

OUTPUT:


![image](https://github.com/Varshakamaraj/vlsi-expt-1/assets/165577098/d7ace638-c4b7-4550-95d1-617aa2aeb6c5)


HALF ADDER:


![image](https://github.com/Varshakamaraj/vlsi-expt-1/assets/165577098/efac0057-e37c-4730-aefc-c82458de3c5b)


PROGRAM:

module ha(a,b,sum,carry);

input a,b;

output sum,carry;

assign sum=a^b;

assign carry=a&b;

endmodule

OUTPUT:


![image](https://github.com/Varshakamaraj/vlsi-expt-1/assets/165577098/15a0d75d-39e6-4cdd-8236-605d78bf2d3f)


HALFSUBTRACTOR:


![image](https://github.com/Varshakamaraj/vlsi-expt-1/assets/165577098/6c86229e-a704-427e-b940-50b31dc5d4af)


PROGRAM:

module hs(a,b,diff,borrow);

input a,b;

output diff,borrow;

assign diff=a^b;

assign borrow=~a&b;

endmodule

OUTPUT:


![image](https://github.com/Varshakamaraj/vlsi-expt-1/assets/165577098/0b21ca08-d3b5-4084-bec9-7d76b3251859)


FULLADDER:


![image](https://github.com/Varshakamaraj/vlsi-expt-1/assets/165577098/f4af8cde-fd4d-4161-a97e-d3242eef1a0e)


PROGRAM:

module fa(a,b,c,sum,carry);

input a,b,c;

output sum,carry;

assign sum=a^b^c;

assign carry=(a&b)|(a&c)|(b&c);

endmodule

OUTPUT:


![image](https://github.com/Varshakamaraj/vlsi-expt-1/assets/165577098/a2efe892-4bd6-4f92-906d-964a1ee585a9)


FULLSUBTRACTOR:


![image](https://github.com/Varshakamaraj/vlsi-expt-1/assets/165577098/df09bad2-f668-4022-9667-853f1f2e8301)


PROGRAM:

module fs(a,b,c,diff,borrow);

input a,b,c;

output diff,borrow;

assign diff=a^b^c;

assign borrow=(~a&c)|(~a&b)|(b&c);

endmodule

OUTPUT:


![image](https://github.com/Varshakamaraj/vlsi-expt-1/assets/165577098/eebb3042-c198-4884-a631-5d64be56e9f3)


8-BIT-RIPPLE-CARRY-ADDER:


![image](https://github.com/Varshakamaraj/vlsi-expt-1/assets/165577098/c7bb92dc-7c4b-40bf-ab35-03c0dbbed319)


PROGRAM:

module ripplemod(a, b, cin, sum, cout);

input [07:0] a;

input [07:0] b;

input cin;

output [7:0]sum;

output cout;

wire[6:0] c;

fulladd a1(a[0],b[0],cin,sum[0],c[0]);

fulladd a2(a[1],b[1],c[0],sum[1],c[1]);

fulladd a3(a[2],b[2],c[1],sum[2],c[2]);

fulladd a4(a[3],b[3],c[2],sum[3],c[3]);

fulladd a5(a[4],b[4],c[3],sum[4],c[4]);

fulladd a6(a[5],b[5],c[4],sum[5],c[5]);

fulladd a7(a[6],b[6],c[5],sum[6],c[6]);

fulladd a8(a[7],b[7],c[6],sum[7],cout);

endmodule

module fulladd(a, b, cin, sum, cout);

input a;

input b;

input cin;

output sum;

output cout;

assign sum=(a^b^cin);

assign cout=((a&b)|(b&cin)|(a&cin));

endmodule

OUTPUT:


![image](https://github.com/Varshakamaraj/vlsi-expt-1/assets/165577098/3446c6c9-b533-4beb-9dec-3f0701f68d63)


RESULT:

Thus, the logic gates and 4 Bit of Adder and Subtractor are Implemented and simulated successfully.
