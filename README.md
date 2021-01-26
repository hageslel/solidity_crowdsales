## Project Overview

The goal of this project was to deploy a crowdsale, which offered PupperCoin tokens (PUP) in exchange for ether (ETH).  To complete this project the following OpenZeppelin libraries were utilized: ERC20, ERC20Detailed, ERC20Mintable, Crowdsale, MintedCrowdsale, CappedCrowdsale, TimedCrowdsale, and RefundablePostDeliveryCrowdsale.  All libraries were used together to deploy the crowdsale and define parameters of the sale.  A total of three contracts were built to accomplish all tasks.  The PupperCoin contract was used to generate tokens, the PupperCoinSale contract defines the parameters of the crowdsale, and the PupperCoinSaleDeployer contract brings all contracts together and deploys the sale.  Further details of the process, along with examples, can be found in the content below. 

### PupperCoin Contract

The PupperCoin contract can be found in the PupperCoin.sol file.  This contract was created simply to generate a token that meets ERC20 standards.  The contract inherits the ERC20, ERC20Detailed, and ERC20Mintable contracts that were imported from Github at the top of the file.  It was built using the ERC20Detailed constructor, which accepts the following arguments: name, symbol, and decimals.  A decimal amount of 18 was hardcoded in to align with Ethereum use cases (1 ETH = 10^18 wei).  This contract is later imported into the Crowdsale.sol file, allowing it to be inherited into the PupperCoinSale and PupperCoinSaleDeployer contracts as needed.  

### PupperCoinSale Contract 

The PupperCoinSale contract can be found in the Crowdsale.sol file.  This contract inherits the Crowdsale, MintedCrowdsale, CappedCrowdsale, TimedCrowdsale, and RefundablePostDeliveryCrowdsale contracts that were imported from Github at the top of the file. All variables defined in the constructor align with varialbes required to be passed into each inherited crowdsale contract's constructor.  No variables were hardcoded in this contract, allowing for contract reuse and flexibility.  

### PupperCoinSaleDeployer Contract

The PupperCoinSaleDeployer contract can also be found in Crowdsale.sol file.  This contract was built to bring all contracts together and actually deploy the crowdsale.  Once deployed, this contract will provide the address of the token generated from the PupperCoin contract, as well as the token sale address generated from the PupperCoinSale contract.  Within the constructor variables are passed to define the token and sale.  The name of the token will be provided here ("PupperCoin"), the symbol will be provided ("PUP"), and the wallet address that will be collecting all Ether raised from the sale.  A demonstration of how this works is provided "Interacting with the Contract" section below.  

The final components of this 
