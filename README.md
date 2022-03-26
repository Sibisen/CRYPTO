# 🚀 Solana SPL Tutorial
This repository contains full tutorial on Solana SPL token for the windows OS.

## Table of Contents
- [Prerequisites](#prerequisites)
- [Creating SPL Tokens](#creating-spl-tokens)
- [Creating SPL NFTs](#creating-spl-nfts)
- [Further Resources](#further-resources)


### Prerequisites

#### 1. Solana CLI


**Windows**

```sh
sh -c "$(curl -sSfL https://release.solana.com/v1.9.13/install)"
```

#### 2. SPL CLI

```sh
cargo install spl-token-cli
```

#### 3. Installing the required packages 

```sh
sudo apt install libudev-dev
sudo apt install libssl-dev pkg-config
sudo apt install build-essential -y
```

#### 4. Solana Wallet

For this tutorial, we're going to use a Filesystem wallet. This is sufficient for testing, but not recommended for production purpose.

```sh
solana-keygen new 
```

#### 5. checking Solana Cluster configuration

Check your Solana Cluster configuration

```sh
solana config get
```
Setting the Solana Cluster to the required network (Testnet/Devnet/Mainnet)

```sh
solana config set --url https://api.devnet.solana.com
```

#### 5. SOL Balance

To check you SOL balance

```sh
solana balance
```

To get some testnet SOL

```
solana airdrop 1
```

### Creating SPL Tokens

First, create the token

```sh
spl-token create-token
```

Using the unique token identifier, we can create an account to store our balance data

```sh
spl-token create-account <token-identifier>
```

Once the account is created, we can mint some SPL tokens.

```sh
 spl-token mint <token-identifier> <token-amount>
```

To check the total supply of the token, use the following command

```sh
spl-token supply <token-identifier>
```

To check the balance of the token, use the following command

```sh
spl-token balance <token-identifier>
```

### Creating SPL NFTs

Creating a spl-token  (NFT decimals --> 0 , Fungible token decimals --> 9)

```sh
spl-token create-token --decimals 0
```

Using the unique token identifier, we can create an account to store our balance data

```sh
spl-token create-account <token-identifier>
```

Mint only one token into the account

```sh
spl-token mint <token-identifier> 1 <token-account>
```

Disable future minting

```sh
spl-token authorize <token-identifier> mint --disable
```

### Further Resources
- [Solana Docs](https://docs.solana.com/introduction)
- [SPL Token Program](https://spl.solana.com/token)
- [Metaplex Docs](https://docs.metaplex.com/candy-machine-v1/introduction)

