                                                                  

EXP.NO- 1                                                                                                            

DATE- 
                    SIMULATION AND IMPLEMENTATION OF LOGIC GATES AND 
                                           4 BIT ADDER & SUBTRACTOR 

AIM: To simulate and synthesis Logic Gates, Adders and Subtractor using VIVADO 

APPARATUS REQUIRED:  Software VIVADO 2023.2 

PROCEDURE: 


STEP:1 Open the Vivado, Select and Name the New project. 


STEP:2 Select the device family, device, package and speed. 


STEP:3 Select new source in the New Project and select Verilog Module as the Source type. 


STEP:4 Type the File Name and Click Next and then finish button. Type the code and save it. 


STEP:5 Select the Behavioural Simulation in the Source Window and click the check syntax. 

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.
 


LOGIC-GATES: 
![image](https://github.com/Varshakamaraj/vlsi-expt-1/assets/165577098/794730f5-6231-4cc0-8961-1cf159a66648)

                            

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

![image](https://github.com/Varshakamaraj/vlsi-expt-1/assets/165577098/ecbc163a-4d4d-48e3-8601-c3ddcb2f19f5)

 


HALF ADDER: 
![image](https://github.com/Varshakamaraj/vlsi-expt-1/assets/165577098/45f0d3ac-3395-448f-80e2-03944e868266)



 

PROGRAM: 

module ha(a,b,s,c);
input a,b;
output s,c;
assign s=a^b;
assign c=a&b;
endmodule




OUTPUT:
![image](https://github.com/Varshakamaraj/vlsi-expt-1/assets/165577098/3194bb5e-a2da-4d95-a0fd-0e05c92b16cc)

 


HALFSUBTRACTOR: 


 ![image](https://github.com/Varshakamaraj/vlsi-expt-1/assets/165577098/e058dd1e-90b0-4d2a-b433-2def135c1a93)




PROGRAM: 

module half_sub(a,b,D,B);
input a,b; 
output D,B;
assign D=a^b; 
assign B=~a&b;
endmodule


OUTPUT:
 ![image](https://github.com/Varshakamaraj/vlsi-expt-1/assets/165577098/d90ff922-a4a6-4f67-8515-9534cefe4836)





FULLADDER: 
![image](https://github.com/Varshakamaraj/vlsi-expt-1/assets/165577098/c4706c35-f6a8-4b67-b923-a2e2ab651ea7)

 


PROGRAM: 

module fa(a,b,c,sum,carry);
input a,b,c; 
output sum,carry;
assign sum=a^b^c; 
assign carry=(a&b)|(a&c)|(b&c);
endmodule



OUTPUT:
 
 ![image](https://github.com/Varshakamaraj/vlsi-expt-1/assets/165577098/d772b24b-df54-418d-9573-d7858e14fbf7)









FULL SUBTRACTOR: 

![image](https://github.com/Varshakamaraj/vlsi-expt-1/assets/165577098/8fc7bb9c-c422-4533-9067-608660af10ba)

 

PROGRAM: 

module fs(a,b,c,diff,borrow);
input a,b,c;
output diff,borrow;
assign diff=a^b^c; 
assign borrow=(~a&c)|(~a&b)|(b&c); 
endmodule


OUTPUT:
 
 
![image](https://github.com/Varshakamaraj/vlsi-expt-1/assets/165577098/f61a348c-f122-46f8-b949-1ada3cf3ac36)


8-BIT-RIPPLE-CARRY-ADDER: 
![image](https://github.com/Varshakamaraj/vlsi-expt-1/assets/165577098/dbc780fe-5389-4873-9345-b4bfbb2bfebf)


 

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
 ![image](https://github.com/Varshakamaraj/vlsi-expt-1/assets/165577098/fa40aec2-c28b-483e-83cc-f657b734e428)
 
RESULT:
        Thus, the logic gates and 4 Bit of Adder and Subtractor are Implemented 
and simulated successfully.




RESULT:
        Thus, the logic gates and 4 Bit of Adder and Subtractor are Implemented 
and simulated successfully.

# vlsi-expt-1
