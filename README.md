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
/* write all the steps invloved */



### PROGRAM 
1.create module encoder and decoder.

2.Get inputs and outputs for encoders and decoders.

3.perform or operation for encoder and and logic for decoders.

4.perform RTL LOGIC and get waveform.
/*
Program for Endocers and Decoders  and verify its truth table in quartus using Verilog programming.
Developed by: Rakesh.V
RegisterNumber: 22008590 
## ENCODER
```
module enc(d0,d1,d2,d3,d4,d5,d6,d7,a,b,c);
input d0,d1,d2,d3,d4,d5,d6,d7;
output a,b,c;
or(a,d4,d5,d6,d7);
or(b,d2,d3,d6,d7);
or(c,d1,d3,d5,d7);
endmodule
```
## DECODER
```
module enc(a,b,c,d0,d1,d2,d3,d4,d5,d6,d7);
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



### RTL LOGIC  
 ## ENCODER
 ![214761606-1b296af7-b939-4beb-a1ed-40c71d871d50](https://user-images.githubusercontent.com/121490890/215005602-39e4f0ff-24bd-4a80-acb1-99c898004cf7.png)

 
 ## DECODER
![214761628-62e0fb8f-51df-4bf4-b9c3-91f677aa403f](https://user-images.githubusercontent.com/121490890/215005626-62d4845b-ad98-4ec0-873a-54671292b63a.png)







### TIMING DIGRAMS  
## ENCODER
![214372416-3be035c8-1b9d-465f-8b0b-8b6d862297f8](https://user-images.githubusercontent.com/121490890/215006175-fe8e526e-3abe-45fd-9b25-6a5cf13e05e7.png)

## DECODER
![199727272-b025753a-672b-4034-8597-cf0219602d69](https://user-images.githubusercontent.com/121490890/215005808-6a57b854-343c-42f7-8c61-ecec1abad972.png)




### TRUTH TABLE 
## ENCODER
![214771633-587c66e7-3bc3-42f4-be6f-af93d33137b6](https://user-images.githubusercontent.com/121490890/215005668-bc0a6541-a6a2-4fe7-8b8c-56238501b8e6.png)

## DECODER
![214771609-3ac6d95d-5356-4e69-9fc4-528000efe4ca](https://user-images.githubusercontent.com/121490890/215005677-2a17a061-ea10-44cf-aeb2-a5f15c7ccfee.png)





### RESULTS 
to 3 Encoder and 3to8 Decoder has been implemented by using verilog and its outputs are validated.
