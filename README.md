# Blockchain Naming Service (BNS)

A decentralized naming service built on Ethereum, allowing users to
register and manage human-readable domain names on the blockchain. This
project is inspired by the Ethereum Name Service (ENS) and is
implemented in Solidity using the Hardhat development framework.

## 📌 Features

-   Domain Registration -- Users can register domain names with a
    specific TLD.

-   Ownership Management -- Retrieve the owner of a registered domain.

-   Custom TLD -- The TLD (e.g., .ninja) can be set at deployment.

-   Payments in ETH -- Registration fees are paid directly to the smart
    contract.

## 🛠 Tech Stack

-   Solidity -- Smart contract programming

-   Hardhat -- Ethereum development environment

-   Ethers.js -- Interacting with Ethereum blockchain

-   Node.js -- Script execution

## 📂 Project Structure

.\
├── contracts\
│ ├── Domains.sol \# Core naming service contract\
│ ├── StringUtils.sol \# Utility library for string operations\
├── scripts\
│ ├── deploy.js \# Deploys the Lock contract (example)\
│ ├── run.js \# Deploys and tests the Domains contract\
├── README.md \# Project documentation

## 🚀 Getting Started

### 1️⃣ Install Dependencies

npm install

### 2️⃣ Compile Contracts

npx hardhat compile

### 3️⃣ Deploy Contracts

Run the deployment script for the Domains contract:

npx hardhat run scripts/run.js \--network localhost

Or deploy to a testnet:

npx hardhat run scripts/run.js \--network goerli

### 4️⃣ Interact with the Contract

The provided run.js script:\
- Deploys the contract with the \`.ninja\` TLD.\
- Registers a sample domain (\`mortal.ninja\`).\
- Fetches and displays the domain owner.\
- Prints the contract's ETH balance.\
Example output:\
Contract deployed to: 0x1234\...\
DomainContract Registration completed!\
Owner of domain mortal: 0xabcd\...\
Contract balance: 0.1

## 📜 Example Code

Register a Domain:

let txn = await domainContract.register(\"mortal\", { value:
hre.ethers.parseEther(\'0.1\') });\
await txn.wait();

Get Domain Owner:

const address = await domainContract.getAddress(\"mortal\");\
console.log(\"Owner:\", address);

## ⚠️ Notes

-   Ensure you have ETH in your wallet when registering domains.

-   The price logic for domain registration can be modified in
    Domains.sol.

-   Always test on a local network or testnet before deploying to
    mainnet.

## 📄 License

This project is licensed under the MIT License.
