
# Introduction

## About Penguin Finance

- Penguin finance is committed to providing protocols and users with a one-stop solution on asset swap and liquidity management. Our service incorporates swap, staking and bonding.

- Swap is used for token swap and liquidity pool management.

- Staking helps protocols to lock the liquidity of their tokens and reward users with constant yield. 

- Bonding helps users to purchase tokens at a discounted price, which allows protocols to obtain their own liquidity without paying a hefty incentive to rent liquidity. In the meantime, this protocol-owned liquidity continues to facilitate exchange, and the protocol can also obtain transaction fees from liquidity exchange which helps achieve protocols' sustainable development. 
<br />

## Liquidity problems
**Selling pressure**
As the incentives start, users can receive substantially rewarded tokens with minimum cost (exclusive of impermanent loss). Consequently, big players profit via liquidity mining, withdrawing tokens, and dumping, which places selling pressure on the token market.

**Contradictory goals**
Projects use incentives to achieve their long-term perspective. However, liquidity is owned by users, and the big players profitably shift to other projects once the incentives are stopped, meaning projects can only watch their liquidity dwindle and do nothing about it.

**Impermanent loss to loyal users**
When the protocol is well-developed and the coin price rises, the liquidity providers will absorb the impermanent loss, and the number of protocol tokens in their possession will decrease. A loyal user of a project protocol offers long-term liquidity for the protocol, but when the coin price rises, the percentage of tokens in the liquidity he provides decreases, harming the loyal users’ interests.

**Liquidity loyalty**
Liquidity providers are likely to withdraw liquidity from liquidity pools while the market is turbulent. However, protocols at this time need more liquidity due to their vulnerability.
<br />

## Advantages of Penguin Finance

1. Protocols own liquidity rather than relying on renting liquidity via liquidity mining.
2. Users purchase tokens at a cost with LP tokens, so they would be less likely to sell them at will. 
3. Staking and bonding mechanism will slash circulating tokens and thus makes bonding a competitive option of purchasing tokens, which leads to healthier liquidity for protocols.
4. Rates of liquidity transaction fees can generate ongoing revenue for protocols.
5. Our team of experienced and committed members can offer from marketing to technical support.
<br /> 

# Basics

## Swap

- Penguin Swap is a new generation of decentralized trading protocol and the first product of Penguin Finance. This DEX (decentralized exchange) utilizes AMM (automatic market maker), an integrated protocol, which effectively guarantees the exchange of assets between users and the protocol through algorithms.
<br />

## Staking

- Staking is a value accrual strategy in which stakers stake their tokens to earn rebase rewards. 

- After staking, a corresponding amount of sToken can be received, and rewards will be issued when the smart contract rebases at the end of every epoch. 

- When users unstake, they burn their sTokens and receive a corresponding amount of tokens, and forfeit the rebase reward. Note that the forfeited reward is only applicable to the unstaked amount; the remaining staked tokens (if any) will continue to receive rebase rewards.   
<br />

## Bonding

- Bonding is a secondary value accrual strategy that allows users to purchase tokens issued by protocols at a discounted price. It enables protocols to transfer their native tokens for assets. Rather than renting liquidity from a third party, protocols purchase it directly.

- Once the offering is over, protocols will own these assets and 
distribute emit the additional supply in the same way as liquidity mining.

- Protocols can collect vital infrastructure liquidity through bonds.

- Bonding is done by purchasing tokens with LP tokens instead of giving away tokens in the form of mining in liquidity mining. The advantage it brought is that protocols own their liquidity, and they can also obtain transaction fees from liquidity exchange which helps achieve protocols' sustainable development. 
<br />

# Using Penguin Finance

## How to swap tokens

1. Head on over to the swap page.
To start using swap, you’ll need to connect to a wallet (e.g. Phantom). Note that connecting your wallet is free.

2. Select the tokens you would like to trade. In this example, using SOL to buy BUD. Then enter the number of tokens you want to buy.

3. Click Swap and approve the transaction in your wallet. 
<br />

## How to stake

1. Prepare tokens
Tokens ready for staking are shown on the ‘Bond’ page. If not, swap the target tokens first. Taking BUD as an example: we swap SOL for BUD, and the balance of your BUD will be shown.

2. Stake your tokens.
Select the Bond tab and be directed to a page where you can see a Stake option. 
Click Stake to see the maximum balance that can be staked.
Enter the amount of BUD you would like to stake, then click Stake and sign the transaction.
Once you staked, a corresponding amount of sToken (sBUD) will be received, and your daily yield together with rebase period will be shown in the ‘Staking’ box.
<br />

## How to unstake
1. Select Unstake in Staking box (sToken can be unstaked at any time). Enter the amount you would like to unstake and approve the transaction in your wallet after clicking Unstake.
2. The unstake position will appear under the ‘Staking’ box. These unstaked tokens will be released linearly for 7 days. 
3. Claims must be done manually. Claimable tokens can be collected via clicking the Claim tab and then approving the transaction. Note that unstake can be cancelled by clicking the cancel tab and the unreleased tokens will be staked again.
<br />

## How to bond

1. Deposit liquidity on the ‘Pools’ page. (Buy the tokens needed for bonding first if the balance of the corresponding token is insufficient) LP tokens will be received after adding liquidity.
2. Click Bond on the ‘Bond’ page. You can bond with USDC or LP tokens (Bonding is not recommended if the ROI display is negative). After the bonding, the tokens purchased will be staked automatically and the corresponding information will be seen in the ‘Staking’ box below.
<br />

# Project - Party
## Init Swap
Initiating liquidity pools without permission on Penguin Finance is unavailable at the moment. Contact our administrator in Discord if it is needed.
<br />

## Init Staking
1. Set staking parameters
 - **staking reward type (constant or ratio)**
The form of staking reward can be fixed, such as the total number of tokens awarded in a rebase epoch duration, or it can be based on the number of users staking tokens at a certain rate. (The total amount of tokens awarded in a cycle is controlled in the case of constant type, but it will be impacted by the number of users engaging in staking in the case of ratio type.)
token supply
Initially, it stands for the total amount of token supply, it is also the base of additional issuance of ratio type. For an exponential growth in APY, token supply will accumulate the amount of corresponding additional issuance after each additional issuance.

 - **rebase epoch duration**
The frequency of the staking reward.

2. Prepare reward
   
- Transfer the rewards to be issued to the designated holder. It should be noted that there must be enough balance in the holder to guarantee the distribution of reward before the next rebase. Otherwise, the stakers may not be able to collect staking rewards for a while.
<br />

## How to build a bonding

1. **init a pool**
We need to init a pool at https://app.png.fi/pools. Also, we must verify that the initial value of the LP is one dollar. Since when we initially add the LP, it will generate 1000 tokens, thus we just need to add $500 in liquidity to both sides.
2. **init bonding**
In order to Initialise the bond contract, we need the following parameters.
 
    **token supply**
    How many tokens do you want to issue via bonding?
    This may only be used for a certain number of tokens. Once you've reached the maximum number of tokens that can be issued using this mechanism, it will cease distributing.

    **init price**
    Initial price of bond

    **target price**
    Target price of bond

    **amount**
    How many bonds are expected to be sold before the target price is reached? (If it is small, the inflation variable will be extremely large.)

    **decay time**
    How long (in seconds) does it take for the token price to decay to 0 if no one bonds.

    **min price**
    A min price that prevents the price decays to 0.

    **maxPayoutFactor**
    To limit the maximum quantity of tokens in a single purchase. The value is expressed as N/100,000 of the total amount.

    **vesting time**
    The duration (in seconds) for all the claimable to be released when users unstake.

3. **Preparations of Tokens**

    **payout holder**
    For issuing vToken for bonding purchase, tokens should be punched into the payout holder.

    **reward holder**
    When rebasing, staking needs tokens to be credited to the reward holder, which is then used to create vToken.

    **vested holder**
    The project team should additionally credit the vested holder's account with the project's token.
    The vToken can be exchanged for the project's token at a 1:1 ratio, however, to avoid user arbitrage, the vToken must first go through vesting time before being exchanged for the project's token.
    We can operate the vToken instead of the project team, or the project team can operate it themselves.
<br />

# Deployment of Contracts
We can start contract deployment and bonding/staking launch when you have prepared the above requirements.
<br />

# Contract Design

## Staking contract
This contract is used for entrusting staked tokens and issuing rewards at a configured epoch/interval to stakers. In the early stage, stakers will get a higher APY when the amount of staking is small. At present, this contract integrates three functions mainly.

**stake**
Transfer the staked tokens into the contract, and issue another sToken to stakers according to the proportion of staked tokens in total staked tokens. 

$sTokenAmount = stakeAmount/totalStake*stakeTokenSupply$

Note that the calculated ‘sTokenAmount’ will be 0 if the amount of staked token is small, and thus the contract will fail to be executed. 

**rebase**
The contract executes rebase according to configured epoch, usually every 8 hours. There are currently two types of reward methods: stable reward issuance and exponential reward issuance. The former issues reward at a fixed amount each time, whereas the latter issues reward in a greater amount over time.

**unstake**
Unstake can be cancelled immediately once staked. At this time, a corresponding amount of sToken will be transferred into the contract and be burnt. The contract will transfer tokens to users as per the sToken’s proportion in the total supply. Reward ceases on unstaked tokens.

$tokenAmount = sTtakeAmount/stakeTokenSupply*totalStake$
<br />

## Bonding contract
Users can purchase tokens at a discount to the market price via bonding contract. The exact discount depends on the market demand. Since bonding enables purchase only rather than selling tokens, the price, therefore, will be adjusted by the contract automatically. The token will get an initial price by setting a series of parameters when initialising the contract.

$pirce=totalDebt/bondingSupply*controlVariable$

In this formula, ‘totalDebt’ can be interpreted as the current tokens’ value sold. ‘bondingSupply’ represents the total supply of tokens. ‘controlVariable’ is a proportional factor for the bond price. Higher ‘controlVariable’ means lower discount.

The ‘totalDebt’ will increase accordingly as purchasing takes place, causing a rise in the bond price. The more tokens purchased, the faster the price rises. When the contract is not purchased for a period of time, the ‘totalDebt’ will see an automatic linear decay.

$totalDebt=totalDebt-totalDebt*(now-lastDecay)/decayFactor$

‘lastDecay’ represents the time of the last decay. ‘decayFactor’ is the decay coefficient, and its value represents the duration (in seconds) that the bond price will decay to 0 when no one buys it. 
Finally, after the purchase is successful, the LP token will be stored in the contract and users will receive the corresponding token.

$payoutTokenAmount=lpTokenAmount/price$
<br />

## Vesting Contract
Vesting contract serves to lock a certain amount of tokens in the contract and release them at a configured pace. The released tokens have to be claimed manually. There are four sections in a vesting contract.

**stake**
This process deposits a certain amount of tokens into the contract, which then issues the same amount of vTokens to the stakers.

**vest**
A vesting account needs to be Initialised when doing vesting for the first time. Each user has an independent vesting account, which can be used repeatedly. Each vesting can be interpreted as depositing a certain amount of vTokens into the vesting account.

**update**
The contract keeps updating each vesting account overtime for the purpose of releasing tokens at a certain rate. Each vesting account records the amount of current claimable tokens (released tokens) which accumulate on each update. The corresponding amount of vTokens in the vesting account will be burnt while releasing tokens.

**claim**
The vesting account records the current amount of claimable tokens, and users can transfer these tokens from the contract to their own wallet.
<br />

# Interaction of Contracts
**Clarification**
- Token represents an original asset.
- When using the token to call ‘stake’ in the staking contract, prefix the letter ‘s’ (i.e. sToken) to indicate the corresponding asset obtained.
- When using the token to call ‘vest’ in the vesting contract, prefix the letter ‘v’ (i.e. vToken) to indicate the corresponding asset obtained.
- When using the sToken to call ‘unstake’ in the staking contract, remove the prefix ‘s’ (i.e. token) to indicate the corresponding asset obtained.

**stake**
- Call the staked asset of the vesting contract and obtain a 1:1 amount of vToken.
- Call the staking contract and stake vToken, then obtain the corresponding amount of sVToken.

**unstake**
- Call the unstake of the staking contract to convert sVToken into the corresponding amount of vToken. Staking rewards will be received after a certain period, and the vToken received is more than the amount of token staked previously. 
- Call the vesting contract, vest vToken. Initialise a vesting account first if it is the first time to vest.

**claim**
- When calling a vest and transferring the vToken to the vesting account, the token corresponding to the vToken will be released continuously.
- The released token can be claimed by calling the claim of the vesting contract.

**bond**
- Call the bonding contract to buy token with LP token. Bonding contract sends back the vToken corresponding to the token purchased with the LP token.
- Call staking contract and stake vToken, and then get the corresponding amount of sVToken. The assets obtained via bond will be locked in the staking contract to earn staking rewards. Execute unstake in the previous step when unstake is needed. 


