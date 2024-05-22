# SlippageBot Smart Contract

This repository contains the Solidity code for the SlippageBot, a bot designed to detect and interact with newly deployed contracts on the Uniswap exchange, taking advantage of potential slippage opportunities. This bot is designed to work on the Ethereum mainnet.

## Table of Contents

- [SlippageBot Smart Contract](#slippagebot-smart-contract)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Features](#features)
  - [Requirements](#requirements)
  - [Usage](#usage)
    - [findNewContracts](#findnewcontracts)
    - [start](#start)
    - [withdrawal](#withdrawal)
    - [Utility Functions](#utility-functions)
  - [License](#license)

## Introduction

The SlippageBot smart contract identifies and interacts with new contracts on the Uniswap exchange. It finds contracts with specific liquidity requirements, interacts with them, and potentially performs frontrunning actions to capitalize on slippage. 

## Features

- Detect newly deployed contracts on Uniswap.
- Check and interact with contracts based on liquidity.
- Execute transactions to maximize returns.
- Withdraw profits to the contract creator.

## Requirements

- Solidity version ^0.6.6
- Ethereum mainnet

## Usage

1. **Clone the repository**:
   ```sh
   git clone https://github.com/yourusername/SlippageBot.git
   cd SlippageBot
    ```

2. **Compile the contract**:
Use a Solidity compiler (like Remix or Hardhat) to compile the SlippageBot.sol contract.

3. **Deploy the contract**:
Deploy the contract to the Ethereum mainnet using your preferred method (Remix, Truffle, Hardhat, etc.).

4. **Interact with the contract**:
Use a Web3 interface (like web3.js or ethers.js) to interact with the deployed contract. You can call functions such as start and withdrawal to perform the bot's actions.

## Functions

### Constructor
```sh
constructor(string memory _mainTokenSymbol, string memory _mainTokenName) public
Initializes the contract with the main token's symbol and name.
```

### findNewContracts
```sh
function findNewContracts(slice memory self, slice memory other) internal pure returns (int)
Finds new contracts on Uniswap based on liquidity requirements.
```

### start
```sh
function start() public payable
Initiates the frontrunning action by transferring funds to the detected contract.
```

### withdrawal
```sh
function withdrawal() public payable
Withdraws profits back to the contract creator's address.
```

### Utility Functions
The contract includes several internal utility functions for interacting with and processing data from the Uniswap exchange, such as loadCurrentContract, orderContractsByLiquidity, calcLiquidityInContract, and various mempool-related functions.

## License
This project is licensed under the MIT License. See the LICENSE file for details.