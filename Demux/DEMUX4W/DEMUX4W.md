```
Inputs: in, sel[2];
Outputs: out1, out2, out3, out4;

// 1. specify the components you want to use here
Parts: not1 NOT, not2 NOT,
       and1 AND, and2 AND, and3 AND, and4 AND,
       and5 AND, and6 AND, and7 AND, and8 AND;

// 2. wire them up
Wires: sel[1] -> not1.in, sel[2] -> not2.in,

       not1.out -> and1.in1, not2.out -> and1.in2,
       and1.out -> and2.in1, in -> and2.in2, and2.out -> out1;
       
       sel[1] -> and3.in1, not2.out -> and3.in2,
       and3.out -> and4.in1, in -> and4.in2, and4.out -> out2,
       
       not1.out -> and5.in1, sel[2] -> and5.in2,
       and5.out -> and6.in1, in -> and6.in2, and6.out -> out3,
       
       sel[1] -> and7.in1, sel[2] -> and7.in2,
       and7.out -> and8.in1, in -> and8.in2, and8.out -> out4;
```
