# NFT App

This project is an NFT (Non-Fungible Token) application developed using Foundry, a fast and portable toolkit for Ethereum application development written in Rust. The application includes functionalities for deploying and interacting with NFT smart contracts.

## Features

- **NFT Deployment**: Deploys ERC721-compliant NFT contracts to the Ethereum blockchain.
- **Minting**: Allows users to mint new NFTs.
- **Mood NFTs**: Implements NFTs with on-chain SVG images that can change mood.

## Getting Started

### Prerequisites

Ensure you have the following installed:

- [Foundry](https://book.getfoundry.sh/): Ethereum development toolkit.
- [Git](https://git-scm.com/): Version control system.

### Installation

1. **Clone the repository**:

   ```bash
   git clone https://github.com/andrei2308/Nft-app.git
   cd Nft-app
   ```

2. **Install dependencies**:

   ```bash
   forge install
   ```

### Configuration

Create a `.env` file in the root directory and add the following variables:

```env
SEPOLIA_RPC_URL=<your_sepolia_rpc_url>
PRIVATE_KEY=<your_private_key>
ETHERSCAN_API_KEY=<your_etherscan_api_key>
```

Replace `<your_sepolia_rpc_url>`, `<your_private_key>`, and `<your_etherscan_api_key>` with your actual credentials.

## Usage

### Building the Project

Compile the smart contracts:

```bash
forge build
```

### Running Tests

Execute the test suite:

```bash
forge test
```

### Deploying Contracts

1. **Start a local Ethereum node**:

   ```bash
   anvil
   ```

2. **Deploy the Basic NFT contract**:

   ```bash
   forge script script/DeployBasicNft.s.sol:DeployBasicNft --rpc-url http://localhost:8545 --private-key $PRIVATE_KEY --broadcast
   ```

3. **Deploy the Mood NFT contract**:

   ```bash
   forge script script/DeployMoodNft.s.sol:DeployMoodNft --rpc-url http://localhost:8545 --private-key $PRIVATE_KEY --broadcast
   ```

### Minting NFTs

- **Mint a Basic NFT**:

  ```bash
  forge script script/Interactions.s.sol:MintBasicNft --rpc-url http://localhost:8545 --private-key $PRIVATE_KEY --broadcast
  ```

- **Mint a Mood NFT**:

  ```bash
  forge script script/Interactions.s.sol:MintMoodNft --rpc-url http://localhost:8545 --private-key $PRIVATE_KEY --broadcast
  ```

### Interacting with Mood NFTs

- **Flip the mood of a Mood NFT**:

  ```bash
  forge script script/Interactions.s.sol:FlipMoodNft --rpc-url http://localhost:8545 --private-key $PRIVATE_KEY --broadcast
  ```

## Project Structure

```plaintext
Nft-app/
├── .github/
│   └── workflows/
├── img/
├── lib/
├── script/
├── src/
├── test/
├── .gitignore
├── .gitmodules
├── LICENSE
├── README.md
└── foundry.toml
```

- **`script/`**: Contains deployment and interaction scripts.
- **`src/`**: Houses the smart contract source code.
- **`test/`**: Includes test files for the contracts.

## Acknowledgements

This project draws inspiration from the [foundry-nft-cu](https://github.com/Cyfrin/foundry-nft-cu) repository.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

For more information on Foundry, refer to the [Foundry Book](https://book.getfoundry.sh/). 
