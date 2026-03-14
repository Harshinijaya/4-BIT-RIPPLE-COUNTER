# 4-BIT-RIPPLE-COUNTER

**AIM:**

To implement  4 Bit Ripple Counter using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 Bit Ripple Counter**

A binary ripple counter consists of a series connection of complementing flip-flops (T or JK type), with the output of each flip-flop connected to the Clock Pulse input of the next higher-order flip-flop. The flip-flop holding the least significant bit receives the incoming count pulses. The diagram of a 4-bit binary ripple counter is shown in Fig. below.

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/cb4b74d4-31ab-4359-95d0-d22e67daba13)

In timing diagram Q0 is changing as soon as the negative edge of clock pulse is encountered, Q1 is changing when negative edge of Q0 is encountered(because Q0 is like clock pulse for second flip flop) and so on.

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/a573a7d6-014e-4e54-93e6-e2ac9530960b)

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/85e1958a-2fc1-49bb-9a9f-d58ccbf3663c)

**Procedure**

Create a new project in Quartus and write the Verilog code for the counter, then save the file.

Compile the design using Start Compilation to check for errors.

Create a simulation waveform file: File → New → University Program VWF and add signals (clk, rstn, q[3..0]).

Set input waveforms: use Overwrite Clock for clk and set rstn = 0 initially, then 1 after some time.

Run simulation (Simulation → Run Functional Simulation) and observe the counter output q[3..0] counting sequentially.

**PROGRAM**

 Program for 4 Bit Ripple Counter and verify its truth table in quartus using Verilog programming.
````
Developed by:Harshini J
RegisterNumber:212225040120

module ripple(clk,rstn,q);
input clk,rstn;
output reg [3:0] q;

always @(posedge clk or negedge rstn)
if(!rstn) q[0]<=0; else q[0]<=~q[0];

always @(posedge q[0] or negedge rstn)
if(!rstn) q[1]<=0; else q[1]<=~q[1];

always @(posedge q[1] or negedge rstn)
if(!rstn) q[2]<=0; else q[2]<=~q[2];

always @(posedge q[2] or negedge rstn)
if(!rstn) q[3]<=0; else q[3]<=~q[3];

endmodule

````

**RTL LOGIC FOR 4 Bit Ripple Counter**

<img width="1341" height="559" alt="image" src="https://github.com/user-attachments/assets/9134251f-95df-4fca-be41-7cb1487be6e6" />



**TIMING DIGRAMS FOR 4 Bit Ripple Counter**

<img width="1919" height="685" alt="image" src="https://github.com/user-attachments/assets/521450db-1da1-4d99-a63e-4d4856600311" />


**RESULTS**

Thus the 4 Bit Ripple Counter has been implemented using Verilog successfully and validated their functionality using their truth table.
