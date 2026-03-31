# Simple-Subscription-Monthly-
Simple Subscription (Monthly)
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

contract Subscription {
    mapping(address => uint256) public expiry;

    function subscribe() public payable {
        require(msg.value == 0.01 ether, "Fee 0.01 ETH");
        expiry[msg.sender] = block.timestamp + 30 days;
    }
}
