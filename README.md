## Project Overview

The goal of this project was to deploy a crowdsale, which offered PupperCoin tokens (PUP) in exchange for ether (ETH).  To complete this project the following OpenZeppelin libraries were utilized: ERC20, ERC20Detailed, ERC20Mintable, Crowdsale, MintedCrowdsale, CappedCrowdsale, TimedCrowdsale, and RefundablePostDeliveryCrowdsale.  All libraries were used together to deploy the crowdsale and define parameters of the sale.  A total of three contracts were built to accomplish all tasks.  The PupperCoin contract was used to generate tokens, the PupperCoinSale contract defines the parameters of the crowdsale, and the PupperCoinSaleDeployer contract brings all contracts together and deploys the sale.  Further details of the process, along with examples, can be found in the content below. 

### PupperCoin Contract

The PupperCoin contract can be found on the PupperCoin.sol file.  This contract was created simply to generate a token that meets ERC20 standards.  The contract was built using the ERC20Detailed constructor, which accepts the following arguments: name, symbol, and decimals.  A decimal amount of 18 was hardcoded in to align with Ethereum use cases (1 ETH = 10^18 wei).  This contract is later imported into the Crowdsale.sol file, allowing it to be inherited into the PupperCoinSale and PupperCoinSaleDeployer contracts as needed.  

### PupperCoin Sale Contract 

The PupperCoinSale contract can be found on the Crowdsale.sol file.  This contract was 
