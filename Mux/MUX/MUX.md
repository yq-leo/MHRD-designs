```
Inputs: in1, in2, sel;
Outputs: out;

// 1. specify the components you want to use here
Parts: not NOT, and1 AND, and2 AND, or OR;

// 2. wire them up
Wires: sel -> not.in, not.out -> and1.in1, in1 -> and1.in2,
       sel -> and2.in1, in2 -> and2.in2,
       and1.out -> or.in1, and2.out -> or.in2, or.out -> out;
```
