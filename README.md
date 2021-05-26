# RISC-V-based-CPU-core
Started with a basic calculator using TL-Verilog to implementing RISC V based CPU core using hardware description language TL-Verilog in Makerchip IDE. 

TL Verilog is commmonly used hardware description language, which is more easier and bug free then standard system verilog language.

![image](https://user-images.githubusercontent.com/70278767/119694143-988b2a00-be6a-11eb-8699-aca237eedb9a.png)

Makerchip is the online IDE which provide working in TL verilog, it provide different windows to visualize out design.

# Basic_Hexadecimal_Calculator
***Firstly i implemented basic calculator design.***

![image](https://user-images.githubusercontent.com/70278767/119695576-f0766080-be6b-11eb-88ee-6f07ef95da85.png)

***#this is the visualization.***

![image](https://user-images.githubusercontent.com/70278767/119696095-75617a00-be6c-11eb-8ace-84163da8bf75.png)

# RISC_V_CPU_Core

***It is a 5 pipelined, 32 bit CPU with 32 General purpose registers with 6 Addressing modes of operation.***

***Blocks of cpu-***

> Program counter
>
> Instruction memory
>
> Instruction decoder
> 
> Regester file reader
> 
> ALU
> 
> Register file writer 
> 
> Data memory

![image](https://user-images.githubusercontent.com/70278767/119697257-a42c2000-be6d-11eb-99e0-ad7294ccced7.png)

***Addresing Modes-***

>R addresing Mode
>
>B addresing Mode
>
>S addresing Mode
>
>I addresing Mode
>
>J addresing Mode
>
>U addresing Mode

***And this is my final CPU core***

![image](https://user-images.githubusercontent.com/70278767/119699706-0ede5b00-be70-11eb-966d-ecd084e1375b.png)

# This are the instructions i fed into my CPU This is the machine level code to find the sum of first 10 natural numbers and save the result in memory

   m4_asm(ADD, r10, r0, r0)             // Initialize r10 (a0) to 0.
   
   // Function:
   
   m4_asm(ADD, r14, r10, r0)            // Initialize sum register a4 with 0x0
   
   m4_asm(ADDI, r12, r10, 1010)         // Store count of 10 in register a2.
   
   m4_asm(ADD, r13, r10, r0)            // Initialize intermediate sum register a3 with 0
   
   // Loop:
   
   m4_asm(ADD, r14, r13, r14)           // Incremental addition
   
   m4_asm(ADDI, r13, r13, 1)            // Increment intermediate register by 1
   
   m4_asm(BLT, r13, r12, 1111111111000) // If a3 is less than a2, branch to label named <loop>
   
   m4_asm(ADD, r10, r14, r0)
  
   m4_asm(SW, r0, r10, 10000)
   
   m4_asm(LW, r17, r0 ,10000)// Store final result to register a0 so that it can be read by main program
  

  
  ***And this is the final visualization of the working of cpu with these codes***
  
  

https://user-images.githubusercontent.com/70278767/119700678-2407b980-be71-11eb-81d7-89555b31fad4.mp4









