# SimpleStorage
// I'm a comment!
// SPDX-License-Identifier: MIT

pragma solidity 0.8.30;

// pragma solidity ^0.8.0;
// pragma solidity >=0.8.0 <0.9.0;

contract SimpleStorage {
    uint256 public myFavoriteNumber;
   // uint256[] listOfFavoriteNumbers; 
   struct Person{
    uint256 favoriteNumber;
    string name;
   }
   // Person public pat = Person({favoriteNumber: 2, name: "Pat"});
   Person[] public listOfPeople;
   mapping(string => uint256) public nameToFavoriteNumber; //mapping is like a hashmap or dictionary in other languages)

 function store(uint256 _favoriteNumber) public {
        myFavoriteNumber = _favoriteNumber;
    }

    function retrieve() public view returns (uint256) {
        return myFavoriteNumber;
    }
    function addperson(string memory _name, uint256 _favoriteNumber) public{
        listOfPeople.push(Person(_favoriteNumber,_name)); //add person ti list of array
        nameToFavoriteNumber[_name] = _favoriteNumber; //add map

    }
}
