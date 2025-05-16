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

1.Type the program in Quartus software.

2.Compile and run the program.

3.Generate the RTL schematic and save the logic diagram.

4.Create nodes for inputs and outputs to generate the timing diagram.

5.For different input combinations generate the timing diagram

**PROGRAM**

/* Program for 4 Bit Ripple Counter and verify its truth table in quartus using Verilog programming.

 Developed by:ANBUDURAI A 
 
 RegisterNumber:212224230018

 module ripple_counter (
```
input clk,        // Input clock

input reset,      // Reset signal (active high)

output [3:0] q    // 4-bit counter output
```
);

reg [3:0] count; // Register to hold counter values

assign q = count; // Assign the register to the output

// Asynchronous ripple counter logic

always @(posedge clk or posedge reset) begin
```if (reset) 

    count <= 4'b0000; // Reset the counter to 0

else begin

    count[0] <= ~count[0];                  // Toggle LSB
    
    count[1] <= count[0] ^ count[1];       // XOR for the second bit
    
    count[2] <= count[1] & ~count[2];      // MSB toggling with cascading stages
```
**RTL LOGIC FOR 4 Bit Ripple Counter**
![image](https://github.com/user-attachments/assets/bcf1e578-d217-479e-94cc-d71bbb3ef4e3)

**TIMING DIGRAMS FOR 4 Bit Ripple Counter**
![image](https://github.com/user-attachments/assets/97e8c3ed-f3cb-4dba-98a0-569245f87c80)

**RESULTS**


Thus the 4 Bit Ripple Counter using verilog is implemented and their functionality using their functional tables is validated.
