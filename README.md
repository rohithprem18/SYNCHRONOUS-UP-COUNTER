### SYNCHRONOUS-UP-COUNTER

**AIM:**

To implement 4 bit synchronous up counter and validate functionality.

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 bit synchronous UP Counter**

If we enable each J-K flip-flop to toggle based on whether or not all preceding flip-flop outputs (Q) are “high,” we can obtain the same counting sequence as the asynchronous circuit without the ripple effect, since each flip-flop in this circuit will be clocked at exactly the same time:

![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/d5db3fa0-e413-404c-b80e-b2f39d82e7e8)


![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/52cb61eb-d04b-442d-810c-31185a68410b)

Each flip-flop in this circuit will be clocked at exactly the same time.
The result is a four-bit synchronous “up” counter. Each of the higher-order flip-flops are made ready to toggle (both J and K inputs “high”) if the Q outputs of all previous flip-flops are “high.”
Otherwise, the J and K inputs for that flip-flop will both be “low,” placing it into the “latch” mode where it will maintain its present output state at the next clock pulse.
Since the first (LSB) flip-flop needs to toggle at every clock pulse, its J and K inputs are connected to Vcc or Vdd, where they will be “high” all the time.
The next flip-flop need only “recognize” that the first flip-flop’s Q output is high to be made ready to toggle, so no AND gate is needed.
However, the remaining flip-flops should be made ready to toggle only when all lower-order output bits are “high,” thus the need for AND gates.

**Procedure**

1.Initialize the shift register to a known state (e.g., all zeros).

2.Input a bit serially into the shift register.

3.Shift the contents of the register one position to the right (or left).

4.Output the shifted bit from the last stage of the register.

5.Repeat steps 2-4 for each bit you want to input and shift.

**PROGRAM**
Developed by: ROHITH PREM S
RegisterNumber: 212223040172
```
module ex11(out,clk,rstn);
input clk,rstn;
output reg [3:0]out;
always @ (posedge clk)
begin
   if(!rstn)
     out<=0;
   else 
     out <= out+1;
end
endmodule
```

**RTL LOGIC UP COUNTER**

![325181572-28c89b13-3373-4039-b8da-6d3607545722](https://github.com/ganeshprabhu2005/SYNCHRONOUS-UP-COUNTER/assets/146162190/dc0f4267-c68c-4212-83e1-5d7de58d08a7)

**TIMING DIAGRAM FOR IP COUNTER**

![325181834-f7a7ea77-2aec-4a46-afdd-da9fea36c9a1](https://github.com/ganeshprabhu2005/SYNCHRONOUS-UP-COUNTER/assets/146162190/544a2e45-6fd4-4eb0-ad37-c7c80b2c80e2)

**TRUTH TABLE**

![325181877-67592a44-d24c-43fc-8e6c-40874657923c](https://github.com/ganeshprabhu2005/SYNCHRONOUS-UP-COUNTER/assets/146162190/1d74a34c-ee02-4e09-85fb-56b70b69cbb9)

**RESULTS**

Hence a 4 bit synchronous up counter is implemented correctly.


