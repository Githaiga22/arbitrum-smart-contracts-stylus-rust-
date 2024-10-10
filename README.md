# Arbitrum Smart Contracts Project
Welcome to the Arbitrum Smart Contracts Project! This repository serves as a comprehensive guide for building and deploying smart contracts on the Arbitrum network using the Stylus framework.

In this project, you will find step-by-step instructions on how to set up your development environment, manage dependencies, and deploy your smart contracts seamlessly. The goal is to empower beginners and enthusiasts alike to explore the world of blockchain development while using the Rust programming language.

Whether you are new to smart contracts or looking to enhance your skills, this project will provide you with the necessary tools and knowledge to successfully create and manage your own contracts on the Arbitrum network. Join us on this exciting journey into the decentralized future!

## Documentation of Setting Up and Deploying Smart Contracts on Arbitrum


### Overview

This documentation outlines the steps taken to set up the environment for developing and deploying smart contracts on the Arbitrum network using Docker, Rust, and the Stylus framework. It includes the necessary commands, explanations of each step, and the dependencies involved.

## 1. Installing Docker

```bash
sudo apt update
sudo apt install docker.io
```
***Explanation:***

   - sudo apt update: Updates the package lists for upgrades and new package installations.
   - sudo apt install docker.io: Installs Docker, allowing you to run applications in containers.

### Why Docker?
Docker is essential for creating isolated environments where your smart contracts can be built and tested without affecting your main system.

## 2. Setting Up Docker Group

**Command:**
```bash
sudo usermod -aG docker $USER
```
***Explanation:***
   - sudo usermod -aG docker $USER: Adds your user to the Docker group, enabling you to run Docker commands without sudo.

### Follow-Up Action:

   - Log Out and Log Back In: This refreshes your user group permissions.

## 3. Installing Rust
**Command:**
```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```
### Why Rust?

Rust is the programming language used to write the smart contracts. Its performance and memory safety features make it ideal for blockchain development.

## 4. Verifying Rust Installation
**Command:**
```bash
rustc --version
```
***Explanation:***

   - rustc --version: Checks the installed version of Rust, confirming that it was installed correctly.

## 5. Installing Cargo (Package Manager for Rust)

Cargo comes bundled with Rust. After Rust installation, ensure Cargo is set up.
***Verify Cargo Installation:***

```bash
cargo --version
```
**Explanation:**

   - cargo --version: Checks the installed version of Cargo to ensure it's ready for use.

## 6. Setting Up Your Stylus Project
**Create a New Project Directory:**
```bash
mkdir ~/Documents/stylus_project
cd ~/Documents/stylus_project
```
***Explanation:***

   - mkdir ~/Documents/stylus_project: Creates a new directory for your Stylus project.
   - cd ~/Documents/stylus_project: Changes the current directory to the project directory.

### Initialize a New Cargo Project:

```bash
cargo init
```
***Explanation:***

   - cargo init: Initializes a new Cargo project in the current directory, creating a Cargo.toml file for dependency management.

## 7. Creating rust-toolchain.toml
***Command:***

Create a file named rust-toolchain.toml in your project directory and specify the Rust version. Example content:
```bash
[toolchain]
channel = "1.80.0"  # Specify the exact version
```
**Explanation:**

   - rust-toolchain.toml: This file ensures that your project uses a specific version of Rust, promoting reproducibility.

## 8. Checking Your Project
**Command:**
```bash
cargo stylus check --endpoint https://sepolia-rollup.arbitrum.io/rpc
```
***Explanation:***

   - cargo stylus check: Validates your smart contract against the specified Arbitrum network endpoint, ensuring all requirements are met.

### Note:

If you encounter an error about the rust-toolchain.toml file, ensure you created it correctly in your project directory.
## 9. Deploying Your Project
**Command:**
```bash
cargo stylus deploy --private-key-path=<PRIVKEY_FILE_PATH> --endpoint https://sepolia-rollup.arbitrum.io/rpc
```
***Explanation:***

   - cargo stylus deploy: Deploys your compiled smart contract to the Arbitrum network. Replace <PRIVKEY_FILE_PATH> with the actual path to your private key file for authentication.

## 10. Other Useful Commands

  ### - Exporting ABI:
```bash
cargo stylus export-abi
```
   - Replaying a Transaction:

```bash
cargo stylus replay
```
   - Tracing a Transaction:
```bash
cargo stylus trace
```
***Explanation:***

These commands assist in managing your smart contracts by allowing you to export interfaces, debug transactions, and inspect execution flow.