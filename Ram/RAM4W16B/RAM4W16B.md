```
Inputs: in[16], load, address[2];
Outputs: out[16];

// 1. specify the components you want to use here
Parts: reg1 REGISTER16B, reg2 REGISTER16B, reg3 REGISTER16B, reg4 REGISTER16B,
       demux DEMUX4W, mux MUX4W16B;

// 2. wire them up
Wires: in -> reg1.in, demux.out1 -> reg1.load, reg1.out -> mux.in1,
       in -> reg2.in, demux.out2 -> reg2.load, reg2.out -> mux.in2,
       in -> reg3.in, demux.out3 -> reg3.load, reg3.out -> mux.in3,
       in -> reg4.in, demux.out4 -> reg4.load, reg4.out -> mux.in4,
       load -> demux.in, address -> demux.sel,
       address -> mux.sel, mux.out -> out;
```

