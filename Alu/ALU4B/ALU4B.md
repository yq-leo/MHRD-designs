```
Inputs: in1[4], in2[4], opCode[4];
Outputs: out[4], negative, zero;

// 1. specify the components you want to use here
Parts: not1 NOT4B, not2 NOT4B, not3 NOT4B, not4 NOT4B,
       mux1 MUX4B, mux2 MUX4B, mux3 MUX4B, mux4 MUX4B,
       nand NAND4B, add ADDER4B,
       and1 AND, and2 AND, and3 AND, and4 AND;
       
// 2. wire them up
Wires: in1 -> mux1.in1, in1 -> not1.in, not1.out -> mux1.in2,
       opCode[4] -> mux1.sel,
       in2 -> mux2.in1, in2 -> not2.in, not2.out -> mux2.in2,
       opCode[3] -> mux2.sel,
       mux1.out -> add.in1, mux2.out -> add.in2, 0 -> add.carryIn,
       mux1.out -> nand.in1, mux2.out -> nand.in2,
       add.out -> mux3.in1, nand.out -> mux3.in2, opCode[2] -> mux3.sel,
       mux3.out -> mux4.in1, mux3.out -> not4.in, not4.out -> mux4.in2,
       opCode[1] -> mux4.sel, mux4.out -> out,
       
       mux4.out[4] -> negative,
       mux4.out -> not3.in, not3.out[1] -> and1.in1, not3.out[2] -> and1.in2,
       not3.out[3] -> and2.in1, not3.out[4] -> and2.in2,
       and1.out -> and3.in1, and2.out -> and3.in2, and3.out -> zero;
```
