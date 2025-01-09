# ❇ Solana SDK Rust - AIRDROP
A Rust Project that acts as a Prerequisite to enter the Turbin3 Program Q1 2025 Cohort. It has scripts that generates keypairs, requests airdrop, transfer sol and interacts with a PDA program on devnet.

> **Onchain Transaction Link:** 
[`https://explorer.solana.com/tx/2yHkCHqW9sTn5Gm2TzAugdhC8KvH2RXF1bNx8yR2KBhgTFDxpCxmw94Bs6E7MvuWwgjJT6RioLp8UULgMFsFgBkp?cluster=devnet`](https://explorer.solana.com/tx/2yHkCHqW9sTn5Gm2TzAugdhC8KvH2RXF1bNx8yR2KBhgTFDxpCxmw94Bs6E7MvuWwgjJT6RioLp8UULgMFsFgBkp?cluster=devnet)

## Prerequisites
1. Cargo Installed
2. Solana CLI installed
3. Rust Installed

## Tech stack used
- Rust 
- cargo (as the package manager)

## Project Structure

```plaintext
├─ src/
├── lib.rs                  // Handles Logic and tests to airdrop, generate keypairs, transfer_sol and enroll
├─ programs/
├──── mod.rs                 // Exposes turbin3_prereq API
├──── turbin3_prereq.rs      // Defines the Program IDL with the Instructions and arguments
├─ dev-wallet.json          // A secret key used to ask for airdrop
├─ Turbin3-wallet.json      // A Seckret key for a solana wallet used to sign transactions
```


## Setup
- Clone the repo by running `git clone https://github.com/HermanCeaser/turbin3-preq-two.git`
- Change the directory to `turbin3-preq-two` folder on your machine `cd turbin3-preq-two`
- Build the dependencies and package by running `cargo build`
- Create a file called `dev-wallet.json`
- Create a file called `turbin3-wallet.json` and paste your private key pair for your dev wallet

## RUN

- Run `cargo test --package airdrop-rust --lib -- tests::keygen --exact --show-output`
- Copy the secret key from the output and paste it in the `dev-wallet.json` then save. 
  The contents should be a binary array similar to 
  ```json
  [15,71,221,67,2,87,32,15,251,184,9,12,215,157,200,94,85,5,191,215,157,230,152,73,107,215,129,92,109,175,117,102,120,119,241,244,89]
  ```
- Then run the airdop command by typing  `cargo test --package airdrop-rust --lib -- tests::airdrop --exact --show-output`
- Check the transaction hash on the explorer by clicking the link to see your account balance

- Run `cargo test --package airdrop-rust --lib -- tests::transfer --exact --show-output` to transfer some SOL to a your public devnet wallet address and view the transaction on blockchain. Change the Public address in line 89 of [`transfer_sol` function](./src/lib.rs) to your wallet public address if you want to receive the SOL

- Finally run `cargo test --package airdrop-rust --lib -- tests::enroll --exact --show-output` to interact with an onchain program that WBA created. Change the github username in line 143 of [`enroll` function](./src/lib.rs) to your username if you want to sign this transaction



## Contributing
- Fork the repository 
- Create a feature branch and make a pull request with your feature or bugfix

## Happy Hacking!
