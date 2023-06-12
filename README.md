# Experiment-08- Encoders-and-decoders 
### AIM: To implement 8 to 3 Encoder and  3to8 Decoder using verilog and validate its outputs
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## Encoders
Binary code of N digits can be used to store 2N distinct elements of coded information. This is what encoders and decoders are used for. Encoders convert 2N lines of input into a code of N bits and Decoders decode the N bits into 2N lines.

1. Encoders –
An encoder is a combinational circuit that converts binary information in the form of a 2N input lines into N output lines, which represent N bit code for the input. For simple encoders, it is assumed that only one input line is active at a time.

As an example, let’s consider Octal to Binary encoder. As shown in the following figure, an octal-to-binary encoder takes 8 input lines and generates 3 output lines.

![image](https://user-images.githubusercontent.com/36288975/171543588-bc0746df-a173-4b35-989e-5fb7d385fe8a.png)
## Figure -01 3 to 8 Encoder 


Implementation –

X = D4 + D5 + D6 + D7
Y = D2 +D3 + D6 + D7
Z = D1 + D3 + D5 + D7 
Hence, the encoder can be realised with OR gates as follows:


![image](https://user-images.githubusercontent.com/36288975/171543740-68403b82-aa93-4c98-9343-f32b14885a2e.png)
## Figure -02 3 to 8 Encoder implenentation 

 ### Decoders 
A decoder does the opposite job of an encoder. It is a combinational circuit that converts n lines of input into 2n lines of output.

Let’s take an example of 3-to-8 line decoder.
Implementation –
D0 is high when X = 0, Y = 0 and Z = 0. Hence,

D0 = X’ Y’ Z’ 
Similarly,

D1 = X’ Y’ Z
D2 = X’ Y Z’
D3 = X’ Y Z
D4 = X Y’ Z’
D5 = X Y’ Z
D6 = X Y Z’
D7 = X Y Z 


![image](https://user-images.githubusercontent.com/36288975/171543978-ee2d0671-2846-40a1-8705-507fd6287a49.png)
## Figure -03 8 to 3 Decoder 



![image](https://user-images.githubusercontent.com/36288975/171543866-5a6eace6-8683-49d7-9c4f-a7cb30ec3035.png)
## Figure -04 8 to 3 Decoder implementation 

### Procedure
/* 
### Step 1:
Open Quartus II and select new project and choose the file location.

### Step 2:
Module Declaration. Module should have the file name.

### Step 3:
Input-Output Delecaration.

### Step 4:
Use assign to define the functionality of logic circuits.

### Step 5:
At the end give endmodule.

### Step 6:
Run the program and choose RTL viewer to get RTL realization.
*/



### PROGRAM 
/*
Program for Endocers and Decoders  and verify its truth table in quartus using Verilog programming.
Developed by: LOGESHWARI.P
RegisterNumber:212221230055  
*/
## ENCODER:
```
module Encoder(a,b,c,d0,d1,d2,d3,d4,d5,d6,d7);
input d0,d1,d2,d3,d4,d5,d6,d7;
output a,b,c;
or(a,d4,d5,d6,d7);
or(b,d2,d3,d6,d7);
or(c,d1,d3,d5,d7);
endmodule
```
## DECODER:
```
module Decoder(d0,d1,d2,d3,d4,d5,d6,d7,a,b,c);
input a,b,c;
output d0,d1,d2,d3,d4,d5,d6,d7;
assign d0 = (~a&~b&~c);
assign d1 = (~a&~b&c);
assign d2 = (~a&b&~c);
assign d3 = (~a&b&c);
assign d4 = (a&~b&~c);
assign d5 = (a&~b&c);
assign d6 = (a&b&~c);
assign d7 = (a&b&c);
endmodule
```

## output:
### RTL LOGIC  
### ENCODER:
![243398300-ae0ffa17-69fd-4441-b802-fe1458096a30](https://github.com/logeshwari2004/Experiment-08-Encoders-and-decoders-/assets/94211349/3d0389b1-9396-4aa8-a058-b077c8340217)
### DECODER:
![243398378-612b9e87-c1d8-4e1e-8e4f-72e73b0591b8](https://github.com/logeshwari2004/Experiment-08-Encoders-and-decoders-/assets/94211349/f863d023-7740-4ff3-bbc1-a0750f7c4988)
### TIMING DIGRAMS  
### ENCODER:
![243398461-481872de-6556-4c61-81f0-853d9d7b01d8](https://github.com/logeshwari2004/Experiment-08-Encoders-and-decoders-/assets/94211349/44137563-b2ff-466f-be25-39d4890922a6)
### DECODER:
![243398523-a250a9b9-409f-4fd4-be21-4841d12a2045](https://github.com/logeshwari2004/Experiment-08-Encoders-and-decoders-/assets/94211349/19b6b0f2-5b0e-422b-9586-eda597ddb1f1)
### TRUTH TABLE 
### ENCODER:
![244088164-51cbaae4-b14b-49ca-a297-4d1686c13853](https://github.com/logeshwari2004/Experiment-08-Encoders-and-decoders-/assets/94211349/f5c791d7-44be-4be6-9fea-71b1e67b5631)
### DECODER:
![243398641-87bc2006-463a-4a5c-8732-0d2c056c6adb](https://github.com/logeshwari2004/Experiment-08-Encoders-and-decoders-/assets/94211349/9e9a2579-60d4-47a3-9766-64f4c78a42fa)
### RESULTS 
Thus, 8 to 3 Encoder and 3 to 8 Decoder is implemented using verilog and its outputs is validated.
