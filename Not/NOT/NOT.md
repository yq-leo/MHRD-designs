```
Inputs: in;
Outputs: out;

// 1. specify the components you want to use here
Parts: mynand NAND;

// 2. wire them up
Wires: in -> mynand.in1, in -> mynand.in2, mynand.out -> out;
```
