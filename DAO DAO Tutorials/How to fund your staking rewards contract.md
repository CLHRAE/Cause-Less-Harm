## Setting up staking rewards for your DAO using cw20-stake-reward-distributor smart contract - a step by step tutorial.

### Fund cw20-stake-rewards-distributor contract.

This tutorial is the next step after you have completed "How to add staking rewards to your DAO tutorial".

In order to distribute staking rewards, the contract needs to hold funds to distribute.  This step will fund the staking rewards contract, which we setup in the last step.

In order to fund the staking rewards contract we need to send the token we nominated in the first step to the contract.  

Reminder, the staking rewards are calculated to distribute every block (roughly 6s).   For my example, I chose to calculate 1 quarter of staking rewards at 0.018176 $CLH per block.  So I am funding my staking rewards contract with 23,800 $CLH

#### Step 1: Create a new governance proposal
First step is to create a new governance proposal. New governance proposals can be created by clicking the “+ New Proposal” button on your DAOs main page. 

#### Step 2: Fill out title and description.

The New Proposal page will prompt you to enter a title and description for your proposal.  Both are required in order to publish your proposal.

#### Step 3: Add "Spend Action

In order to fund the cw20-stake-reward-distributor smart contract we’ll choose “+ Add an action” button under the Action heading.

Choose "DAO Treasury" Category

Choose the “Spend” action

![Image](https://user-images.githubusercontent.com/114192151/235364166-27e5930f-d728-41ec-bda0-9c86680de78e.png)

The Spend action requires 3 inputs: Number of tokens to send, token, and address to send the tokens.  

![Image](https://user-images.githubusercontent.com/114192151/235364281-8f2ae2bd-9efa-4a6c-8be2-1f1f994fd276.png)

In our example we’re sending 23,800 $CLH to the cw20-stake-reward-distributor contract address.

#### Step 4: Fill out quantity of tokens

#### Step 5: Choose token denomination
This needs to be the same cw20 token that you configured the contract with.

#### Step 6: Input staking rewards contract address
The cw20-stake-reward-distributor contract address can be found by going into the executed proposal that we created earlier.  Scroll past your proposal description and look for “Instantiated Address”.

![Image](https://user-images.githubusercontent.com/114192151/235364508-37905a16-6da3-4b4f-8ccb-8e902e9a389f.png)

### Step 7: Publish proposal
Clicking the “Publish” button  will create the code to instantiate the cw20-stake-reward-distributor smart contract for your DAO. 

Once published, the governance proposal will go up for vote.   If the governance proposal passes, the proposal can be executed by any DAO member, which will cause the code to be run on chain, and thus your staking rewards contract will have funds to distribute.

At this point, the staking rewards contract is live, and is funded.  This means that until we run the “distribute” command, staking rewards will be accruing.

Next up distributing staking rewards.

**Tutorial author:**
CauseLessHarmRae

