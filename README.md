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



**Program:**
```
module fulladder(a, b, c, sum, carry);
    input a;
    input b;
    input c;
    output sum;
    output carry;
	 reg sum,carry;
	 reg t1,t2,t3;
	 always @ (a or b or c) begin
	 sum = (a^b)^c;
	 t1=a & b;
	 t2=b & c;
	 t3=a & c;
	 carry=(t1 | t2) | t3;
	 end
endmodule
```

```
module fulsubbehavioral(a, b, cin, diff, borrow);
    input a;
    input b;
    input cin;
    output diff;
    output borrow;
	 reg t1,t2,t3;
	 reg diff,borrow;
	 reg abar;
	 always @ (a or b or cin) begin
	 abar= ~ a;
	 diff = (a^b)^cin;
	 t1=abar & b;
	 t2=b & cin;
	 t3=cin & abar;
	 borrow=(t1 | t2) | t3;
	 end
	endmodule
```

**RTL Schematic**
![8](https://github.com/user-attachments/assets/6b1ce971-8a3f-4c08-8c3a-520eda9d4b66)
![9](https://github.com/user-attachments/assets/6ef67248-2cff-43b4-84f8-df9ed883fc77)

**Output Timing Waveform**
![10](https://github.com/user-attachments/assets/86383f43-7c92-40f6-b22e-c7e7001033ef)
![11](https://github.com/user-attachments/assets/cdd05c20-5c57-4102-81bb-935889c2cdc7)

**Result:**

Thus the Full Adder and Full Subtractor circuits are designed and the truth tables is verified using Quartus software.



