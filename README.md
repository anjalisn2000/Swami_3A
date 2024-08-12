# Swami_3A
Implement use of solidity : variables,operators,loops,dm,strings,arrays,Enums,struct,mapping,conversion,ether unit,special variables
[I] Variable [add the valu after debuging from numbers]
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;
contract variable_demo {
    uint256 sum = 4;
    uint256 x;
    address a;
    string s = "welcome";

    function add(uint256) public {
        uint256 y = 2;
        sum = sum + x + y;
    }

    function display() public view returns (uint256) {
        return sum;
    }

    function displayMsg() public view returns (string memory){
        return s;
    }
}
======================================================
[II] Operators[add-5,5  div-4,2  5,9  sub 20,5]
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0; 
 
contract Operators { 
     
    uint256 result = 0; 
 
    function addition(uint256 a, uint256 b) public pure returns (uint256) { 
        return a + b; 
    } 
 
    function subtraction(uint256 a, uint256 b) public pure returns (uint256) { 
        return a - b; 
    } 
 
    function division(uint256 a, uint256 b) public pure returns (uint256) { 
        return a / b; 
    } 
 
    function multiply(uint256 a, uint256 b) public pure returns (uint256) { 
        return a * b; 
    } 
}
================================
Loops
pragma solidity ^0.5.0; 
contract LoopingTest { 
    uint256 storedData; 
    constructor() public { 
        storedData = 10; 
    } 
    function getResult() public pure returns (string memory) { 
        uint256 a = 10; 
        uint256 b = 2; 
        uint256 result = a + b; 
        return integerToString(result); 
    } 
    function integerToString(uint256 _i) internal pure returns (string memory) { 
        if (_i == 0) { 
            return "0"; 
        } 
        uint256 j = 0; 
        uint256 len; 
        for (j = _i; j != 0; j /= 10) { 
            //for loop example 
            len++; 
        } 
        bytes memory bstr = new bytes(len); 
        uint256 k = len - 1; 
        while (_i != 0) { 
            bstr[k--] = bytes1(uint8(48 + (_i % 10))); 
            _i /= 10; 
        } 
        return string(bstr); //access local variable 
    } 
}
=========================
[IV] Decision Making
pragma solidity ^0.5.0;
 contract ifelsedemo
 {
 uint i=10;
 function decision_making() public view returns(string memory)
 {
 if(i%2==0)
 {
     return "even";
 }
 else
 {
    return "Odd";
 }
 }
 }
=======================
[V] Strings
pragma solidity ^0.5.0;
 contract LearningStrings {
 string text;
 function getText() public view returns (string memory) {
 return text;
 }
 function setText() public {
 text = "hello";
 }
 function setTextByPassing(string memory message) public {
 text = message;
 }
 }
================================
 [VI] Arrays [50,20]
 // SPDX-License-Identifier: MIT 
pragma solidity 0.7.0; 
 
contract Arrays { 
 
    function initArray() public pure returns (uint256) { 
        uint128[3] memory array = [1, 2, uint128(3)]; 
        return array[0]; 
    } 
 
    function dynamicArray(uint256 a, uint256 b) public pure returns (uint256) { 
         
        uint128[] memory array = new uint128[](a); 
        uint128 val = 5; 
 
        for (uint128 j = 0; j < a; j++) { 
            array[j] = j * val; 
        } 
 
        return array[b]; 
    } 
}
========================================================
[VII] Enums
CODE:
pragma solidity ^0.5.0; 
 
contract enumTest { 
    enum FreshJuiceSize { 
        SMALL, 
        MEDIUM, 
        LARGE 
    } 
    FreshJuiceSize choice; 
    FreshJuiceSize constant defaultChoice = FreshJuiceSize.MEDIUM; 
 
    function setLarge() public { 
        choice = FreshJuiceSize.LARGE; 
    } 
 
    function getChoice() public view returns (FreshJuiceSize) { 
        return choice; 
    } 
 
    function getDefaultChoice() public pure returns (uint256) { 
        return uint256(defaultChoice); 
    } 
}
===========================================================================
[VIII] Structs
CODE:-
pragma solidity ^0.5.0;
 contract structdemo {
  struct Book {
    string name;
    string author;
    uint256 id;
    bool availability;
  }
  Book book2;
  Book book1 = Book("A Little Life", "Hanya Yanagihara", 2, false);
  function set_details() public {
    book2 = Book("Almond", "Sohn won-pyung", 1, true);
  }
  function book_info()
    public
    view
    returns (
      string memory,
      string memory,
      uint256,
      bool
    )
  {
    return (book1.name, book1.author, book1.id, book1.availability);
  }
  function get_details()
    public
    view
    returns (
      string memory, string memory, uint256, bool
    )
  {
    return (book2.name, book2.author, book2.id, book2.availability);
  }
 }
================================
[IX] Mappings [copy from after balance type--400]
pragma solidity ^0.5.0;
 contract LedgerBalance {
 mapping(address => uint256) public balances;
 function updateBalance(uint256 newBalance) public {
 balances[msg.sender] = newBalance;
 }	
 }
 contract Updater {
 function updateBalance() public returns (uint256) {
 LedgerBalance ledgerBalance = new LedgerBalance();
 return ledgerBalance.balances(address(this));
 }
 }
 ================================
 [X] Conversions [150 down 1500000000]
pragma solidity ^0.4.0; 
 
contract Conversions { 
    function intToUint(int8 a) public constant returns (uint256) { 
        uint256 b = uint256(a); 
        return b; 
    } 
 
    function uint32ToUint16(uint32 a) public constant returns (uint16) { 
        uint16 b = uint16(a); 
        return b; 
    } 
}
=========================================================================
[XI] Ether Units[60 in all box]
CODE:
// SPDX-License-Identifier: MIT
 pragma solidity ^0.8.0;
 contract SolidityTest {
  function convert_Amount_to_Wei(uint256 Amount) public pure returns (uint256) {
    return Amount * 1 wei;
  }
  function convert_Amount_To_Ether(uint256 Amount) public pure returns (uint256) {
    return Amount * 1 ether;
  }
  function convert_Amount_To_Gwei(uint256 Amount) public pure returns (uint256) {
    return Amount * 1 gwei;
  }
  function convert_seconds_To_mins(uint256 _seconds) public pure returns (uint256) {
   return _seconds / 60;
    }
 function convert_seconds_To_Hours(uint256 _seconds) public pure returns (uint256) {
    return _seconds / 3600;
 }
 
 function convert_Mins_To_Seconds(uint256 _mins) public pure returns (uint256) {
   return _mins * 60;
   }
 }
 ================================================
 [XII] Special Variables
CODE:
// SPDX-License-Identifier: MIT
 pragma solidity ^0.8.0;

 contract Special_Variables {
     mapping(address => uint256) rollNo;

     function setRollNO(uint256 _myNumber) public {
         rollNo[msg.sender] = _myNumber;
 }
 
     function whatIsMyRollNumber() public view returns (uint256) {
          return rollNo[msg.sender];
 }
 }







