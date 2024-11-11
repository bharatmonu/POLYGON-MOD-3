# Custom Zero-Knowledge Circuit Overview
This document outlines a bespoke zero-knowledge circuit implemented through the Circom language. The circuit, denoted as customCircuit, showcases the construction of logic gates and their interconnections to form a unique computation. The resulting circuit is designed for generating zero-knowledge proofs for specific computations while maintaining the confidentiality of input values.

### Input Signals: The circuit incorporates two input signals, namely A and B, serving as operands for the computation.
### Logic Gates: Three distinct logic gates—AND, NOT, and OR—are utilized in the circuit. Each gate is defined as an independent template.
### Intermediate Signals: Two intermediate signals, X and Y, are introduced as outputs from the AND and NOT gates, respectively.
### Output: The final output signal, Q, is computed through the OR gate, employing inputs from the intermediate signals.
## Circuit Templates
The customCircuit template embodies the primary circuit, defining input signals A and B, intermediate signals X and Y, and the ultimate output signal Q. The circuit entails the following stages:

- An AND gate (andG) calculates the logical AND of inputs A and B, storing the result in the intermediate signal X.
- A NOT gate (notG) computes the logical NOT of input B, and its output is stored in the intermediate signal Y.
- An OR gate (orG) computes the logical OR of the intermediate signals X and Y, yielding the final output signal Q.
- AND, NOT, and OR Templates
These templates articulate the logic governing the AND, NOT, and OR gates, respectively. Each gate processes input signals to generate an output signal based on the defined logic.

## How to Use

1. Install the required dependencies by running the command:
   ```
   npm install
   ```

2. Compile the circuit using the command:
   ```
   npx hardhat circom
   ```
   This will generate circuit intermediaries and the necessary Solidity verifier contracts.

3. Generate a proof and deploy a verifier contract using the provided script:
   ```
   npx hardhat run scripts/deploy.ts
   ```
   This script performs the following tasks:
   - Deploys the verifier contract.
   - Generates a proof using circuit intermediaries.
   - Generates calldata for verification.
   - Calls `verifyProof()` on the verifier contract with calldata for proof verification.




## License

This project is licensed under the MIT License - see the LICENSE.md file for details

