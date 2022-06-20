```
Inputs: instr[16];
Outputs: cToM, loadA, loadD, loadM, op1, op2[2], opCode[4], jmpIfZ,
constant[15];

// 1. specify the components you want to use here
Parts: not1 NOT, not2 NOT, not3 NOT,
       and1 AND, and2 AND, and3 AND, and4 AND, and5 AND, and6 AND,
       or OR;

// 2. wire them up
Wires: instr[16] -> cToM, instr[13] -> op1, instr[11:12] -> op2,
       instr[7:10] -> opCode, instr[1:15] -> constant,
       
       instr[16] -> not1.in, instr[16] -> or.in2,
       not1.out -> and3.in1, not1.out -> and5.in1, not1.out -> and1.in1,
       instr[15] -> and2.in1, instr[15] -> not2.in, instr[15] -> and6.in1,
       not2.out -> and3.in2,
       instr[14] -> and2.in2, instr[14] -> not3.in, instr[14] -> and4.in2,
       not3.out -> and6.in2,
       instr[6] -> and5.in2,
       
       and1.out -> loadD,
       and2.out -> and1.in2,
       and3.out -> and4.in1,
       and4.out -> loadA,
       and5.out -> jmpIfZ,
       and6.out -> or.in1,
       or.out -> loadM;
```
