
1. Look at the example of init code in today's notes

  When we do the CODECOPY operation, what are we overwriting?
  (debugging this in Remix might help here)
  -  Overwriting the `value1` when we do a `CODECOPY`
2. Could the answer to Q1 allow an optimisation?
  - Yes saving the `value1` as constant instead of initializing it in the constructor, saves approx 20k gas.
3. Can you trigger a revert in the init code in Remix?
4. Write some Yul to
  1. Add 0x07 to 0x08
  2. store the result at the next free memory location.
  3. (optional) write this again in opcodes
5. Can you think of a situation where the opcode EXTCODECOPY is used?
6. Complete the assembly exercises in this repo
