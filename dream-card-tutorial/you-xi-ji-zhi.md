# 游戏机制

## 游戏机制

### **匹配规则**

匹配根据匹配时间分为**正常匹配和扩大匹配两种阶段**

**正常匹配阶段**：匹配用户卡组战力（x）差不超过300用户。

根据用户的匹配时间来计算，匹配时间（t）t^2+5和300比较取最小值（n），匹配范围：x-n ~ x+n。根据用户战力在匹配范围内分别依次向上加一、向下减一取值，把取出来的值依次放进一个列表，再根据列表中的数值依次取配对用户，配对成功则进入战斗流程。正常匹配的结算系数（k）为100%

**扩大匹配阶段**：正常匹配阶段没有匹配成功则进入扩大匹配阶段。

根据用户的匹配时间来计算，匹配时间（t），匹配范围：x-（t^2+5） ~ x+ （t^2+5）。根据用户战力在匹配范围内分别依次向上加一、向下减一取值，把取出来的值依次放进一个列表，再根据列表中的数值依次取配对用户，配对成功则进入战斗流程。扩大匹配的结算系数（k）：1-（战力差的绝对值-300）/50\*5%（大于1按1处理，负数按0来处理）

### **结算规则**

玩家战斗**失败会掉落经验，胜利会获得XWG**

失败方单张卡牌的掉落经验为：当前等级升级经验\*0.2%\*结算系数（k）

失败方掉落的总经验（m）为：所有参战卡组中所有卡牌掉落经验之和

胜利方获得的XWG：m\*0.5/100

奖池获得的XWG：m\*0.2/100

失败方获得的经验：m\*0.3

### **任务激励规则**

玩家做任务可以**获得任务积分，积分可以转换成XWG**

玩家获得XWG：周期任务挖矿/玩家总积分\*单个玩家的积分  


### **远征规则**

远征分为**普通远征**和**创世远征**，把拥有的卡牌进行远征质押即可获得XWG奖励，如果卡牌是第一次质押的创世卡将获得额外的创世奖励\(一次性\)。

**单卡远征质押收益**=当前矿池分配总量/总卡牌参考价值_单卡参考价值_（（当前区块号-质押区块号）/\(当前矿池分配总量/出块产量））

**创世远征奖励：**

| 创世卡牌品质 | 质押满30天 | 质押满60天 | 质押满90天 |
| :--- | :--- | :--- | :--- |
| 稀有（绿卡） | 455XWG | 455XWG | 600XWG |
| 史诗（蓝卡） | 909XWG | 909XWG | 1212XWG |
| 传奇（紫卡） | 2273XWG | 2273XWG | 3030XWG |
| 神话（橙卡） | 4545XWG | 4545XWG | 6061XWG |

## 获取XWG方法

**领空投**：进游戏会获得系统赠送的1张白卡及4本经验书，通过系统回收可以获得XWG

**做任务**：每天任务可以获得任务积分，任务积分可以转换成XWG

**十连抽**：十连抽抽取高级卡牌，可以通过交易所获得XWG

**远征质押**：把拥有的卡牌进行远征质押可以获得XWG

**战斗**：战斗胜利可以获得XWG
