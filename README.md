# Experiment-08- Encoders-and-decoders 
## AIM: 
To implement 8 to 3 Encoder and  3to8 Decoder using verilog and validate its outputs
## HARDWARE REQUIRED:  
PC, Cyclone II , USB flasher
## SOFTWARE REQUIRED: 
Quartus prime
## THEORY: 

## Encoders:
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

 ## Decoders: 
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
Step1:- Open the quartus II software.

Step2:- Create a new project.

Step3:- Name the projects such that the same name is used for mentioning the name of the module.

Step4:- Develop programmes for both Encoder and Decoder using verilog programming.

Step5:- Run RTL Simulation.

Step6:- Create the Timing diagram.

Step7:- Validate the outputs.

### PROGRAM 
```
Program for Endocers and Decoders  and verify its truth table in quartus using Verilog programming.
Developed by: BHUVANESHWAR V
RegisterNumber:  212221240009
i)ENCODER:
module exp8(a,b,c,d0,d1,d2,d3,d4,d5,d6,d7);
output a,b,c;
input d0,d1,d2,d3,d4,d5,d6,d7;
or(a,d4,d5,d6,d7);
or(b,d2,d3,d6,d7);
or(c,d1,d3,d5,d7);
endmodule

ii)DECODER:
module dec(d0,d1,d2,d3,d4,d5,d6,d7,a,b,c);
output d0,d1,d2,d3,d4,d5,d6,d7;
input a,b,c;
assign d0=(~a & ~b & ~c) ;
assign d1=(~a & ~b &c);
assign d2=(~a & b &~c);
assign d3=(~a & b &c);
assign d4=(a &~b&~c);
assign d5=(a &~b&c);
assign d6=(a&b&~c);
assign d7=(a&b&c);
endmodule

```
## RTL LOGIC:
### ENCODER:
![image](https://user-images.githubusercontent.com/94233985/201405338-ca0f1cdb-947a-44f4-bd54-990febecaa5f.png)

### DECODER:
![image](https://user-images.githubusercontent.com/94233985/201405408-d04f5bac-bbf4-4231-a889-f63f57a370ec.png)


## TIMING DIGRAMS: 

### ENCODER:
![image](https://user-images.githubusercontent.com/94233985/201405481-43d7ae18-23d6-440b-a213-3d1e3ee5f18e.png)
![image](https://user-images.githubusercontent.com/94233985/201405615-a053b5f1-16f2-426a-8aad-ceff2fe4c25b.png)

![image](https://user-images.githubusercontent.com/94233985/201405701-a08b8120-18b0-4ea0-b88a-d103d248e3f3.png)

### DECODER:

![image](https://user-images.githubusercontent.com/94233985/201405793-4b5d9c77-c988-4eb2-bcef-0b4d38495763.png)

## TRUTH TABLE:


### ENCODER:
![image](https://user-images.githubusercontent.com/94233985/201405872-697ae8cc-d157-485e-92ed-3dae68f61bad.png)

### DECODER:

![image](https://user-images.githubusercontent.com/94233985/201405930-f654e9ad-4e14-445b-9446-a652b5a5a4ab.png)



## RESULT:
Thus 8 to 3 Encoder and 3to8 Decoder are implemented successfully using verilog and validate its outputs.
