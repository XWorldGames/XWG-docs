# Game Mechanism

**Matching Rules**

According to the matching time, the matching is divided into two stages:&#x20;

> **Normal matching**&#x20;
>
> **Extended matching**

**Normal matching**: The difference in the combat power (x) of the matching user card group does not exceed 300 users.&#x20;

Calculating according to the user's matching time, the matching time (t) t^2+5 is compared with 300 to take the minimum value (n), and the matching range: x-n \~ x+n. According to the user's battle power, the value is increased by one up and down by one in the matching range, and the retrieved values ​​are put into a list in turn, and then matched users are selected in turn according to the values ​​in the list. If the match is successful, the battle flow is entered.

The settlement coefficient (k) for normal matching is 100%

**Extended matching**: the normal matching stage will enter the extended matching stage if the match is not successful.&#x20;

Calculating according to the user’s matching time, matching time (t), matching range:&#x20;

**`x-(t^2+5) ~ x+ (t^2+5)`**

According to the user's combat power, the value is increased by one up and down by one in the matching range, and the retrieved values ​​are put into a list in turn, and then matched users are selected in turn according to the values ​​in the list. If the match is successful, the battle flow is entered.

Expansion of matching settlement coefficient (k):&#x20;

**`1-(the absolute value of the difference in combat power-300) / 50 * 5%  (greater than 1 is treated as 1, and negative numbers are treated as 0)`**

### **Settlement rules**

Players will lose experience if they fail in battle, and $XWG will be awarded if they win.

The lost experience of a single card of the losing party is: **`current level upgrade experience * 0.2% * settlement coefficient (k)`**

The total experience lost by the loser (M) is: the sum of the experience dropped by all cards in all participating decks

$XWG obtained by the winner: $$M*0.5/100$$&#x20;

$XWG win in prize pool: $$M*0.2/100$$&#x20;

$Experience gained back by the losing party: $$M*0.3$$

### Mission Rules

Players can earn mission reward points for doing missions, which can be converted into $XWG

Players gaining $XWG: **`Periodic mission mining/Total player Points * Points of a single player`**

### Expedition Rules

Conquest is divided into **ordinary expedition and genesis expedition**. You can get $XWG rewards if you stake your own cards on **expedition**. If cards are acquired from the Genesis Sale, you will get additional Genesis Staking rewards.

**Ordinary Expedition Revenue Formula**

_PR = player’s one-card staking revenue_

_TR = current total revenue distributes to staking pool_

_TV = total reference value of participating cards_

_PV = player’s one-card reference value_

_B = current block #_

_S = current staking block #_

_BP = current block production_

&#x20;**** $$PR= \frac{TR}{TV}\cdot PV\cdot\frac{B-S}{BP}$$&#x20;

****

### **Genesis Expedition Staking Reward**

![](<../../../.gitbook/assets/0 (1).png>)



****
