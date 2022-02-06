## Blockchain Toolbox Cheatsheet

This page is a blockchain toolbox cheatsheet to help you to have usefull command for most of development, testing and deployement tools used in blockchain.

- [Docker](#docker)
- [Hardhat](#hardhat)
- [Slither](#slither)
- [Ganache](#ganache)
- [Echidna](#echidna)
- [Mandicore](#mandicore)

- [Solidity](#solidity)
- [Vyper](#vyper)

## DOcker

Pull your image:
```bash
docker pull trailofbits/eth-security-toolbox
```
Run your docker and image:
```bash
docker run -it trailofbits/eth-security-toolbox
docker run -it -v "$PWD":/home/trufflecon trailofbits/eth-security-toolbox
```

## Hardhat

Deploying your contracts and run it:
```bash
npx hardhat run scripts/sample-script.js
```
Connecting a wallet or Dapp to Hardhat Network:
```bash
npx hardhat run scripts/sample-script.js --network localhost
```
Kill a Hardhat Node:
```bash
npx hardhat run scripts/sample-script.js --network localhost
```
