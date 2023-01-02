# Solidity smart contract deployment using Hardhat example script

This project is an example of the usage of Hardhat for Solidity smart contract deployment on Ethereum-compatible (EVM) blockchains. It comes with an example smart contract.

## Installation

These are installation instructions for Debian 11.x:

```console
apt update
apt -y upgrade
apt -y install git yarn
git clone https://github.com/libersoft-org/solidity-example.git
cd solidity-example
yarn install
```

## Configuration and deployment

1. Edit a new file called ".secret" and put there a wallet mnemonic phrase (24 words) - you need to have some gas on this wallet to be able to deploy the smart contract.
2. Register on etherscan.io / bscscan.com / polygonscan.com or other etherscan-compatible block explorer and create your new API keys. This needs to be done to have your smart contract verified and made public on block explorer.
3. Edit .apikey_* files and add your API keys on the first line of each file (* means block explorer name, e.g.: etherscan, polygonscan, bscscan ...)
4. Edit the ./scripts/deploy.js file and set your smart contract variables
5. Run the deploy script:

```console
./deploy_hardhat.sh
```

## Interact with your smart contract:

If you'd like to interact with your smart contract, you can do it from block explorer or from the command line using:

```console
npx hardhat console --network [NETWORK_NAME]
> var Contract = await ethers.getContractFactory('[CONTRACT_NAME]');
> var contract = await Contract.attach('[CONTRACT_ADDRESS]');

For example:

```console
npx hardhat console --network polygonTestnet
> var Contract = await ethers.getContractFactory('Sample');
> var contract = await Contract.attach('0x1234567890123456789012345678901234567890');
```

## License:
This software is open source released under [**Unlicense**](./LICENSE)
