# smart-contract
pragma solidity >=0.4.22 <0.6.6;
contract SplitIt {
adress[] emplyees = [0x942Bb39c93306091AB7962702FDDF5d46F94152B,
0xea856591bA9e78B76AfA8f876Eb245c700c9460F];
uint totalReceivedMoney = 0;
mapping (address => uint) withdrawnAmounts;
function SplitIt () payable {
updateTotalReceivedMoney();
}
function () payable {
updateTotalReceivedMoney ();
}
function updateTotalReceivedMoney () internal {
totalReceivedMoney = totalReceivedMoney + msg.value;
}
modifier canWithdraw () {
bool contains = false;
for(uint i = 0; i < employees.length; i++) {
if (employees[i] == msg.sender) {
contains = true;
//break
}
}
require(contains);
_;
}
function Withdraw () canWithdraw {
uint amountAllocated = totalReceivedMoney / employees.length;
uint amountWithdrawn = withdrawnAmounts[msg.sender];
uint amount = amountAllocated - amountWithdrawn;
withdrawnAmounts[msg.sender] = amountWithdrawn + amount;
if (amount > o){
msg.sender.transfer(amount);
}
} 
}
