```
Inputs: in, load;
Outputs: out;

// 1. specify the components you want to use here
Parts: dff DFF, and1 AND, and2 AND, and3 AND,
       not NOT, or OR;

// 2. wire them up
Wires: in -> and1.in1, load -> and1.in2, and1.out -> or.in1,
       dff.out -> and2.in1, load -> not.in, not.out -> and2.in2,
       and2.out -> or.in1, or.out -> dff.in, dff.out -> out;
```
