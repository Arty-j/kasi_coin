# Application

## Challenge: Martian Token Crowdsale

This project will create a fungible token that is ERC-20 compliant and that will be minted by using a `Crowdsale` contract from the OpenZeppelin Solidity library.

The crowdsale contract will manage the entire crowdsale process, allowing users to send ether to the contract and in return receive KAI, or KaseiCoin tokens. The contract will mint the tokens automatically and distribute them to buyers in one transaction.

### Instructions

The steps for this project are divided into the following sections:

1. Create the KaseiCoin Token Contract

2. Create the KaseiCoin Crowdsale Contract

3. Create the KaseiCoin Deployer Contract

4. Deploy the Crowdsale to a Local Blockchain

5. Optional: Extend the Crowdsale Contract by Using OpenZeppelin

### Create the KaseiCoin Token Contract

A smart contract that defines KaseiCoin as an ERC-20 token. 

1. Import the provided `KaseiCoin.sol` starter file into the Remix IDE.

2. Import the following contracts from the OpenZeppelin library:

    * `ERC20`

    * `ERC20Detailed`

    * `ERC20Mintable`

3. Define a contract for the KaseiCoin token called `KaseiCoin`, and have the contract inherit the three contracts that you just imported from OpenZeppelin.

4. Inside the `KaseiCoin` contract, add a constructor with the following parameters: `name`, `symbol`, and `initial_supply`.

5. Then, as part of the constructor definition, add a call to the `ERC20Detailed` contract’s constructor, passing the parameters `name`, `symbol`, and `18` (the value for the `decimal` parameter.


6. Compile the contract using compiler version 0.5.0.

7. Check for any errors and debug as needed.

8. See the Evaluation Evidence section for a screenshot of the successful compilation of the contract.

### Create the KaseiCoin Crowdsale Contract

Define the KaseiCoin crowdsale contract.

1. Import the provided `KaseiCoinCrowdsale.sol` starter code into the Remix IDE.

2. Have this contract inherit the following OpenZeppelin contracts:

* `Crowdsale`

* `MintedCrowdsale`

3. Within the `KaisenCoinCrowdsale` constructor, provide parameters for all of the features of your crowdsale, such as `rate`, `wallet` (where the funds that the token raises should be deposited), and `token`. Configure these parameters as you see fit for your KaseiCoin token.

4. Compile the contract using compiler version 0.5.0.

5. Check for any errors and debug as needed.

6. See the Evaluation Evidence section for a screenshot of the successful compilation of the contract.

### Create the KaseiCoin Deployer Contract


Create the KaseiCoin deployer contract, with variables to store the addresses of the `KaseiCoin` and `KaseiCoinCrowdsale` contracts, which this contract will deploy.

1. Create an `address public` variable called `kasei_token_address`, which will store `KaseiCoin`’s address once that contract has been deployed.

2. Create an `address public` variable called `kasei_crowdsale_address`, which will store `KaseiCoinCrowdsale`'s address once that contract has been deployed.

3. Add the following parameters to the constructor for the `KaseiCoinCrowdsaleDeployer` contract: `name`, `symbol`, and `wallet`.

4. Inside of the constructor body (between the curly braces), complete the following steps:

    * Create a new instance of the `KaseiCoinToken` contract.

    * Assign the KaseiCoin token contract’s address to the `kasei_token_address` variable. This will allow an easy fetch the token's address later.

    * Create a new instance of the `KaseiCoinCrowdsale` contract using the following parameters:

       * `rate` (Set `rate` equal to 1 in order to maintain parity with ether.)

       * `wallet` (Pass `wallet` in from the main constructor. This is the wallet that will get paid all of the ether raised by the crowdsale contract.)

       * `token` (This should be the `token` variable where `KaseiCoin` is stored.)

    * Assign the KaseiCoin crowdsale contract’s address to the `kasei_crowdsale_address` variable. This will allow an easy fetch the crowdsale’s address later.

    * Set the `KaseiCoinCrowdsale` contract as a minter.

    * Have the `KaseiCoinCrowdsaleDeployer` renounce its minter role.

5. Compile the contract using compiler version 0.5.0.

6. Check for any errors and debug as needed.

7. See the Evaluation Evidence section for a screenshot of the successful compilation of the contract.


### Evaluation Evidence

1. Successful compilation of the KaseiCoin.sol contract
![compilaton_kasei_coin](Images/KaseiCoin-compilation.png)

2.Successful compilation of the KaseiCoin Crowdsale and KaseiCoin Crowdsale Deployer contracts
![compilaton_kasei_coin_crowdsaleanddeployer](Images/KaseiCoinCrowdsale-compilation.png)



### Deploy the Crowdsale to a Local Blockchain

This section describes, deploying the crowdsale to a local blockchain using Remix, MetaMask, and Ganache. 


#### Deploy the crowdsale to a local blockchain with Remix, MetaMask, and Ganache.

![remix_contract_deployment](Images/Remix_contract_deploy.png)

![metaMask_contract_deployment](Images/contract_deployment.png)

![ganache_contract_deployment](Images/contract_hash.png)
*transaction hash in Remix with address via Ganache as seen in images below*

#### Test the functionality of the crowdsale by using test accounts to buy new tokens and then checking the balances associated with those accounts.

**3 Eth Transaction:**

Meta Mask Confirmation of transaction

![meta_mask_3eth](Images/3eth_meta.png)

Ganache Record of transaction

![ganache_3eth](Images/3eth_ganache.png)

**10 Eth Transaction:**

Meta Mask Confirmation of transaction

![meta_mask_10eth](Images/10eth_meta.png)

Ganache Record of transaction

![ganache_10eth](Images/10eth_ganache.png)


**All Transaction Records in Ganache**
    
![ganache_all_transactions](Images/all_ganache_transactions.png)

![ganache_address_balances](Images/ganache_balances.png)

#### After purchasing tokens with one or more test accounts, view the total supply of minted tokens and the amount of wei that has been raised in the crowdsale contract.

Remix IDE display of Kasei Coin balance after 3 eth transaction

![Remix_3coins](Images/3Kasei_Coins.png)

Remix IDE display of total wei raised

![balance_after_purchase](Images/3eth_transaction_coin_total.png)

Remix IDE display of Kasei Coin balance after 10 eth transaction

![Remix_13coins](Images/13Kasei_Coins.png)

Remix IDE display of total wei raised

![balance_after_purchase_10eth](Images/10eth_transaction_coin_total.png)

