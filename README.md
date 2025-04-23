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


![image](https://github.com/user-attachments/assets/e3510e13-5a92-4410-af27-8dbfd1a887b9)


**Truthtable**



![image](https://github.com/user-attachments/assets/400870df-c886-4a2c-828b-df5293c908a8)


**Procedure**

Write the detailed procedure here

**Program:**

/* Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming. Developed by: RegisterNumber: 212224230219
*/
```
Full Adder

  module half (A, B, Cin, Sum, Carry); 
  input A, B, Cin;
  output Sum, Carry;

  wire AxorB, AB, BCin, ACin;

  xor (AxorB, A, B);           
  xor (Sum, AxorB, Cin);       

  and (AB, A, B);              
  and (BCin, B, Cin);          
  and (ACin, A, Cin);          
  or (Carry, AB, BCin, ACin);  
  endmodule

Full Subtractor

 
 module full (A, B, Bin, Diff, Borrow);
 input A, B, Bin;
 output Diff, Borrow;

 wire AxorB, A_not, A_not_and_B, A_not_and_Bin, B_and_Bin;

 xor (AxorB, A, B);               
 xor (Diff, AxorB, Bin);          

 not (A_not, A);                
 and (A_not_and_B, A_not, B);     
 and (A_not_and_Bin, A_not, Bin); 
 and (B_and_Bin, B, Bin);         
 or (Borrow, A_not_and_B, A_not_and_Bin, B_and_Bin); 
 endmodule
```
**RTL Schematic**
![image](https://github.com/user-attachments/assets/42f01775-ac3a-400e-ba46-5b9cc1cb88f8)
![image](https://github.com/user-attachments/assets/47b2ccf6-5ce2-4b1b-8453-ef47e875401f)


**Output Timing Waveform**
![image](https://github.com/user-attachments/assets/ce0fe76e-f399-482f-8507-158bfa5847e1)
![image](https://github.com/user-attachments/assets/d9e9abae-410f-4378-99c4-a1e68ba65a6a)



**Result:**

Thus the Full Adder and Full Subtractor circuits are designed and the truth tables is verified using Quartus software.



