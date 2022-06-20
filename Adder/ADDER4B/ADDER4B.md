```
Inputs: in1[4], in2[4], carryIn;
Outputs: out[4], carryOut;

// 1. specify the componetns you want to use here
Parts: fadd1 FULLADDER, fadd2 FULLADDER, 
       fadd3 FULLADDER, fadd4 FULLADDER;
       
// 2. wire them up
Wires: in1[1] -> fadd1.in1, in2[1] -> fadd1.in2,
       carryIn -> fadd1.carryIn, fadd1.out -> out[1],
       in1[2] -> fadd2.in1, in2[2] -> fadd2.in2,
       fadd1.carryOut -> fadd2.carryIn, fadd2.out -> out[2],
       in1[3] -> fadd3.in1, in2[3] -> fadd3.in2,
       fadd2.carryOut -> fadd3.carryIn, fadd3.out -> out[3],
       in1[4] -> fadd4.in1, in2[4] -> fadd4.in2,
       fadd3.carryOut -> fadd4.carryIn, fadd4.out -> out[4],
       myfadd4.carryOut -> carryOut;
```
