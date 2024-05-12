# canid8

canid8 is a toy CPU architecture I wanted to make because I wanted to write a virtual machine and a compiler, and maybe a hardware design one day. Let's see how this goes.

As of day 1, taking architectural inspiration from the AVR family of microcontrollers

## Brainstorm

I like register based architectures, I don't know why, but i want registers.

AVRs get away with 8-bit, so after all, why shouldn't I?

AVRs have 32 general purpose registers

I want minimal operations on the ALU, and as few opcodes as necessary to implement a universal computer, while still being comprehensible.

NAND is functionally complete, and therefore AND+NOT is functionally complete, and therefore AND+OR+NOT is functionally complete, the ALU shall support AND+OR+NOT.

