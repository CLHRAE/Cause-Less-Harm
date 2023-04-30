## Setting up staking rewards for your DAO using cw20-stake-reward-distributor smart contract - a step by step tutorial.

### Distribute cw20-stake-rewards-distributor contract.


So, to recap.   We have instantiated the cw20-stake-reward-distributor contract in our DAO, and configured it to reward anyone who stakes in our DAO at a customised rate.   

In order to distribute those rewards, we need to execute the “distribute” call on our cw20-stake-reward-distributor contract, using DAO DAO's Transaction Builder.  

**It should be noted that executing the “distribute” command on the staking rewards contract is permissionless (can be executed by anyone).**

![Image](https://user-images.githubusercontent.com/114192151/235371561-9072b7cf-a25f-4c5c-aae1-ed3108811443.png)

#### Step 1: Navigate to https://daodao.zone/me/tx
You can also click on the "me" button on the left hand side navigation, then click "Transaction Builder" on the top right.

#### Step 2: Add the "Execute Smart Contract" action
In order to execute the "distribute" call we’ll choose “+ Add an action” button under the Action heading.

Choose "Smart Contracting" Category

Choose “Execute Smart Contract” action

#### Step 3: Fill in Smart Contract address
The cw20-stake-reward-distributor contract address can be found by going into the executed proposal that we created earlier.  Scroll past your proposal description and look for “Instantiated Address”.

![Image](https://user-images.githubusercontent.com/114192151/235364508-37905a16-6da3-4b4f-8ccb-8e902e9a389f.png)

#### Step 4: Fill in the "distribute" Message 
It's important that the "distribute" message is copied exactly as below, or it will not execute.

{
  "distribute": {}
}

#### Step 5: Execute "distibute" command
Click the execute button and complete the transaction.

That's it!  You've distributed the staking rewards.  This action needs to be completed whenever you want the staking rewards to be distributed. 

Note - It will soon be possible to automatically execute the command.

**Tutorial author:**
CauseLessHarmRae
