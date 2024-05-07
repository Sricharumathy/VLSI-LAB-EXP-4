# SIMULATION AND IMPLEMENTATION OF SEQUENTIAL LOGIC  CIRCUITS                         

## AIM:
To simulate and synthesis SR, JK, T, D - FLIPFLOP, COUNTER DESIGN  using VIVADO

## APPARATUS REQUIRED: 
VIVADO 2023.2

## PROCEDURE:
 STEP:1 Start the Vivado, Select and Name the New project.
 
 STEP:2 Select the device family, device, package and speed. 
 
 STEP:3 Select new source in the New Project and select Verilog Module as the Source type.
 
 STEP:4 Type the File Name and Click Next and then finish button. Type the code and save it.
 
 STEP:5 Select the Behavioural Simulation in the Source Window and click the check syntax.
 
 STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

## SR FLIPFLOP
![image](https://github.com/Sricharumathy/VLSI-LAB-EXP-4/assets/159044760/7bd5073b-5a6b-4bb7-b378-cf9556e0c444)

## PROGRAM
```
end module SRFF(s, r, clk, rst, q);
input s, r, clk, rst;
output reg q;
always@(posedge clk)
begin
if(rst==1)
q=1'b0;
else
begin
case({s, r})
2'b00:q=q;
2'b01:q=1'b0;
2'b10:q=1'b1;
2'b11:q=1'bx;
end
end
endmodule
```

## OUTPUT
![image](https://github.com/Sricharumathy/VLSI-LAB-EXP-4/assets/159044760/7aca7c2a-2c25-4dac-a74e-8ab6bca739f7)

## JK FLIPFLOP
![image](https://github.com/Sricharumathy/VLSI-LAB-EXP-4/assets/159044760/e6fe8fec-8874-452d-b595-5bafa1f168c9)

## PROGRAM
```
module JKFF(j, k, clk, rst, q);
input j, k, clk, rst;
output reg q;
always@(posedge clk)
begin
if(rst==1)
q=1'b0;
else
begin
case({j, k})
2'b00:q=q;
2'b01:q=1'b0;
2'b10:q=1'b1;
2'b11:q=~q;
endcase
end
end
endmodule
```

## OUTPUT
![image](https://github.com/Sricharumathy/VLSI-LAB-EXP-4/assets/159044760/21828a96-fd5f-4d41-9932-749ccc20e721)

## T FLIPFLOP
![image](https://github.com/Sricharumathy/VLSI-LAB-EXP-4/assets/159044760/24fcd822-a09d-42da-8345-387b44f101b1)

## PROGRAM
```
module TFF(clk, rst, t, q);
input t, clk, rst;
output reg q;
always@(posedge clk)
begin
if(rst==1)
q=1'b0;
else
begin
if(t==0)
q=q;
else
q=~q;
end
end
endmodule
```

## OUTPUT
![image](https://github.com/Sricharumathy/VLSI-LAB-EXP-4/assets/159044760/7b582d41-0d22-4c32-98b4-1a472b138344)

## D FLIPFLOP
![image](https://github.com/Sricharumathy/VLSI-LAB-EXP-4/assets/159044760/cf5a8f6e-ac77-4c8c-a43e-bbea90eb1fca)

## PROGRAM
```
module DFF(d, q, clk, rst);
input d, clk, rst;
output reg q;
always@(posedge clk)
begin
if(rst==1)
q=1'b0;
else
q=d;
end
endmodule
```

## OUTPUT
![image](https://github.com/Sricharumathy/VLSI-LAB-EXP-4/assets/159044760/a33541ff-05fd-499d-a138-ae4c181c82ab)

## COUNTER
![image](https://github.com/Sricharumathy/VLSI-LAB-EXP-4/assets/159044760/e16c5840-5b14-4b8c-a563-79244ccb2d0c)

## UPDOWN PROGRAM
```
module Counter(clk,rst,updown,out);
input updown,clk,rst;
output reg [3:0]out;
always@(posedge clk)
begin
if(rst==1)
out=8'b0;
else
begin
if(updown==1)
out=out+1'b1;
else
out=out-1'b1;
end
end
endmodule
```

## OUTPUT
![Screenshot 2024-04-02 141207](https://github.com/Sricharumathy/VLSI-LAB-EXP-4/assets/159044760/73d4e2c3-da7f-4faa-9c2a-838252412a99)

## MOD10 COUNTER PROGRAM
```
module mod10_c(clk,rst,out);
input clk,rst;
output reg [3:0]out;
always@(posedge clk)
begin
if(rst==1 | out==9)
out=8'b0;
else
out=out+1;
end
endmodule
```

## OUTPUT
![Screenshot 2024-04-01 213130](https://github.com/Sricharumathy/VLSI-LAB-EXP-4/assets/159044760/f277ab5b-8178-434c-ac8d-adcf32a24f00)

## RESULT
Thus, The FlipFlops and Counter are simulated and verified Successfully.













 
