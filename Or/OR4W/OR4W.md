```
Inputs: in[4];
Outputs: out;

// 1. specify the components you want to use here
Parts: or1 OR, or2 OR, or3 OR;

// 2. wire them up
Wires: in[1] -> or1.in1, in[2] -> or1.in2,
       in[3] -> or2.in1, in[4] -> or2.in2,
       or1.out -> or3.in1, or2.out -> or.in2, or3.out -> out;
```
