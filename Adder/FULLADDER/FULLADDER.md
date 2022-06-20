```
Inputs: carryIn, in1, in2;
Outputs: out, carryOut;

// 1. specify the components you want to use here
Parts: hadd HALFADDER, xor XOR, and AND, or OR;

// 2. wire them up
Wires: in1 -> hadd.in1, in2 -> hadd.in2, 
       hadd.out -> xor.in1, carryIn -> xor.in2, xor.out -> out,
       carryIn -> and.in1, hadd.out -> and.in2,
       and.out -> or.in1, hadd.carry -> or.in2,
       or.out -> carryOut;
```
