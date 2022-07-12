---
layout: two-cols-one-heading
---

# <span class="flex"> <img src="/chainlink-symbol-blue.svg" class="w-8 mr-4" />Data Feeds 💾</span>

::left::

are..

- easy to add via `chainlink` npm package
- smart contracts consuming data feeds can be written in ..
  * [Solidity](https://docs.soliditylang.org/en/v0.8.15/)
  * [web3.js](https://github.com/ChainSafe/web3.js) / [ether.js](https://github.com/ethers-io/ethers.js/)
  * [Web3.py](https://github.com/ethereum/web3.py) / [Vyper](https://github.com/vyperlang/vyper)
  * ...
- some examples of **available data feeds** on Ethereum
  * `AAPL / USD`: [Contract](https://etherscan.io/address/0xc929ad75B72593967DE83E7F7Cda0493458261D9)
  * `BTC / ETH`: [Contract](https://etherscan.io/address/0xdeb288F737066589598e9214E782fa5A8eD689e8)
- migrated to [ENS](https://docs.ens.domains/)

::right::

Feeds are currently available on:
- Ethereum
- BNB
- Polygon (Matic)
- HECO
- Gnosis (xDai)
- Avalanche
- Fantom
- Arbitrum
- Harmony
- Optimism
- Moonrive
- *Solana*

<!-- 
- koennen on- und off-chain verwendet werden 
- ausser SOL alles EVM chains

## Warum ist das wichtig?
- erlaubt chains bridging zu erleichtern
- multichain ecosystem..
-->

---

# <span class="flex"> <img src="/chainlink-symbol-blue.svg" class="w-8 mr-4" />Solidity Example 💾</span>

```solidity
pragma solidity ^0.8.7;

import "@chainlink/contracts/src/v0.8/interfaces/AggregatorV3Interface.sol";

contract PriceConsumerV3 {

    AggregatorV3Interface internal priceFeed;

    constructor() {
        priceFeed = AggregatorV3Interface(0x8A753747A1Fa494EC906cE90E9f37563A8AF630e);
    }

   function getLatestPrice() public view returns (int) {
        (
            /*uint80 roundID*/,
            int price,
            /*uint startedAt*/,
            /*uint timeStamp*/,
            /*uint80 answeredInRound*/
        ) = priceFeed.latestRoundData();
        return price;
    }
}
```

<!-- 
- als kleine Vorbereitung auf Leo's praesentation

* Network: Rinkeby
* Aggregator: ETH/USD
* Address: 0x8A753747A1Fa494EC906cE90E9f37563A8AF630e 
-->

---

# <span class="flex"> <img src="/chainlink-symbol-blue.svg" class="w-8 mr-4" />Python Example 💾</span>

```python
web3 = Web3(Web3.HTTPProvider('https://rinkeby.infura.io/v3/<infura_project_id>'))
abi = '...'
addr = '0x8A753747A1Fa494EC906cE90E9f37563A8AF630e'
contract = web3.eth.contract(address=addr, abi=abi)
latestData = contract.functions.latestRoundData().call()
# latestData now holds the latest ETH/USD price
```

<br />

- the API is quite simple
- everyone should find a language to utilize it with
