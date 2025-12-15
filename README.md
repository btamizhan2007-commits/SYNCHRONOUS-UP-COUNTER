# SYNCHRONOUS-UP-COUNTER

AIM:

To implement 4 bit synchronous up counter and validate functionality.

SOFTWARE REQUIRED:
          Quartus prime

THEORY

4 bit synchronous UP Counter

If we enable each J-K flip-flop to toggle based on whether or not all preceding flip-flop outputs (Q) are “high,” we can obtain the same counting sequence as the asynchronous circuit without the ripple effect, since each flip-flop in this circuit will be clocked at exactly the same time:

<img width="607" height="321" alt="1" src="https://github.com/user-attachments/assets/0da732cc-1314-4624-a4b5-f4359f23bf55" />

<img width="744" height="409" alt="2" src="https://github.com/user-attachments/assets/42b38efb-8cf3-4b09-8756-7e518e2cbf5f" />

Each flip-flop in this circuit will be clocked at exactly the same time. The result is a four-bit synchronous “up” counter. Each of the higher-order flip-flops are made ready to toggle (both J and K inputs “high”) if the Q outputs of all previous flip-flops are “high.” Otherwise, the J and K inputs for that flip-flop will both be “low,” placing it into the “latch” mode where it will maintain its present output state at the next clock pulse. Since the first (LSB) flip-flop needs to toggle at every clock pulse, its J and K inputs are connected to Vcc or Vdd, where they will be “high” all the time. The next flip-flop need only “recognize” that the first flip-flop’s Q output is high to be made ready to toggle, so no AND gate is needed. However, the remaining flip-flops should be made ready to toggle only when all lower-order output bits are “high,” thus the need for AND gates.

PROGRAM:

```
module synchronous_up_counter (
    input wire clk,     
    input wire reset,   
    output reg [3:0] count 
);

always @(posedge clk) begin
    if (reset) begin
        count <= 4'b0000;
    end else begin
        count <= count + 1; 
    end
end

endmodule

```
TRUTH TABLE:

 <img width="1088" height="373" alt="TRUTH TABLE" src="https://github.com/user-attachments/assets/6e47d91f-309d-455e-a276-0fdcc2bb72d4" />

RTL LOGIC UP COUNTER:

[EX 11 Dia.pdf](https://github.com/user-attachments/files/24148596/EX.11.Dia.pdf)

WAVEFORM: 

[synchronous up counters.pdf](https://github.com/user-attachments/files/24171265/synchronous.up.counters.pdf)

NAME: TAMIZHAN.B

REF NO: 25018064

 RESULT:
       Hence a 4 bit synchronous up counter is implemented correctly.

