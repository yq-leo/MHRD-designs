```
Inputs: instr[16], data[16], reset;
Outputs: write, dataAddr[16], instrAddr[16], result[16];

// 1. more devices are needed to implement behavior as described in specification
Parts:
	decoder DECODER, mReg REGISTER16B, aReg REGISTER16B, pc COUNTER16B, alu
ALU16B,
	and AND, op1mux MUX16B, op2mux MUX4W16B, mrmux MUX16B;

// 2. wire them up
Wires: instr -> decoder.instr,
       
       decoder.loadM -> mReg.load, decoder.cToM -> mrmux.sel,
       alu.out -> mrmux.in1, decoder.constant -> mrmux.in2[1:15],
       mrmux.out -> mReg.in,
       
       decoder.loadA -> aReg.load, alu.out -> aReg.in,
       decoder.loadM -> write, decoder.opCode -> alu.opCode,
       
       aReg.out -> op1mux.in1, decoder.constant[1:5] -> op1mux.in2[1:5],
       decoder.op1 -> op1mux.sel, op1mux.out -> alu.in1,
       
       decoder.constant[1:5] -> op2mux.in1[1:5], aReg.out -> op2mux.in2,
       mReg.out -> op2mux.in3, data -> op2mux.in4,
       decoder.op2 -> op2mux.sel, op2mux.out -> alu.in2,
       
       decoder.jmpIfZ -> and.in1, alu.zero -> and.in2,
       and.out -> pc.load, mReg.out -> pc.in,
       
       alu.out -> result,
       mReg.out -> dataAddr,
       pc.out -> instrAddr,
       reset -> pc.reset;
```
