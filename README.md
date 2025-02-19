# solana-smart-contract-interaction 
The solana-smart-contract-interaction script provides a straightforward approach to interacting with smart contracts on the Solana blockchain. 
Command-Line Interface (CLI) and the @solana/web3.js library, this script allows users to deploy programs (smart contracts), send transactions, and query contract data. It serves as a practical foundation for developers and enthusiasts engaging with Solana's smart contract ecosystem.
#!/bin/bash

# Set your Solana node URL
SOLANA_NODE_URL="https://api.devnet.solana.com"

# Set your Solana wallet information
WALLET_PRIVATE_KEY="your_wallet_private_key_here"

# Deploy a smart contract (Rust program on Solana)
deploy_smart_contract() {
    solana-tokens create-account
    cargo build-bpf --manifest-path path/to/your/smart_contract/Cargo.toml
    solana deploy path/to/your/smart_contract/target/deploy/smart_contract.so
}

# Send a transaction to interact with the smart contract
send_transaction() {
    PROGRAM_ID="your_program_id_here"
    RECEIVER_ADDRESS="recipient_address_here"

    solana transfer \
        --from "$WALLET_PRIVATE_KEY" \
        --to "$RECEIVER_ADDRESS" \
        --lamports 1000000000  # Adjust the amount of lamports as needed

    solana call \
        --from "$WALLET_PRIVATE_KEY" \
        "$PROGRAM_ID" \
        your_instruction_here  # Replace with your specific instruction for the smart contract
}

# Query smart contract information
query_contract_info() {
    CONTRACT_ADDRESS="smart_contract_address_here"

    solana account "$CONTRACT_ADDRESS"
}

# Example Usage
deploy_smart_contract

# Wait for the contract deployment to be confirmed and grab the contract address

# Now, interact with the deployed smart contract
send_transaction

# Query smart contract information
query_contract_info

This script simplifies smart contract interactions on the Solana blockchain using Solana CLI and @solana/web3.js. Users can deploy Rust programs (smart contracts), send transactions, and query contract data. It serves as a practical tool for developers and enthusiasts engaging with Solana's smart contract ecosystem.
# Query smart contract information 
96845296
