# MyToken

MyToken is a simple token management module implemented in the Move programming language, designed to run on the Aptos blockchain. This module allows users to create, mint, and transfer tokens.

## Features

- **Token Creation**: Initialize a new token with a name, symbol, and total supply.
- **Token Minting**: Mint new tokens and add them to the creator's balance.
- **Token Transfers**: Transfer tokens between users.

## Requirements

- Aptos Framework
- Aptos Standard Library
- Move Standard Library

## Installation

Make sure you have the necessary dependencies in your project. The dependencies are listed in the `Move.toml` file:

```toml
[package]
name = "MyToken"
version = "0.0.1"
authors = ["Your Name <youremail@example.com>"]
license = "MIT"

[dependencies]
AptosFramework = { git = "https://github.com/aptos-labs/aptos-core.git", subdir = "aptos-move/framework/aptos-framework", rev = "some_commit_hash" }
AptosStd = { git = "https://github.com/aptos-labs/aptos-core.git", subdir = "aptos-move/framework/aptos-std", rev = "some_commit_hash" }
MoveStdlib = { git = "https://github.com/aptos-labs/aptos-core.git", subdir = "aptos-move/framework/move-stdlib", rev = "some_commit_hash" }
```

Be sure to replace `some_commit_hash` with the relevant commit hashes for your dependencies.

## Addresses

Ensure that the `MyToken` module is properly deployed at the specified address:

```toml
[addresses]
MyToken = "0x92cd929e80ce2d471f13bae113040b9eed1c1b582a75291a472277574a3df02b"
```

## Usage

### 1. Create a Token

The `create_token` function initializes a new token with a specified name, symbol, and total supply:

```move
public fun create_token(
    account: &signer,
    name: String,
    symbol: String,
    total_supply: u64,
)
```

Example:

```move
create_token(account, "MyToken", "MTK", 1_000_000);
```

### 2. Mint Tokens

The `mint_tokens` function allows the creator to mint new tokens and add them to their own balance:

```move
public fun mint_tokens(
    account: &signer,
    amount: u64,
)
```

Example:

```move
mint_tokens(account, 100_000);
```

### 3. Transfer Tokens

The `transfer_tokens` function transfers tokens from one user to another:

```move
public fun transfer_tokens(
    sender: &signer,
    recipient: address,
    amount: u64,
)
```

Example:

```move
transfer_tokens(sender, recipient_address, 50_000);
```
