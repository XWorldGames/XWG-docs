---
description: Uesers can use Play to earn to stake to earn XWG Token.
---

# 🛣 P2E2S Model

![X World Games Innovative P2E2S Flowchart](<../../.gitbook/assets/Token Earning Flow.jpg>)

## P2E2S Staking Mechanism

### **Rules**

1. **Staking Pools**: all cards will be staked into the same staking pool.
2. **Staking Warehouse**: All cards for staking must be transferred to the Card Warehouse before they start staking
3. **Staking Period:**
   1. Users are able to stake at any time when any pool is open and available.
   2. Each staking pool has its **own portal** according to the length of the staking period
      * **7 days, 14 days, 30 days.**
      * Users are allowed to stake at any time before the staking period ends.
      * Calculation of required LUCIDs fee will be based on the length of staking
   3. Different staking periods require different amounts of LUCIDs and will have **different ROI**.
      * 30 days (greatest return), followed by 14 days and 7 days (least return)
      * The implementation will use the **discounted hash rate** approach to achieve.
   4. Upon expiration of the staking period, the staking pool will do the reward calculation and lock all rewards for users. No more output from the staking pools.
      * The reward cannot be claimed before the staking period has expired.
   5. After the reward calculation, users will have 7 days to claim the rewards. Unclaimed Rewards after such 7 days period will be sent to the burning pool and destroyed.
   6. **Card Redemption (Unstake).**
      * Players can unstake before the staking period’s expiration, but no already-consumed LUCIDs will NOT be returned and no staking rewards will be given.
      * After the staking expiration, once players unstake the cards, the reward will be automatically claimed as well (one action).
4. Minimum Participation Requirements.
   * Hash Rate: the total hash rate power of the cards (DECK GROUP) must reach a minimum value in order to enter the staking pool, and such value is configurable and hot-change (can be adjusted event by event).
   * A minimum value of hash rate power per deck with the total hash rate power of 20 cards must not be less than **12,720**.
   * Lucid: the amount consumed varies according to the hash rate of cards staked and the length of the staking time.
   * Rarity: _**No Special Requirement for Card Rarity.**_
   * Quantity**: 20 cards per deck**&#x20;
   * Hero Character Requirement: _**No Special Requirement for Character.**_

## Hashrate Calculation:

$$
\text{HashRate}=\text{nftBasePrice}+\frac{\text{experience}}{100}+(\text{star}-1)\cdot50
$$

If the staking period is selected as 30 days, the hashrate calculation is the same as the previous hashrate calculation

$$
\text{Staking Hashrate} = \sum \text{DeckHashrate}
$$

If the staking period is selected as 14 days, the hashrate is the previous hashrate multiplied by 0.9

$$
\text{Staking Hashrate} = 0.9\cdot\sum \text{DeckHashrate}
$$

If the staking period is selected as 7 days, the hashrate is the previous hashrate multiplied by 0.8

$$
\text{Staking Hashrate} = 0.8\cdot\sum \text{DeckHashrate}
$$

If $$DeckHashrate < 12,720$$, such deck group cannot be staked

## Required Lucid Calculation

Staking Time: $$t$$

Base Time: $$t_{0} = 30 \cdot 24 \cdot 60 \cdot 60 = 2,592,000 seconds$$

Lucid Requirement: $$m = 50,000$$

Hashrate Benchmark: $$H_{0} = 48$$

$$
\text{Required Lucid} = \frac{m \cdot t \cdot \text{Total Staking Hashrate}}{t_{0} \cdot H_{0}}
$$

The calculation method of staking time _`t`_ is the activity deadline - the time at the time of staking:

$$
t = t_{\text{expiry}} - t_{\text{stake}}
$$

There are 3 staking period, corresponding to 7 days, 14 days, and 30 days.

$$
\text{If  } t_{\text{expiry}} \geqslant t_{\text{stake}}, \text{it cannot be staked to the corresponding expiration date.}
$$

## Reward Calculation

APR constant value: $$\beta = 300%$$ &#x20;

Reward Output per second**:** $$r$$

Seconds in a year: 31,536,000 $$B_{0}$$

The total hashrate of the current staking deck: $$H_{\text{total}}$$

The Maximum of total hashrate: $$H_{\text{max}}$$

$$
\text{APR} = \frac{r\cdot B_{0}}{H_{\text{total}}}
$$

**An adjustment coefficient** $$r$$ **to ensure that the APR is a one constant value below a certain upper limit of hashrate**

$$
r = \begin{cases} \frac{\beta \cdot H_{\text{total}}}{B_{0}} & (H_{\text{total}} < H_{\text{max}})\\ \frac{\beta \cdot H_{\text{max}}}{B_{0}} & (H_{\text{total}} \geqslant H_{\text{max}}) \end{cases}
$$

After the user stakes and unstakes, update $$r$$ value.

_**The Maximum of total hashrate**_ $$H_{\text{max}}$$ _**of the first phase is 32,850,000.**_

## Staking Example

### _The staking period for 20 legendary cards (1 generation 1 star) is selected as 7 days, and the staking period for 20 myth cards (1 generation 1 star) is selected as 30 days, stake from the beginning:_

__

_`Legendary card’s hasrate = 3,182`_

_`Myth card’s hashrate = 6,363`_

__

$$
\text{FirstDeckHashrate} = 20 \cdot 3,182 = 63,640
$$

$$
\text{SecondDeckHashrate} = 20 \cdot6,363 = 127,260
$$

_**`Since the both deck’s hashrate > = 12,720, staking OKAY ✅`**_

_`7-days staking period discount = 0.8`_

$$
\text{FirstDeckHashrate} = 0.8 \cdot 63,640 = 50,912
$$

$$
\text{SecondDeckHashrate} = 127,260
$$

$$
\text{DeckHashrate} = \text{FirstDeckHashrate} + \text{SecondDeckHashrate} = 178,172
$$

The total hashrate of the current staking card $$H_{\text{total}}= 25,000,000$$

Since $$H_{\text{total}} + \text{DeckHashrate}$$ does not exceed the maximum hashrate $$H_{\text{max}}= 32,850,000$$, therefore:

$$
r = \frac{\beta \cdot (H_{\text{total}} + \text{DeckHashrate})}{B_{0}}
$$

### **S**_**taking Reward Calculation**:_

First 7 days

$$
r \cdot 7 \cdot 24 \cdot 60 \cdot 60 \cdot\frac{\text{DeckHashrate}}{H_{\text{total}}+\text{DeckHashrate}} = \frac{3 \cdot (25,000,000 + 178,172)}{31,536,000}\cdot7\cdot 24\cdot60\cdot60\cdot\frac{178,172}{25,000,000 + 178,172} \cong 10250.99\ \text{XWG}
$$

The rest of 23 days

Since no more staking for the first deck after 7 days, therefore:

$$
\text{DeckHashrate} = 127,260
$$

$$
H_{\text{total}}=25,000,000 + 127,260 = 25,127,260 < 32,850,000,
$$

so:

$$
r = \frac{\beta \cdot H_{\text{total}}}{B_{0}}
$$



$$
r\cdot 23 \cdot 24 \cdot60\cdot 60\cdot\frac{\text{DeckHashrate}}{H_{\text{total}}} = \frac{3 \cdot 25,127,260}{31,536,000}\cdot23\cdot 24\cdot60\cdot60\cdot\frac{127,260}{25,127,260} \cong  24057.37\ \text{XWG}
$$

**`Total staking reward = 10,250.99 XWG + 24,057.37 XWG = 34308.36 XWG`**

### **Lucid Consumption for Staking:**

First Deck

$$
\frac{m \cdot t \cdot \text{FirstDeckHashrate}}{t_{0} \cdot H_{0}} = \frac{50,000 \cdot 7\cdot 24\cdot60\cdot60 \cdot 50,912}{2,592,000 \cdot 48} = 12,374,444 \ \text{Basic Lucid}$
$$

Second Deck:

$$
\frac{m \cdot t \cdot \text{SecondDeckHashrate}}{t_{0} \cdot H_{0}} = \frac{50,000 \cdot 30\cdot 24\cdot60\cdot60 \cdot 127,260}{2,592,000 \cdot 48} = 132,562,500 \ \text{Basic Lucid}
$$

**`Total Lucids required: 144,936,944 Basic Lucid`**
