```
Inputs: in1, in2;
Outputs: out;

// 1. specify the components you want to use here
Parts: not1 NOT, not2 NOT, and1 AND, and2 AND, or OR;

// 2. wire them up
Wires: in1 -> and1.in1, in2 -> not2.in, not2.out -> and1.in2,
       in2 -> and2.in1, in1 -> not1.in, not1.out -> and2.in2,
       and1.out -> or.in1, and2.out -> or.in2, or.out -> out;
```
