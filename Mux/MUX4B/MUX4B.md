```
Inputs: in1[4], in2[4], sel;
Outputs: out[4];

// 1. specify the components you want to use here
Parts: mux1 MUX, mux2 MUX, mux3 MUX, mux4 MUX;

// 2. wire them up
Wires: in1[1] -> mux1.in1, in2[1] -> mux1.in2, sel -> mux1.sel,
       in1[2] -> mux2.in1, in2[2] -> mux2.in2, sel -> mux2.sel,
       in1[3] -> mux3.in1, in2[3] -> mux3.in2, sel -> mux3.sel,
       in1[4] -> mux4.in1, in2[4] -> mux4.in2, sel -> mux4.sel,
       mux1.out -> out[1], mux2.out -> out[2],
       mux3.out -> out[3], mux4.out -> out[4];
```
