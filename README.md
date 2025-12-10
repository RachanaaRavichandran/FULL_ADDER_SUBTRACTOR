# FULL_ADDER_SUBTRACTOR

Implementation-of-Full-Adder-and-Full-subtractor-circuit

**AIM:**

To design a Full Adder and Full Subtractor circuit and verify its truth table in Quartus using Verilog programming.

**Equipments Required:**

Hardware – PCs, Cyclone II , USB flasher

Software – Quartus prime

**Full Adder and Full Subtractor**

**Full Adder**

Full adder is a digital circuit used to calculate the sum of three binary bits. It consists of three inputs and two outputs. Two of the input variables, denoted by A and B, represent the two significant bits to be added. The third input, Cin, represents the carry from the previous lower significant position. Two outputs are necessary because the arithmetic sum of three binary digits ranges in value from 0 to 3, and binary 2 or 3 needs two digits. The two outputs are sum and carry.

Sum =A’B’Cin + A’BCin’ + ABCin + AB’Cin’ = A ⊕ B ⊕ Cin 

Carry = AB + ACin + BCin

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/0f30ba51-5ffb-4198-845f-18e054f675e7)

**Figure -1 FULL ADDER**

**Full Subtractor**

A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow.

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/02b24f51-ab51-4304-9ad6-7b81ffc1ead5)

Diff = A ⊕ B ⊕ Bin 

Borrow out = A'Bin + A'B + BBin

**Truthtable**

**Procedure**

Write the detailed procedure here

**Program:**

/* Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming. Developed by: RegisterNumber:25004301
*/
full adder 
module exp4add (a,b,c,x,y,z,sum,dif,car,bor);
input a,b,c,x,y,z;
output sum,dif,car,bor;
assign sum = a^b^c;
assign car = a&b | a&c | b&c;
assign dif = x^y^z;
assign bor = ~x&z | ~x&y | y&z;
endmodule

full subractor
module exp4sub(a, b, bin, diff, bout);
input a, b, bin;           // a, b, borrow-in
output diff, bout;         // difference, borrow-out

wire xor1, and1, and2;

assign xor1 = a ^ b;       // First XOR stage
assign diff = xor1 ^ bin;  // Final difference (XOR with borrow-in)

assign and1 = ~a & b;      // Borrow from a-b
assign and2 = ~xor1 & bin; // Borrow from borrow-in
assign bout = and1 | and2; // Final borrow-out (OR)

endmodule

**RTL Schematic**
full adder
<img width="606" height="594" alt="Screenshot 2025-12-10 132600" src="https://github.com/user-attachments/assets/4ec6a550-33fc-4e94-8c6d-793cbcf975e0" />

full subractor
<img width="585" height="223" alt="Screenshot 2025-12-10 134311" src="https://github.com/user-attachments/assets/ff473383-e4a7-47a9-b7ae-78e4421b94a6" />


**Output Timing Waveform**
full adder
<img width="1026" height="524" alt="Screenshot 2025-12-10 132935" src="https://github.com/user-attachments/assets/55b0a882-2017-4c0e-8be1-1f4d63d6ddf6" />

full subractor
<img width="1883" height="932" alt="Screenshot 2025-12-10 134539" src="https://github.com/user-attachments/assets/996fdc9f-ceea-425a-82f0-b085786666cc" />


**Result:**

Thus the Full Adder and Full Subtractor circuits are designed and the truth tables is verified using Quartus software.



