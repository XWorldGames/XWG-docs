# Game Mechanism

## **Game Mechanism**

### **Matching Rules**

According to the matching time, the matching is divided into two stages: **normal matching and extended matching:**

**Normal matching stage**: The difference in the combat power \(x\) of the matching user card group does not exceed 300 users. Calculating according to the user's matching time, the matching time \(t\) t^2+5 is compared with 300 to take the minimum value \(n\), and the matching range: x-n ~ x+n. According to the user's combat power, the value is increased by one up and down by one in the matching range, and the retrieved values ​​are put into a list in turn, and then matched users are selected in turn according to the values ​​in the list. If the match is successful, the battle flow is entered. The settlement coefficient \(k\) for normal matching is 100%

**Extended matching stage**: the normal matching stage will enter the extended matching stage if the match is not successful. Calculating according to the user’s matching time, matching time \(t\), matching range: x-\(t^2+5\) ~ x+ \(t^2+5\). According to the user's combat power, the value is increased by one up and down by one in the matching range, and the retrieved values ​​are put into a list in turn, and then matched users are selected in turn according to the values ​​in the list. If the match is successful, the battle flow is entered. Expansion of matching settlement coefficient \(k\): 1-\(the absolute value of the difference in combat power-300\) / 50 \* 5% \(greater than 1 is treated as 1, and negative numbers are treated as 0\)

### **Settlement rules**

Players will lose experience if they fail in battle, and $XWG will be awarded if they win.

The lost experience of a single card of the losing party is: current level upgrade experience\*0.2%\*settlement coefficient \(k\)

The total experience lost by the loser \(m\) is: the sum of the experience dropped by all cards in all participating decks

XWG obtained by the winner: m\*0.5/100

XWG won in prize pool: m\*0.2/100

Experience gained back by the losing party: m\*0.3

### Mission Rules

Players can earn mission reward points for doing missions, which can be converted into $XWG

Players gaining $XWG: Periodic mission mining/Total player points \* Points of a single player

### Expedition Rules

Conquest is divided into **ordinary expedition and genesis expedition**. You can get $XWG rewards if you stake your own cards on **expedition**. If cards are acquired from the Genesis Sale, you will get additional Genesis Staking rewards.

**Ordinary Expedition Revenue Formula**

_PR = player’s one-card staking revenue_

_TR = current total revenue distributes to staking pool_

_TV = total reference value of participating cards_

_PV = player’s one-card reference value_

_B = current block \#_

_S = current staking block \#_

_BP = current block production_

**PR = TR / TV \* PV \* \(\(B-S\) / \(TR/BP\)\)**

**Genesis Expedition Staking Reward**

![](../.gitbook/assets/0%20%281%29.png)

## Where to get $XWG?

**Airdrop**: When players enter the game, they will get 1 common white card and 4 experience books as complimentary from the system, and $XWG can be obtained from recycling the card.

**Mission**: players can earn mission reward points through daily missions, and the mission reward points can be converted into XWG

**10 lucky draw**: Players have chances to draw high-level cards from 10 lucky draws, and they can sell them to get $XWG through the official NFT exchange.

**Expedition Staking**: Players can get $XWG by staking their cards with the conquest feature.

**Combat**: Players can earn $XWG if they win in-game battles.

