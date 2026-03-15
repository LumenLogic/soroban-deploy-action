#  Soroban Auto-Deploy GitHub Action

[![Stellar](https://img.shields.io/badge/Stellar-Ecosystem-blue)](https://stellar.org)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A zero-configuration GitHub Action to automatically compile and deploy your Soroban smart contracts to the Stellar network (Testnet, Futurenet, or Mainnet) directly from your CI/CD pipeline.

## The Problem
Deploying Soroban contracts currently requires developers to manually run shell scripts, manage CLI installations, and handle secret keys locally. This action abstracts the infrastructure, allowing teams to deploy safely and automatically on every push or release.

## Usage

Add this step to your GitHub Workflow (`.github/workflows/deploy.yml`):

```yaml
steps:
  - uses: actions/checkout@v4
  - name: Deploy to Stellar Testnet
    uses: LumenLogic/soroban-deploy-action@main
    with:
      network: 'testnet'
      source-secret-key: ${{ secrets.STELLAR_SECRET_KEY }}
```

## Inputs

| Name | Description | Required | Default |
| --- | --- | --- | --- |
| network | Target network (testnet, futurenet, mainnet) | Yes | testnet |
| source-secret-key | Secret key of the deploying account | Yes | N/A |
| manifest-path | Path to the contract's Cargo.toml | No | Cargo.toml |

## Roadmap

* [ ] Implement binary caching for faster Soroban CLI installation.
* [ ] Export the deployed Contract ID as a GitHub Action Output.
* [ ] Add support for deploying using soroban-cli identity files.

## Contributing

We welcome contributions! Please see CONTRIBUTING.md for guidelines. This repository is participating in Stellar Drips Wave 3.




