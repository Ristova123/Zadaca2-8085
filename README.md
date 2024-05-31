# Zadaca2-8085

Да се иницијализира компонентата 8155/56 така да RAM-от
зафаќа простор 4800h–48FFh. Портата А да се иницијализира
како стробирана влезна порта, а B како обична излезна.
Тајмерот брои поворка од кратки импулси со T = 1ms.
(f=4MHZ). 

**Resenie:**

```
А15 А14 А13 А12 А11

32к 16к  8к  4к  2к

0    1   0   0    1 
```

 ![Screenshot (1)](https://github.com/slavko444/8085-Zadaca-2/blob/main/Diagram.png)
 


```
CSR 01001 000

PA 01001 001

PB 01001 010

PC 01001 011

TLSB 01001 100

TMSB 01001 101

T=0,25 microsec, Ts = 0,5 microsec; 1 ms = 2000 * 0,5 microsec; 2000 = 7*256+208

TMSB 11000111

TLSB 11010000

CSR 11010110

MVI A, 208d        CSR EQV 01001000

OUT TLSB           TMSB EQV 01001101

MVI A, 199d        TLSB EQV 01001100

OUT TMSB

MVI A, D6h

OUT CSR

END
```

**Develop by:**

[Tamara Ristova ](https://github.com/Ristova123)


**Subject**

Microcomputer's systems

**Built With**

This project is built using the following tools:

- [e8085](https://emu8086-microprocessor-emulator.en.softonic.com/): Assembler and emulator for the Intel 8085 microprocessor.

**Getting Started**

To get a local copy up and running, follow these steps.

**Prerequisites**

In order to run this project you need:

A working computer
Connection to internet
Setup

**How to Run**

To run the program, you need an 8085 emulator or assembler. You can use emulators like DOSBox or TASM (Turbo Assembler). Here's how to run the program using e8085.exe:

1. Download and install e8085.exe from [here](https://emu8086-microprocessor-emulator.en.softonic.com/).
2. Clone this repository to your local machine.
3. Open e8085.exe and load the `zadaca-2-code.asm` file.
4. Assemble the code by pressing the Assemble button.
5. Run the program by pressing the Run button or by pressing F10.
