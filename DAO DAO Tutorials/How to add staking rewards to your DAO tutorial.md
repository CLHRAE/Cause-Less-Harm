## Setting up staking rewards for your DAO using cw20-stake-reward-distributor smart contract - a step by step tutorial.

### Instantiate the cw20-stake-rewards-distributor contract.

#### Step 1: Create new proposal
In order to instantiate the staking rewards contract (get staking rewards working in your DAO), we require a new governance proposal.  

New governance proposals can be created by clicking the “+ New Proposal” button on your DAOs main page. 

**Step 2: Fill out title and description.**

The New Proposal page will prompt you to enter a title and description for your proposal.  Both are required in order to publish your proposal.

**Step 3: Add "Instantiate Smart Contract" action.**

In order to instantiate the cw20-stake-reward-distributor smart contract we’ll choose “+ Add an action” button under the Action heading.

Choose "Smart Contracting" Category

Choose “Instantiate Smart Contract” action

![image](https://user-images.githubusercontent.com/114192151/235354132-ae85c303-eee8-4562-a7c8-9608654aa297.png)

In the instantiate smart contract action widget, there are four fields that require input.  

Below is a completed instantiate smart contract widget which I created for Cause Less Harm DAO.  Use it for reference and syntax, but note that other than the Code ID, it is all specific to the Cause Less Harm DAO configuration.

![image](https://user-images.githubusercontent.com/114192151/235354798-0d063c1d-4351-4080-a27a-913ae5f2c8c4.png)

The four fields are:

#### Step 4: Fill out Code ID: 
Currently 2446, though could change with an update.  All current Main net Code IDs can be found in [DAO DAO releases](https://github.com/DA0-DA0/dao-contracts/releases) under Juno-1  

#### Step 5: Fill out Contract Label:  
Can be whatever you’d like, though helpful to name it appropriately

#### Step 6: Fill out Message:  
JSON code which is the input data needed to configure the cw20-stake-reward-distributor.  
Code can be found on DAO DAO github under [contracts/staking/cw20-stake-reward-distributor/src/msg.rs](https://github.com/DA0-DA0/dao-contracts/blob/main/contracts/staking/cw20-stake-reward-distributor/src/msg.rs) under InstantiateMsg

![image](https://user-images.githubusercontent.com/114192151/235355261-5e635740-33aa-4e74-bf31-f66511dfa894.png)

As we can see from the code above, the contract is expecting four points of data for configuration; “owner”, “staking_addr”, “reward_rate”, and “reward_token”.  Omitting any of these will result in an error.

* **“owner”:**  is likely to be the DAO’s address, but could be a SubDAO.  DAO address can be found in the DAOs URL or on the DAOs main page, as shown below.

![image](https://user-images.githubusercontent.com/114192151/235355413-2282a45d-4b50-4a26-90c1-0b63ee82840f.png)

* **"staking_addr”:** is the contract address for your staking contract.  Located on the Create proposal sidebar.

![image](https://user-images.githubusercontent.com/114192151/235355496-c40e5645-74f5-4cfc-a913-aa8b7ca95167.png)

* **“reward_rate”:** The reward rate is the number of rewards paid per block (roughly every 6s), and is written with 6 decimal places.  In the above example 0.018176 is written as 18176.  If you wanted to pay 10 tokens per block it would be written as 10000000

* **“reward_token”:**  The reward token is the Juno address for your governance token.  It can be found in the dropdown for your token in the Treasury tab.

![image](https://user-images.githubusercontent.com/114192151/235355673-ca13b9b5-e495-4b54-81f9-e996b2d7cc2b.png)

### Step 7: Publish proposal
Clicking the “Publish” button  will create the code to instantiate the cw20-stake-reward-distributor smart contract for your DAO. 

Once published, the governance proposal will go up for vote.   If the governance proposal passes, the proposal can be executed by any DAO member, which will cause the code to be run on chain, and thus setup your staking rewards contract.

At this point, the staking rewards contract is live.  This means that from this point forward, until we run the “distribute” command, staking rewards will be accruing.

Next up, funding the staking reward contract "See Fund Staking rewards contract" tutorial


tutorial written by: CauseLessHarmRae


