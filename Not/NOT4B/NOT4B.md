```
Inputs: in[4];
Outputs: out[4];

// 1. specify the components you want to use here
Parts: not1 NOT, not2 NOT, not3 NOT, not4 NOT;

// 2. wire them up
Wires: in[1] -> not1.in, not1.out -> out[1],
       in[2] -> not2.in, not2.out -> out[2],
       in[3] -> not3.in, not3.out -> out[3],
       in[4] -> not4.in, not4.out -> out[4];
```
