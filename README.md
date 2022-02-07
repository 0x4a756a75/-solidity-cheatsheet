# Blockchain Toolbox Usefull Command

This page is a blockchain toolbox cheatsheet to help you to have usefull command for most of development, testing and deployement tools used in blockchain.

## Contributions are welcome!

Feel free to submit a pull request, with anything from small fixes to tools you'd like to add. If adding a new tool, **please add a brief description** that you think new developers would understand.

## Table of Contents

### Frameworks
- [Docker](#docker)
- [Hardhat](#hardhat)
- [Ganache](#ganache)

### Security
- [Slither](#slither)
- [Echidna](#echidna)
- [Mandicore](#mandicore)

### Storage
- [IPFS](#ipfs)
- [Web3.Storage](#web3.storage)

### Smart Contract Languages
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
Let's now install the Truffle and Web3.js plugins, as well as web3.js:
```bash
npm install --save-dev @nomiclabs/hardhat-truffle5 @nomiclabs/hardhat-web3 web3
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
### Web3.Storage

Create a folder for this quickstart project, and move into that folder:
```bash
mkdir web3-storage-quickstart
cd web3-storage-quickstart
```
Create a file called put-files.js and paste in the following code:
```bash
import process from 'process'
import minimist from 'minimist'
import { Web3Storage, getFilesFromPath } from 'web3.storage'

async function main () {
  const args = minimist(process.argv.slice(2))
  const token = args.token

  if (!token) {
    return console.error('A token is needed. You can create one on https://web3.storage')
  }

  if (args._.length < 1) {
    return console.error('Please supply the path to a file or directory')
  }

  const storage = new Web3Storage({ token })
  const files = []

  for (const path of args._) {
    const pathFiles = await getFilesFromPath(path)
    files.push(...pathFiles)
  }

  console.log(`Uploading ${files.length} files`)
  const cid = await storage.put(files)
  console.log('Content added with CID:', cid)
}

main()
```
Create another file called package.json and paste in the following code:
```bash
{
    "name": "web3-storage-quickstart",
    "version": "0.0.0",
    "private": true,
    "description": "Get started using web3.storage in Node.js",
    "type": "module",
    "scripts": {
        "test": "echo \"Error: no test specified\" && exit 1"
    },
    "dependencies": {
        "minimist": "^1.2.5",
        "web3.storage": "^3.1.0"
    },
    "author": "YOUR NAME",
    "license": "(Apache-2.0 AND MIT)"
}
```
Save both files, and then run npm install from your project folder:
```bash
npm install
```
