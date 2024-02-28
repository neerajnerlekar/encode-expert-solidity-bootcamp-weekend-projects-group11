## Homework 2

Solidity

1.  Write a function that will delete items (one at a
    time) from a dynamic array without leaving
    gaps in the array. You should assume that the
    items to be deleted are chosen at random, and
    try to do this in a gas efficient manner.
    For example imagine your array has 12 items
    and you need to delete the items at indexes 8,
    2 and 7.
    The final array will then have items
    {0,1,3,4,5,6,9,10,11

    ***

> Solution

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

contract ArrayItems() {
    uint[] public array;

    function removeRandomArrayItems(uint index) public {
        // move item to the last
        array[index] = array[array.length -1];
        //remove item
        array.pop();
        }

    function testRemoveArrayItems() external {
        array = [0,1,2,3,4,5,6,7,8,9,10,11];

        // remove item at index 8
        removeRandomArrayItems(8);
        assert(array.length == 11);
        assert(array[8] == 9)

        // remove item at index 2
        removeRandomArrayItems(2);
        assert(array.length == 10);
        assert(array[2] == 3)

        // remove item at index 7
        removeRandomArrayItems(7);
        assert(array.length == 9);
        assert(array[7] == 10);
        }
    }
```
