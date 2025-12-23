# Moonwell Cantilever (Built for Base)

Moonwell Cantilever is a browser-first Base reference repository that validates network identity (chainId 8453 / 84532) and exposes a strictly read-only view into balances, blocks, gas conditions, and ERC-20 token metadata with direct Basescan references.

---

## Tooling and dependencies

This repository intentionally references both Base and Coinbase open-source ecosystems:

- Coinbase Wallet SDK for EIP-1193 wallet access  
- OnchainKit references for Base-aligned primitives and account abstraction context  
- viem for typed, efficient, read-only RPC communication  
- Multiple Base and Coinbase GitHub repositories included via direct Git dependencies  

---

## Capabilities overview

Moonwell Cantilever provides a compact diagnostic surface for Base networks:

- Coinbase Wallet connection and chainId verification  
- ETH balance inspection for any address  
- Latest block snapshot (timestamp + gas fields)  
- RPC pulse check (chainId, block height, gas price)  
- ERC-20 read-only panel (name/symbol/decimals/totalSupply/balanceOf)  
- Basescan links for external verification  

No transactions are created, signed, or broadcast.

---

## Repository layout

- app.moonwell-cantilever.ts  
  Browser script that renders a minimal UI for wallet connection and read-only Base RPC queries.

- config/networks.json  
  Static Base network configuration (chainIds, RPC URLs, explorers).

- docs/validation.md  
  Internal checklist for testnet validation, explorer verification, and release hygiene.

- contracts/  
  Solidity contracts deployed to Base Sepolia for testnet validation:
  - control_contract.sol — is a Solidity contract that combines contract logic with access control
  - 
- package.json  
  Dependency manifest referencing Coinbase SDKs and multiple Base + Coinbase repositories.

- README.md  
  Technical documentation and deployment records.

---

## Base network context

Base Mainnet  
chainId (decimal): 8453  
Explorer: https://basescan.org  

Base Sepolia  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  

---

## Installation and execution

Install dependencies using Node.js.  
Serve the project with any modern frontend dev server and open it in a browser.

Expected result:
- Active network and chainId displayed  
- Wallet session details visible after connection  
- Read-only balance, block, gas, and ERC-20 data available  
- Basescan references printed for verification  

---

## License

MIT License

Copyright (c) 2025 YOUR_NAME

---

## Author contacts

GitHub: https://github.com/simmer-rulers

Email: simmer.rulers-0n@icloud.com 

---

## Testnet Deployment (Base Sepolia)

As part of pre-production validation, one or more contracts may be deployed to the Base Sepolia test network to confirm correct behavior and tooling compatibility.

Network: Base Sepolia  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  

Contract control_contract.sol address:  
0x3e06669ca0a5d997f5077a4ad7b35869dcfa7756

Deployment and verification:
- https://sepolia.basescan.org/address/0x3e06669ca0a5d997f5077a4ad7b35869dcfa7756
- https://sepolia.basescan.org/0x3e06669ca0a5d997f5077a4ad7b35869dcfa7756/0#code  

These testnet deployments provide a controlled environment for validating Base tooling, account abstraction flows, and read-only onchain interactions prior to Base Mainnet usage.
