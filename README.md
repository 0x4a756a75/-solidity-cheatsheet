# Blockchain Toolbox Usefull Command

This page is a blockchain toolbox cheatsheet to help you to have usefull command for most of development, testing and deployement tools used in blockchain.

## Contributions are welcome!

Feel free to submit a pull request, with anything from small fixes to tools you'd like to add. If adding a new tool, **please add a brief description** that you think new developers would understand.

## Table of Contents
- [Docker](#docker)
- [Hardhat](#hardhat)
- [IPFS](#ipfs)
- [Slither](#slither)
- [Ganache](#ganache)
- [Echidna](#echidna)
- [Mandicore](#mandicore)
- [Solidity](#solidity)
- [Vyper](#vyper)

## Tools
### Docker

Pull your image:
```bash
docker pull trailofbits/eth-security-toolbox
```
Run your docker and image:
```bash
docker run -it trailofbits/eth-security-toolbox
docker run -it -v "$PWD":/home/trufflecon trailofbits/eth-security-toolbox
```

### Hardhat

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
ps aux | grep node
killall -9 node
```

### IPFS

Download the macOS binary from dist.ipfs.io:
```bash
curl -O https://dist.ipfs.io/go-ipfs/v0.11.0/go-ipfs_v0.11.0_darwin-amd64.tar.gz
```
Unzip the file::
```bash
tar -xvzf go-ipfs_v0.11.0_darwin-amd64.tar.gz
```
Move into the go-ipfs folder and run the install script::
```bash
cd go-ipfs
sudo  ./install.sh
```
Check that IPFS installed:
```bash
ipfs --version
```
