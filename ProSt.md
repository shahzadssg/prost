
### Provably Secure Homomorphic Steganography (ProSt) Implementation

This repository contains the result of the Python implementation of **Provably Secure Homomorphic Steganography (ProSt)**, an innovative approach that merges steganography with homomorphic computation. ProSt enables secure computations on data hidden within images, ensuring both the data's location and content remain secret from an honest-but-curious adversary while still allowing meaningful operations on the concealed information.

#### Key Features
- **Steganographic Embedding**: Embeds secret bits into cover images using least significant bit (LSB) substitution at a randomly selected secret position.
- **Homomorphic Computation**: Evaluates Boolean circuits on hidden data using reversible Fredkin gates, maintaining security and bit distribution during computation.
- **Circuit Obfuscation**: Hides the computation's purpose by renaming wires and adding dummy components to the circuit.
- **Randomized Gate Execution**: Executes gates in a randomized topological order to obscure the circuit structure.
- **Security**: Ensures an adversary gains negligible advantage in uncovering the secret, as supported by the accompanying research paper.

#### Workflow
1. **Circuit Specification**: Define a Boolean circuit with a simple syntax (e.g., inputs, gates like FREDKIN, and outputs).
2. **Obfuscation**: Rename wires and insert dummy gates/ancillaries to disguise the circuit.
3. **Secret Position Selection**: Choose a secret position in the image for embedding the bits (known only to the sender, Alice).
4. **Embedding**: Insert input bits and ancillary values into cover images at the secret position.
5. **Homomorphic Computation**: An untrusted server (Eve) processes the circuit pixel-wise across all images, applying gates in random order without knowing the secret position.
6. **Extraction**: Retrieve the computation result from the output image at the secret position.

This results showcases ProSt as a tool for privacy-preserving computations in untrusted settings, such as cloud environments, by combining the stealth of steganography with the flexibility of homomorphic operations.