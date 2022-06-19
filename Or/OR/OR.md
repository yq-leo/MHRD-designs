```
Inputs: in1, in2;
Outputs: out;

// 1. specify the components you want to use here
Parts: not1 NOT, not2 NOT, nand NAND;

// 2. wire them up
Wires: in1 -> not1.in, not1.out -> nand.in1,
       in2 -> not2.in, not2.out -> nand.in2,
       nand.out -> out;
```
