```
Inputs: in[4], load, reset;
Outputs: out[4];

// 1. specify the components you want to use here
Parts: mux1 MUX4B, mux2 MUX4B, reg REGISTER4B, add ADDER4B, not NOT;

// 2. wire them up
Wires: reg.out -> mux1.in1, in -> mux1.in2, load -> mux1.sel,
       mux1.out -> add.in1, 0000 -> add.in2, not.out -> add.carryIn,
       add.out -> mux2.in1, 0000 -> mux2.in2, reset -> mux2.sel,
       load -> not.in, mux2.out -> reg.in, 1 -> reg.load,
       reg.out -> out;
```
