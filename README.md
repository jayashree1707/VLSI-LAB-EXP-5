## SIMULATION AND IMPLEMENTATION OF FINITE STATE MACHINE

## AIM:
To simulate and synthesis finite state machine using vivado.

## APPARATUS REQUIRED: 
vivado 2023.2

## PROCEDURE: 
STEP:1 Start the vivado 2023.2 software, Select and Name the New project.
STEP:2 Select the device family, device, package and speed. 
STEP:3 Select new source in the New Project and select Verilog Module as the Source type. 
STEP:4 Type the File Name and Click Next and then finish button. Type the code and save it. 
STEP:5 Select the Behavioral Simulation in the Source Window and click the check syntax. 
STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table. 

## Logic Diagram :

![image](https://github.com/navaneethans/VLSI-LAB-EXP-5/assets/6987778/34ec5d63-2b3b-4511-81ef-99f4572d5869)


## VERILOG CODE:
```
module fsm(clk,rst,x,y);
input clk,rst,x;
output y;
reg [2:1]present,next;
parameter s0=2'b00,s1=2'b01,s2=2'b10,s3=2'b11;
always@(x,present)
case (present)
s0:if (x)
next=s1;
else
next=s0;
s1:if(x)
next=s1;
else
next=s2;
s2:if(x)
next=s3;
else
next=s0;
s3:if (x)
next=s1;
else
next=s2;
endcase
always@(negedge rst,posedge clk)
if (rst)
present=s0;
else
present=next;
assign y=(present==s3);
endmodule
```
## OUTPUT:

![WhatsApp Image 2024-04-13 at 13 18 57_32a9c898](https://github.com/jayashree1707/VLSI-LAB-EXP-5/assets/160314881/6b7910fb-042d-47a5-bd74-3d255d1a724c)


## RESULT:
thus the simulation and implemention of finite state Moore machine is done and the outputs are verified successfully.



