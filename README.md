# Random Avatars Interface for Blockchain Academy Solidity Course certification

## Table of Contents
* [Overview](#Overview)
* [Instructions to run this project](#Instructions-to-run-this-project)
    * [Installing Node.js and NPM](#Installing-Node.js-and-NPM)
    * [Installing dependencies](#Installing-dependencies)
    * [Running the project](#Running-the-project)
    * [Updating the ABI](#updating-the-abi)
* [Deploying website to IPFS with Fleek](#deploying-website-to-ipfs-with-fleek)
* [References](#References)

## Overview
This is the final project for the Blockchain Academy Solidity Course. In this project we mint NFTs using the ERC721 standard using the [Multiavatar](https://api.multiavatar.com/) avatar library for our images, we also integrate Chainlink by using its Chainlink VRF (Verifiable Randomness Function) to get a non-deterministic random number that will determine the avatar that the user mints. We also create a UI for the user for minting the NFT and seeing all minted NFTs. Everything runs on the Rinkeby test network.

This is a simple UI that allows the user to mint ERC721 tokens and view a gallery with all the minted NFTs, with the option to search by owner address. This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

The project is divided in two repositories.
1. The smart contract for the minting of NFTs. (Repository available [here](https://github.com/georgetegral/RandomAvatars))
2. The dApp using React.js, built for interaction with the smart contract in a user-friendly way. (This repository)

## Instructions to run this project
To run this project we will use React.js, which needs you to install Node.js and NPM. 

### Installing Node.js and NPM
Use the following link to install Node.js in your computer: https://nodejs.org/en/download/, follow the instructions in the website.

At the end, you can verify that the installation was correct by running the following commands

```bash
node -v
npm -v
```

### Installing dependencies
To install the necesary dependencies to run this project, run the following command:

```bash
npm install
```

### Running the project
In the project directory, you can run:

```bash
npm start
```

This command runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

The page will reload when you make changes.

### Updating the ABI
The project will run with my smart contract, but if you want to use your own, please follow the steps to create your smart contract for the minting of NFTs (Repository available [here](https://github.com/georgetegral/RandomAvatars)). After you have done that, follow the next steps.

Copy the ABI of your smart contract, assuming you have verified it on [Rinkeby Etherscan](https://rinkeby.etherscan.io/), navigate to the "Contract" section, and then go to "Code", if you scroll down, you will see the section "Contract ABI", you have to copy it, click the button next to the option "Export ABI".

You will have to paste it in the [abi.js file](src/config/web3/artifacts/abi.js) alongside the address of your contract. You will replace these values:

```javascript
const RandomAvatarsInterface = {
    address: {
        4: 'Your Contract Address here'
    },
    abi: [{"Your ABI Here"}]
}
```

The "4" means that this contract will only work for the Rinkeby test network, but feel free to add it to any network you so desire.

## Deploying website to IPFS with Fleek
To deploy our website we will be using decentralized options instead of a centralized hosting, we will be using Fleek to deploy our website. You will also need to upload your repository to Github.

Create a new account at [Fleek.co](https://app.fleek.co/), and follow this instructions:
1. Click on "Add New Site"
2. Click on "Connect with Github"
3. Connect your Fleek account to Github
4. Select your RandomAvatarsInterface repository
5. In Hosting Services, select "IPFS"
6. In "Basic Building Settings", leave everything as-is unless you've made some special configuration.
7. Click on "Deploy site"

The deployment will start, and in a few minutes you will have your dApp running on IPFS.

## References
- [Multiavatar](https://api.multiavatar.com/)
- [Create React App](https://github.com/facebook/create-react-app)
- [Node.js](https://nodejs.org/en/download/)
- [Rinkeby Etherscan](https://rinkeby.etherscan.io/)
- [IPFS](https://ipfs.io/)
- [Fleek](https://app.fleek.co/)
