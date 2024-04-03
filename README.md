# Solidity Smart Contracts README

This repository contains two Solidity smart contracts: ERC20 token and Vault.

## ERC20 Token Contract

The ERC20 contract implements a standard token interface with basic functionalities such as transferring tokens, approving spending, and allowance management. Here are some key points about this contract:

- **Name**: Solidity by Example
- **Symbol**: SOLBYEX
- **Decimals**: 18
- **Total Supply**: Initial supply is set to 0, and tokens can be minted by calling the `mint` function.
- **Events**: The contract emits `Transfer` and `Approval` events upon token transfers and approvals.

### Functions

1. `transfer`: Allows transferring tokens from the sender's account to another address.
2. `approve`: Allows the sender to approve a spender to spend tokens on their behalf.
3. `transferFrom`: Allows transferring tokens from one address to another, provided the sender has been approved to do so.
4. `mint`: Allows minting new tokens. Only the contract deployer can call this function.
5. `burn`: Allows burning tokens, reducing the total supply. Tokens can only be burned by the owner of the tokens.

## Vault Contract

The Vault contract is designed to securely hold ERC20 tokens and allow users to deposit and withdraw them in a trustless manner. Here are some key points about this contract:

- **Token**: The contract accepts an ERC20 token address during deployment, defining the token to be stored in the vault.
- **Total Supply**: Tracks the total supply of shares representing ownership in the vault.
- **Functions**:
    - `deposit`: Allows users to deposit ERC20 tokens into the vault in exchange for shares.
    - `withdraw`: Allows users to withdraw ERC20 tokens from the vault by providing the corresponding number of shares.

### Deposit Function

The `deposit` function calculates the number of shares to mint based on the proportion of the deposited amount to the current total supply of shares. It then transfers the deposited tokens from the sender to the vault.

### Withdraw Function

The `withdraw` function calculates the amount of tokens to be withdrawn based on the proportion of shares to the current total supply. It then transfers the corresponding amount of tokens from the vault to the sender.

## Getting Started

To deploy and interact with these contracts, you'll need a development environment set up with Solidity and a testing framework like Truffle or Hardhat. You can deploy the contracts on local testnets or public Ethereum networks.

Feel free to explore and modify these contracts for your own use cases!

