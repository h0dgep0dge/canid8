# canid8

canid8 is a toy CPU architecture I wanted to make because I wanted to write a virtual machine and a compiler, and maybe a hardware design one day. Let's see how this goes.

As of day 1, taking architectural inspiration from the AVR family of microcontrollers

## Arithmetic Logic Unit

I want minimal operations on the ALU, and as few opcodes as necessary to implement a universal computer, while still being comprehensible. I'm even tempted to make the only arithmetic operation addition, so let's try it.

NAND is functionally complete, and therefore AND+NOT is functionally complete, and therefore AND+OR+NOT is functionally complete, the ALU shall support AND+OR+NOT.

## Memory

I like register based architectures, I don't know why, but i want registers.

AVRs get away with 8-bit, so after all, why shouldn't I?

AVRs have 32 general purpose registers, 32 seems like a find number, let's make it 32.

Some of the registers will be paired into 16 bit accumulators, for accessing memory. The AVRs have 3, so I'll have 3.

We could support operations that provide an immediate address, but in the name of a simpler instruction set, why not only support indirect addressing? So all memory access will be indirectly addressed.

In fact, no immediate values, let's say only indirect values too.

## Operations

ALU
 - ADD Rr Rd -> Rd = Rd + Rr 
 - ADC Rr Rd -> Rd = Rd + Rr + carry
 - AND Rr Rd -> Rd = Rd & Rr
 - OR Rr Rd  -> Rd = Rd | Rr
 - NOT Rd    -> Rd = !Rd (bitwise! not boolean!)

Flow
 - JUMP  -> copy accumulator register to program counter
 - JMPIZ -> copy accumulator register to program counter, if register is zero

Memory
 - LOAD  -> copy byte from memory to register
 - STORE -> copy byte from register to memory
 - MOVE  -> overloaded assembler macro? is this a thing?
