# M21-KaseiCoin 
Minting tokens for a CrowdSale  

![KaseiCoinCrowdsale-Title](./Images/KAI_Crowdsale_Title-2022-08-09162204.png) 

*"Leading a project for a monetary system to develop a new cryptocurrency called KaseiCoin for a new Mars colony."* 


## Background 

After waiting for years and passing several tests, being selected by the Martian Aerospace Agency a new monetary system needs to be implemented for the first human colony on Mars. As a prominent fintech professional, I was chosen to lead a project to develop a monetary system for the new Mars colony. The decision is made to base this new monetary system on blockchain technology, and to define a new cryptocurrency called KaseiCoin. (“Kasei” means “Mars” in Japanese.)

KaseiCoin will be a fungible token that is ERC-20 compliant. The crowdsale contract created will manage the entire crowdsale process, allowing users to send ether to the contract and in return receive KAI, or KaseiCoin tokens. The contract will mint the tokens automatically and distribute them to buyers in one transaction. It will allow people who are moving to Mars to convert their earthling money to KaseiCoin.

---
#
## Evaluation Evidence

In the completed Solidity KaseiCoin Crowdsale smart contract a folder named `Evaluation_Evidence` contains images. These images are confirms of performance in a real-world, pre-production test of a KaseiCoin crowdsale. The transactions are designed to test the `KaseiCoin.sol`, `KaseiCoinCrowdsale.sol` and `KaseiCoinCrowdsaleDeployer` functionality in the JavaScript VM, as expected. In order to do so, deployment of the crowdsale is to a local blockchain using Remix, MetaMask, and Ganache.

After deploying the contract, it’s time to test its functionality! After each step, capture a screenshot of the execution, and then save it in a folder named `Evaluation_Evidence`. *(5 tokens were previously purchased by owner account 3 prior to the following screenshots for testing.) 

To interact with your compiled & deployed smart contract, complete the following steps. 
 

1. Create & compile the `KaseiCoin.sol` contract using compiler version 0.5.5; take a screenshot of the successful compilation of the contract, and add it to the Evaluation_Evidence section: 

    ![KaseiC-Compiled](./Evaluation_Evidence/1_KaseiC_Compiled-2022-08-09170347.png) 

2. Create, define & compile the `KaseiCoinCrowdsale.sol` contract inheriting OpenZeppelin contracts `Crowdsale` & `MintedCrowdsale`; check for any errors and debug as needed; compile the contract using compiler version 0.5.5; take a screenshot of the successful compilation of the contract, and add it to the Evaluation_Evidence section. 

    ![KaseiCoinCrowdsale](./Evaluation_Evidence/2_KCCrowdsale_Compiled-2022-08-09182256.png) 

3. Create the `KaseiCoinCrowdsaleDeployer` and add the `KaseiCoin` and `KaseiCoinCrowdsale`  contract addresses; add the `name`, `symbol`, and `wallet` parameters to the `KaseiCoinCrowdsaleDeployer`; renounce its minter role; compile the contract using compiler version 0.5.5; check for any errors and debug as needed; take a screenshot of the successful compilation of the contract, and add it to the Evaluation_Evidence section: 

    ![KaseiCoinCrowdsaleDeployer](./Evaluation_Evidence/3_KCCrwdSaleDeplyr_Compld-2022-08-09164602.png)

4. Deploy the KAICrowdsale and KAIToken in transaction activities to the Local Blockchain

- The KAICrowdSaleDeployer contract with KAICrowdSale & KAIToken addresses for the blockchain with Remix, MetaMask, and Granache:

    ![KAICrwdSaleAddr](./Evaluation_Evidence/4_KAICrwdSaleAddr-2022-08-14014851.png)  

- The KaseiCoinCrowdSale contract to buy tokens for beneficiaries and the KAICoin Minter:  

    ![KAICrwdSaleContract](./Evaluation_Evidence/5_KAICrwdSContrct-2022-08-14015052.png)

- Test of account 4 to buy 5 KAI from the crowdsale for account 4 and check the balance for the account:

    ![A4Buy5KAI_forA4](./Evaluation_Evidence/6_A4Buy5KAI2022-08-14015434.png)  

- Confirmation of purchase of 5 KAI for account 4:

    ![A4Confirmof5KAIpurchase](./Evaluation_Evidence/7_A4BuyConfirm2022-08-14015622.png) 

- Ether balance of purchase of 7 KAI for beneficiary account 5 by account 4, with total `weiRaised`: 

    ![A4EthBalaftr7KAIpurchase](./Evaluation_Evidence/8_KAICrwdSaleA4BalFunds2022-08-14021214.png)

    ![A5KAITokenBalance](./Evaluation_Evidence/9_A4tfr7KAItoA52022-08-14021400.png)

- After purchasing tokens with test accounts, view the `totalSupply` of minted tokens and the amount of `weiRaised` by the crowdsale: *(total supply in owner wallet in `KaseiCoin` contract matches total `weiRaised` in `KaseiCoinCrowdsale` contract above with account 4, after 7 KAI purchase.)
    ![A5KAITokenBalance](./Evaluation_Evidence/10_KAICoinTtlSpplyRaisd-2022-08-14183538.png)

5. ### *Optional:* Extend the Crowdsale Contract by Using OpenZeppelin. extend the crowdsale contract to enhance its functionality. To do so, you will use the following OpenZeppelin contracts:  

- `CappedCrowdsale`: This contract allows you to cap the total amount of ether that may be raised during your crowdsale.:

    ![CappedCrowdsale](./Evaluation_Evidence/) 

- `TimedCrowdsale`: This contract allows you to set a time limit for your crowdsale by adding an opening time and a closing time: 

    ![TimedCrowdsale](./Evaluation_Evidence/)

- `RefundablePostDeliveryCrowdsale`: Every time you launch a crowdsale, you set a goal amount of ether to raise. If the goal is not reached, it is common practice to refund your investors. This contract adds this capability to a crowdsale: 
 
    ![RefundablePostDeliveryCrowdsale](./Evaluation_Evidence/) 


---
#
## Technologies

The software program was built using 'Remix 0.25.1' IDE in a web app. The Remix IDE is an open-source application for developing, deploying, and administering smart contracts that run in Ethereum-based blockchains development environment. 

The programming language was developed in 'Solidity 0.5.0' to create a smart contract and code that works on the Ethereum blockchain. The OpenZeppelin library provides a variety of contracts that are related to the ERC-20 token standard. The `ERC-20` standard defines some mandatory functions for a fungible-token contract and provides critical functionality for any `ERC-20` token smart contract. The `ERC20` contract uses the SafeMath library, and the ERC20 `_transfer` function is coded to prevent integer underflow error. 

Using 'Granache 2.5.4' app allows a quick setup of a local blockchain in a development environment. 'MetaMask 10.18.0' is a is a digital wallet for the digital currency blockchain. Together they operates in an isolated decentralized environment mimicking the consensus engine of the Ethereum blockchain to perform a `KaseiCoinCrowdsale` to mint coins for an ICO. 
 

---

## Installation Guide

The Remix IDE is an open source application for developing, deploying, and administering smart contracts that run in Ethereum-based blockchains. First navigate to use the web version of this IDE, you don’t need to install any software for this module. Open your browser to the [Remix-Docs website](https://remix-ide.readthedocs.io/en/latest/) or use the links below. The OpenZeppelin contract library `ERC20`; `ERC20Detailed`; `Crowdsale` and `MintedCrowdsale` are from the [OpenZeppelin documentationImport](https://github.com/OpenZeppelin/openzeppelin-contracts).


1. [Remix Online IDE](https://remix.ethereum.org) 
* Supported browsers: Firefox, Chrome, Brave. We do not support Remix’s use on tablets or mobile devices. 

2. [Remix Desktop IDE](https://github.com/ethereum/remix-desktop/releases) 

3. Follow the instructions on the [MetaMask Download page](https://metamask.io/download) to install MetaMask digital wallet in your web browser: 

Import to inherit the OpenZeppelin the `ERC20`; `ERC20Detailed`; `Crowdsale` and `MintedCrowdsale` contracts in the appropiate program applications:
```
import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/release-v2.5.0/contracts/token/ERC20/ERC20.sol";
import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/release-v2.5.0/contracts/token/ERC20/ERC20Detailed.sol"; 
import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/release-v2.5.0/contracts/token/ERC20/ERC20Mintable.sol"; 
import "./ArcadeTokenMintable.sol";
import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/release-v2.5.0/contracts/crowdsale/Crowdsale.sol";
import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/release-v2.5.0/contracts/crowdsale/emission/MintedCrowdsale.sol";
remix 
```


---

## Usage

This program is run from `KaseiCoin.sol` and `KaseiCoinCrowdsale.sol` to deploy smart contract transactions on the blockchain. `KaseiCoin.sol` functions to mint digital coins for crytpocurrency circulation of Kaseicoin (`KAI`), while `KaseiCoinCrowdsale.sol`deploys and manages the entire crowdsale process for users to exchange `ETH` for `KAI` from their digital wallets. It is launched from the Remix 0.25.1 using Solidity language for the **.sol** file to build the `KaseiCoinCrowdsale.sol`. The 'Remix' GUI on the left side of the web page utilizes the program code to run the Smartcontracts on Ethereum blockchain transactions. It is deployed in 'Injected Provider- MetaMask' JavaScript Environment utilizing the ‘Solidity’ compiler, deployer and tools. 

Once the program code runs it is compiled, deployed and evaluated for approval, and `KaseiCoinCrowdsale` will mint digital coins for the Mars colony economy. Complete the following steps to interact with compiling, deploying and holding a `KaseiCoinCrowdsale` to mint digital coins for the Mars colony: 

### 1. Compile and Deploy Your Contract in ReMix. 

1.	In the Remix IDE, select `KaseiCoin.sol` tab; then navigate to the left "Deploy & Run Transactions" pane, and make sure that "Injected Provider- Metamask" wallet is selected for the environment. 

- Click the Deploy button to deploy your smart contract, and then confirm that it successfully deployed.

- The terminal can be used to check transactions details and start debugging. 

- Once deployed, test for functionality with Ganache provided accounts minting Kaseicoins, receive `KAI` balances for accounts and `totalSupply`. 

2. Select `KaseiCoinCrowdsale.sol` tab; then navigate to the left "Deploy & Run Transactions" pane, and make sure that "Injected Provider- Metamask" wallet is selected for the environment. Repeat the steps above for `KaseiCoin.sol`. 

- upon deployment of `KaseiCoinCrowdsale.sol`   click on the left arrow to open the functions for the contract.  


### 2. Interact with Your Deployed Smart Contract. 

1.	After deployment of `KaseiCoin.sol` in ReMix navigate to `KaseiCoinCrowdsale.sol`, and set the 'Environment' to 'Injected Provider- Metamask'. MetaMask should open for deployment. Open 'Granache' and select Account Adress 'Private Key' for the owner account and copy the Private Key. In MetaMask select 'Import Account' and paste the key in the appropiate box. Repeat to open a 2nd account, and 3rd if you prefer. Select the 1st account imported in MetaMask. The account should appear in Remix under the 'Account' drop-box field. Now the contract addresses in ReMix should be ready for connection with 'MetaMask' and 'Granache' accounts.   

2.	Test the deposit functionality of the smart contracts by sending selected amounts of `ether` to buy new `KAI` tokens. After each transaction to `buyTokens`, check the account balances in Metamask to match the tranaction in `KaseiCoinCrowdsale` functions and the Granache accounts 'Transactions' and 'Blocks' on the blockchain to verify that the funds were added to the 'beneficiary account. 

- Reminder that `ether` is counted in `wei` in the contract accounts. (use the website [Ethereum Unit Converter](https://eth-converter.com/) to do the conversion.) 


```
Solidity 

KaseiCoin.sol
KaseiCoinCrowdsale.sol
```
 
---

## Contributors

*Provided to you by digi-Borg FinTek*, 
Dana Hayes: nydane1@gmail.com


---

## License  

Columbia U. Engineering 
--
[BSD 2-Clause LicenseCopyright (c) 2022, digi-Borg
All rights reserved.](/LICENSE)
