1. Look at the example of init code in today's notes
    When we do the CODECOPY operation, what are we overwriting?
    (debugging this in Remix might help here)
      - Overwriting the `value1` when we do a `CODECOPY`
2. Could the answer to Q1 allow an optimisation?
    - Yes saving the `value1` as constant instead of initializing it in the constructor, saves approx 20k gas.
3. Can you trigger a revert in the init code in Remix?
4. Write some Yul to
    1. Add 0x07 to 0x08
    2. store the result at the next free memory location.
    3. (optional) write this again in opcodes
5. Can you think of a situation where the opcode EXTCODECOPY is used?
6. Complete the assembly exercises in this repo
     - `Assembly_1.sol`
         -
       ```solidity
            pragma solidity ^0.8.4;
            contract Intro {
                function intro() public pure returns (uint16) {
                    uint256 mol = 420;
            
                    assembly {
                        // Instantiate a stack variable that holds the value of mol
                        let stackVar := mol
                        
                        // Memory location to store the result
                        let memLocation := 0x20
                        
                        // Store the value of the stack variable in memory
                        mstore(memLocation, stackVar)
                        
                        // Return the value stored in memory
                        return(memLocation, 0x20)
                    }
                }
            }
       ```
      - `Assembly2_sol`
         ```solidity
         pragma solidity ^0.8.4;
         pragma solidity ^0.8.4;

        contract Add {
            function addAssembly(uint256 x, uint256 y) public pure returns (uint256) {
            uint256 result;

                assembly {
                // Add x and y and store the result in memory
                result := add(x, y)
                }

               assembly {
                // Return the result stored in memory
                return(result)
              }
           }
        }

         ```
