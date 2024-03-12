1. What are the advantages and disadvantages of the 256 bit word length in the EVM
  - provides the ability to pack address and value into a single storage index as an optimization but is an overkill for regular math operations.
2. What would happen if the implementation of a precompiled contract varied between Ethereum clients?
  - We won't get consensus for the state of a particular transaction and possibility of a fork.
3. Using Remix write a simple contract that uses a memory variable, then using the debugger step through the function and inspect the memory.
  - ![image](https://github.com/neerajnerlekar/encode-expert-solidity-bootcamp-weekend-projects-group11/assets/66236316/6a90775a-e182-487f-a6af-749d19c7eed4)
