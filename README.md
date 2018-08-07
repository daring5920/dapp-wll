## #dapp-wll ##

在SLU公链上设计了强大、安全的智能合约实现WLL，WLL总量100亿，根据算力由矿工自行挖出。智能合约启用了数学安全模型，并对owner、manager进行了约定，对于矿工来说涉及的功能有：
1. 确认矿工资格。用户购买矿机后，系统会调用智能合约approveMiner(address _miner)进行矿工资格确认。
2. 矿工挖矿。符合条件后开始挖矿，用户随时提币确认，确认后调用智能合约mint(address _receiver, uint256 _value)，矿工进帐【提币确认前，用户需要自己提供SILUBIUM地址，可以直接使用交易所的钱包地址】。
3. WLL价值传递。挖矿确认后的代币可以随时在交易所变现。
4. WLL地址上需要充值一定的SLU作为GAS费用，不论金额大小，每次操作需消耗手续费 0.02SLU左右，执行操作时预估费用，操作结束后会以GAS找零方式退回未用完的手续费。

### 接口调用说明 ###
