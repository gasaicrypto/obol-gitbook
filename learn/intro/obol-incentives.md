# OBOL Incentives

## OBOL Incentives Program

The **OBOL Incentives Program** is designed to be powerful and transparent, rewarding anyone OBOL tokens for staking on **Distributed Validators (DVs).**

### What is the OBOL Incentives Program?

OBOL Incentives offer an opportunity to **earn OBOL Token incentives** for staking on **Distributed Validators**.

* **12.5 million OBOL Tokens** (2.5% of the total supply) will be distributed in the **first year (2025).**
* Incentives **begin accruing on March 24th, 2025.**
* **Claiming** will be possible shortly thereafter.

Each week, **1/52 of the 12.5M OBOL** will be distributed (**\~240,385 OBOL per week**).\
If you are staking with a partner, incentives must be claimed participating partner UI frontends or via the [DV Launchpad](https://launchpad.obol.org) if you are running your own distributed validator.

***

### How do I participate?

You can participate by:

1. **Staking through Staking Partners**
   * For the latest list of partners that qualify for OBOL Incentives, visit [https://obol.org/incentives](https://obol.org/incentives).
2. **Running Your Own DV Cluster**
   * Use the [DV Launchpad](https://launchpad.obol.org) to create and manage your own DV cluster, e.g., using a [DappNode](https://dappnode.com/) or other hardware.
   * This method directly supports Ethereum’s decentralization while earning OBOL incentives.
   * Visit the official Obol Discord to find squad mates.

***

### Is existing stake eligible?

* Stake deposited after January 13th, 2025, is eligible for rewards.
* Exception: Stake deposited directly on DVs (outside of staking protocols) is eligible regardless of when it was deposited.

***

### How much OBOL will I receive per ETH staked on DVs?

* **The OBOL amount per ETH depends on total ETH participation.**
* The **240,385 OBOL per week** is distributed **proportionally** across all participating ETH.
* Your **share of the total ETH** determines your **share of OBOL incentives.**
* If you need help calculating your potential rewards, feel free to use this community created calculator:
  * **NOTE:** This is a community created calculator, is not managed by DV Labs or the Obol Association, and is not to be fully trusted.&#x20;

***

### How are incentives tracked?

OBOL incentives are based on **staking rewards earned by validators (pubkeys)**. Performance factors like **effectiveness and uptime** impact rewards.

* Incentives are tracked off-chain in a centralized database.
* API endpoints allow users & protocols to query earned incentives.
* Incentives are displayed in the [Obol DV Launchpad](https://launchpad.obol.org) and/or participating partner UI frontends.

***

### How can I track my OBOL incentives?

* For those staking with a Partner: Your staking platform should show and distribute your OBOL incentives in their UI frontend.
* For those running their own Distributed Validators: Incentives are displayed on the [DV Launchpad](https://launchpad.obol.org).

***

### What benefits do I get from the OBOL Token?

OBOL Tokens serve as the basis for ownership and governance of the Obol Collective.\
Learn more on the OBOL Token page.

<figure><img src="../../.gitbook/assets/image (57).png" alt=""><figcaption></figcaption></figure>

***

### How are incentives calculated?

OBOL incentives are tied to validator staking rewards and calculated daily.

For a validator with total staking rewards ( R ), and operator split percentages ( p\_1, p\_2, ..., p\_n ), the operator’s rewards (Oᵢ) are:

\[ Oᵢ = R × pᵢ × 0.01 × 1.01 ]

* ( pᵢ ) = Operator’s percentage split.
* The 1.01 multiplier ensures the full 1% of rewards is distributed correctly.

Higher effectiveness & uptime = more incentives.

***

### Can I withdraw my staked ETH at any time?

Yes, you can withdraw at anytime but you **stop accruing incentives** upon withdrawal.

* If you are staking with a partner,  they may choose to set penalties for early withdrawals but this is not common.
* If you are running your own distributed validator, there is no penalty for withdrawing or exiting.

***

### What is the minimum amount of ETH needed to stake?

* If you are staking with a partner,  they will have their own minimum deposit amount.
* If you are running your own distributed validator, the total amount required by your squad is 32 ETH.
* Check each partner’s requirements at [https://obol.org/incentives](https://obol.org/incentives).

***

### What happens if my validator has downtime?

Since OBOL incentives are tied to staking rewards, validator performance metrics directly impact earned incentives.

* More uptime & effectiveness = More incentives.
* Longer downtime = Fewer rewards.

***

### Will my incentives be public?

Yes. Incentives are publicly accessible through the Obol API (with the correct protocol address).

***

### How do I increase the amount of OBOL I can earn?

* Increase the amount of ETH staked.
* Improve validator performance (higher uptime & effectiveness).

***

### What are the benefits of using Distributed Validators?

Distributed Validators improve performance, lower risks and increase rewards. Learn more at [obol.org/learn](https://obol.org/learn).

***

### How can I get support if I have issues?

* Join the Obol Discord community: [discord.gg/obol](https://discord.gg/obol).
* If you are staking with a partner, reach out to them directly.

***
