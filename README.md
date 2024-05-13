# F-E-Smart-Contract
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.10;

        //Contract contains two state variables.
contract mineContract {
        //These variables are publicly accessible, that means that thier values can read by anyone.
    uint256 public p = 20;
    uint256 public j = 10;
        //if the condition fails, it reverts the transaction with the specified error msg.
    function requireValue(uint256 _value) public pure returns (uint256){
        require(_value <= 20, "Value must be less tahn or equals to 20");
        return _value;
    }
        //if the assertion fails, it indicates a critical error, and transaction is revert
    function assertValue() public view returns (uint256){
        uint256 result = p + j;
        assert(result == 30);
        return result;
    }
    
    function revertValue() public pure returns (uint256){
        uint256 a = 20;
        uint256 b = 0;
        if (b == 0){
            revert("Divident cannot be zero");
        }

        return a/b;
    }
}
