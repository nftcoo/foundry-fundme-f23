This project is an attempt at the Foundry Fund Me lesson from Patrick Collins' course on Solidity, Blockchain Development and Smart Contracts, accessed at the youtube link below:
https://www.youtube.com/watch?v=sas02qSFZ74

Getting Started
Requirements
git
foundry

Usage
Deploy
forge script script/DeployFundMe.s.sol

Testing
We use unit and forked tests in this repo
forge test
Test covergage
forge coverage

Deployment
Set up environment variables in your .env filr including:
SEPLOLIA_RPC_URL
PRIVATE_KEY (don't use an address with real funds)
ETHERSCAN_API_KEY if you want to verify your contract
Deploy:
forge script script/DeployFundMe.s.sol --rpc-url $SEPOLIA_RPC_URL --private-key $PRIVATE_KEY --broadcast --verify --etherscan-api-key $ETHERSCAN_API_KEY

Scripts
After deploying to a testnet or local net, you can run the scripts.

Using cast deployed locally example:
cast send <FUNDME_CONTRACT_ADDRESS> "fund()" --value 0.1ether --private-key <PRIVATE_KEY>
or
forge script script/Interactions.s.sol --rpc-url sepolia  --private-key $PRIVATE_KEY  --broadcast

Withdraw
cast send <FUNDME_CONTRACT_ADDRESS> "withdraw()"  --private-key <PRIVATE_KEY>

Estimate gas
You can estimate how much gas things cost by running:
forge snapshot
And you'll see an output file called .gas-snapshot

Thank You!