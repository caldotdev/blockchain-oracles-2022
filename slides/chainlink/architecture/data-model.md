# <span class="flex"> <img src="/chainlink-symbol-blue.svg" class="w-8 mr-4" />Architecture - Data Model</span>

- **Data Aggregation** [*sol contract*](https://github.com/smartcontractkit/libocr/blob/master/contract/AccessControlledOffchainAggregator.sol)
  * feed is created by multiple independent operators
  * further enhanced by Off-Chain Reporting - *we talk about that later* ⏰ 
- **Shared Data Resource**
  * data feeds are built & funded by the users relying on the data
- **Decentralized Oracle Network (DON)**
  * data feeds are updated by an decentralized oracle Network
  * oracles are rewarded for publishing data
  * feeds are only updated if a minimum number of responses are returned
  * data is published during a an aggregation round

---

# <span class="flex"> <img src="/chainlink-symbol-blue.svg" class="w-8 mr-4" />DON - Components📦</span>
*three contracts..*

- **consumer**
  * use data feed
  ```js
  ...
  AggregatorV3Interface feed = AggregatorV3Interface(address);
  return feed.latestRoundData();
  ```
- **proxy**
  * on-chain
  * enable upgrades/changes of underlying aggregator w/o breaking on-chain functionality
- **aggregator**
  * receives periodic updates from oracle network
  * *if ... triggered*
    - deviation threshold
    - heartbeat threshold


<!-- 
# consumer
- beliebiger contract, der Daten von chainlink data feed konsumiert
- muss correctes interface referenzieren und verwenden\
- auch off-chain Verwendung moeglich: JS & Py
# thresholds
- deviation
  * off chain values weichen mehr als spezifiziertes delta vom on-chain Wert ab
  * festgelegte Zeit seit letztem Update vergangen
-->
