# <span class="flex"> <img src="/chainlink-symbol-blue.svg" class="w-8 mr-4" />Architecture - Request Model 🙋🏻‍♂️</span>

<div class="container mx-auto flex flex-column justify-center">
    <div class="mb-4">
        <img src="/chainlink-request-model.png" class="h-auto w-400 rounded object-center"/>
        <a href="https://docs.chain.link/docs/architecture-request-model/" class="italic text-xs">Source</a>
    </div>
</div>

- **ChainlinkClient** available in the smart contract library
- **LINK Token**
  * used to **compensate node operators**
  * `ERC 667` compliant [src](https://github.com/ethereum/EIPs/issues/677)
- **Oracle Contract**
- **Oracle Node** (*Off-chain*)

<!-- 
- die smart contract library kann mittels npm, yarn, pnpm,... installiert werden
## `ERC 667`
- erlaubt Tokens an contracts geschickt zu werden
- triggered logic beim erhalt der tokens innerhalb einer Transaktion

-->

---

# <span class="flex"> <img src="/chainlink-symbol-blue.svg" class="w-8 mr-4" />Architecture - Request Model 🙋🏻‍♂️</span>

<div class="container mx-auto flex flex-column justify-center">
    <div class="mb-4">
        <img src="/chainlink-request-model.png" class="h-auto w-400 rounded object-center"/>
        <a href="https://docs.chain.link/docs/architecture-request-model/" class="italic text-xs">Source</a>
    </div>
</div>

#### **Oracle Contract**
- is contacted if sufficient LINK is available
- owned by node operators
- `Request`
  * `oracle address`, `job ID` & `callback function`
- `Fulfillment`
  * `fulfillOracleRequest` function returns result of request to specified callback

<!-- 
- oracle contract gehoert node operator
- callback function?
-->

---

# <span class="flex"> <img src="/chainlink-symbol-blue.svg" class="w-8 mr-4" />Architecture - Request Model 🙋🏻‍♂️</span>

<div class="container mx-auto flex flex-column justify-center">
    <div class="mb-4">
        <img src="/chainlink-request-model.png" class="h-auto w-400 rounded object-center"/>
        <a href="https://docs.chain.link/docs/architecture-request-model/" class="italic text-xs">Source</a>
    </div>
</div>

#### **Oracle Node**
- listens to events emitted by the corresponding smart contract: `OracleRequest` event
- creates request and converts result into blockchain compatible data

[*if you want to run a node* 😎](https://docs.chain.link/docs/running-a-chainlink-node/)


