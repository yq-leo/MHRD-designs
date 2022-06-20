```
Inputs: in, sel;
Outputs: out1, out2;

// 1.specify the components you want to use here
Parts: not NOT, and1 AND, and2 AND;

// 2. wire them up
Wires: in -> and1.in1, sel -> and1.in2, and1.out -> out2,
       in -> and2.in1, sel -> not.in, not.out -> and2.in2,
       and2.out -> out1;
```
