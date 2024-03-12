1. By re-ordering the variables, can you reduce the number of storage slots needed?
  -- Yes by re-ordering the variable in the struct and declarations it uses less storage spaces as it pack the variables together.
  ```solidity
  // SPDX-License-Identifier: UNLICENSED
  pragma solidity ^0.8.13;
  
  contract Store {
  
      struct payments {
          uint256 amount;
          uint256 finalAmount;
          uint256 initialAmount;
          address sender;
          address receiver;
          uint8 paymentType;
          bool valid;
          bool checked;
      }
  
      uint256 public number;
      uint8 index;
      bool flag1;
      bool flag2;
      bool flag3;
      address admin;
      address admin2;
      mapping (address => uint256) balances;
      payments[8] topPayments;
  
      constructor() {}
  
      function setNumber(uint256 newNumber) public {
          number = newNumber;
      }
  
      function increment() public {
          number++;
      }
  }
  ```
