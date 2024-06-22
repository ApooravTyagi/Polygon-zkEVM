# Polygon-zkEVM

## Overview
This project involves creating, compiling, and deploying a zero-knowledge proof circuit using the hardhat-circom template. The objective is to implement a correct `circuit.circom`, compile it, generate a proof, deploy a verifier on Sepolia or Mumbai Testnet, and verify the proof on-chain.

## Tools Used
- **Hardhat-Circom Template**: Used for writing and compiling the circuit, generating proofs, and creating a verifier contract.
- **Circom**: A tool used for designing and compiling zero-knowledge circuits.
- **Sepolia/Mumbai Testnet**: Blockchain networks where the verifier contract will be deployed.

## Project Rubric
To successfully complete the Final Challenge, your project should meet the following criteria:

1. **Write a Correct `circuit.circom` Implementation**:
   - Design a circuit in `circuit.circom` that correctly implements the required functionality.

2. **Compile the Circuit**:
   - Compile the circuit to generate necessary intermediaries like R1CS, WASM, and Zkey files.

3. **Generate a Proof**:
   - Use inputs \( A = 0 \) and \( B = 1 \) to generate a proof for the compiled circuit.

4. **Deploy a Solidity Verifier**:
   - Deploy the verifier contract on Sepolia or Mumbai Testnet.

5. **Verify the Proof On-Chain**:
   - Call the `verifyProof()` method on the deployed verifier contract and ensure the output is `true`.

## Steps to Follow

### 1. Write the Circuit
Create the `circuit.circom` file and implement the logic for your zero-knowledge proof circuit. Ensure that the circuit is correct and adheres to the specifications of your project.

### 2. Compile the Circuit
Compile the circuit using the Hardhat-Circom tools to generate intermediaries:
```bash
npx hardhat circom:compile
```
This command will generate the R1CS, WASM, and Zkey files necessary for proof generation and verification.

### 3. Generate the Proof
Generate a proof using the inputs \( A = 0 \) and \( B = 1 \). Use the following command:
```bash
npx hardhat circom:generate-proof --input '{"A":0,"B":1}'
```
This will create the proof and public signals files.

### 4. Deploy the Verifier Contract
Deploy the Solidity verifier contract to Sepolia or Mumbai Testnet. You can use the following command to deploy:
```bash
npx hardhat run scripts/deploy.js --network <network-name>
```
Replace `<network-name>` with either `sepolia` or `mumbai` depending on your chosen testnet.

### 5. Verify the Proof On-Chain
Call the `verifyProof()` method on the deployed verifier contract and assert that the output is `true`. You can use the following script to call the method:
Replace `<verifier-contract-address>` with the actual address of your deployed verifier contract and ensure the paths to `proof.json` and `publicSignals.json` are correct.

## Conclusion
Follow the steps outlined in this README to implement, compile, and deploy your zero-knowledge proof circuit. Ensure that all criteria in the project rubric are met to successfully complete the Final Challenge. Happy coding!
