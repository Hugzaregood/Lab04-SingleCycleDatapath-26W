## Name: Nicholas Castellanos
## Email: ncast094@ucr.edu

## Section #1:

Some issues I encountered was Verilog not being installed on my system. 
This was due to forgetting that I had installed it on my PC rather than on my laptop which I needed for this lab. 
I also had some issues figuring out how to use the splitter between cpumemory and cpu_registers

This was my original version before I knew I had to also connect SignEx (Which I forgot because of how small it was lol):
- opcode → bits [31–26]
- rs → bits [25–21]
- rt → bits [20–16]
- rd → bits [15–11]
- funct → bits [5–0]

Now instead I had to change it into this: 
- opcode → bits [31–26]
- rs → bits [25–21]
- rt → bits [20–16]
- rd → bits [15–11]
- immediate (SignEx) → [15–0]
- funct (ALU) → bits [5–0]

Finally one small tool that helped me was using Tunnels for less wiring around the circuit board which helped immensely.

## Section #2:

Execution Traced MIPS instructions that were assembled for this lab:

| Instruction | Binary Representation | Machine Code (Hex) |
|------------ | ---------------------- | -------------------|
| `and $t0 $t1 $t2` | 000000 01001 01010 01000 00000 10010 | 0x012A4024 |
| `addi $t3 $t4 123` | 001000 01100 01011 0000000001111011 | 0x218B007B |
| `lw $t5, 135($t1)` | 100011 01001 01101 0000000010000111 | 0x8D2D0087 |
| `sw $t3, 136($t1)` | 101011 01001 01011 0000000010001000 | 0xAD2B0088 |
| `beq $t3, $zero, -10` | 000100 01011 00000 1111111111110110 | 0x1160FFF6 |

