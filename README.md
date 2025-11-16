# SKILL-ASSESSMENT-1

# TO EXCHANGE CONTENTS OF TWO BLOCKS
# 8051 Program

## AIM
To write an assembly language program in 8051 to exchange the contents of two memory blocks of equal length 

## APPARATUS REQUIRED
- Personal computer
- Keil μVision IDE

## ALGORITHM
1.Start the program execution at address 00H.

2.Initialize register R0 with the starting address of Block 1 (e.g., 30H).

3.Initialize register R1 with the starting address of Block 2 (e.g., 40H).

4.Load register R2 with the number of bytes to be exchanged between the two blocks.

5.Begin the loop (label NEXT) to perform the exchange operation.

6.Move the byte from the memory location pointed by R0 (Block 1) into the accumulator A.

7.Move the byte from the memory location pointed by R1 (Block 2) into register B.

8.Transfer the contents of register B to the memory location pointed by R0 (Block 1).

9.Transfer the contents of accumulator A to the memory location pointed by R1 (Block 2).

10.Increment both R0 and R1 to point to the next memory locations in Block 1 and Block 2 respectively.

11.Decrement R2 and check whether all bytes have been exchanged.

12.If R2 ≠ 0, repeat the process from step 6.

13.If R2 = 0, all bytes are exchanged — jump to label HERE.

14.Enter an infinite loop (SJMP HERE) to stop further execution.

15.End the program.
## PROGRAM

ORG 0000H
11MOV R0, #30H      
MOV R1, #40H    
MOV R2, #05H      
NEXT: MOV A, @R0   
      MOV B, @R1   
      MOV @R0, B   
      MOV @R1, A  
      INC R0       
      INC R1       
      DJNZ R2, NEXT
HERE: SJMP HERE    
END


## OUTPUT


<img width="1920" height="1200" alt="sk1 1" src="https://github.com/user-attachments/assets/334820b1-e4fd-4c62-bde1-ee64a1df7813" />


<img width="1920" height="1200" alt="sk1 2" src="https://github.com/user-attachments/assets/46f563d2-3c29-4ddb-a7ad-9759b9b473fc" />



## RESULT
The program successfully exchanges the contents of two memory blocks of equal length, and the result is verified in the Keil µVision memory window.
