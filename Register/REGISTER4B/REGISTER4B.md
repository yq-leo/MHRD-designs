```
Inputs: in[4], load;
Outputs: out[4];

// 1. specify the components you want to use here
Parts: reg1 REGISTER, reg2 REGISTER, reg3 REGISTER, reg4 REGISTER;

// 2. wire them up
Wires: in[1] -> reg1.in, load -> reg1.load, reg1.out -> out[1],
       in[2] -> reg2.in, load -> reg2.load, reg2.out -> out[2],
       in[3] -> reg3.in, load -> reg3.load, reg3.out -> out[3],
       in[4] -> reg4.in, load -> reg4.load, reg4.out -> out[4];
```
