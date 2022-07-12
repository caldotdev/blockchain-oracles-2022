# <span class="flex"> <img src="/chainlink-symbol-blue.svg" class="w-8 mr-4" />VRF - random number generator 🎲</span>

*Why is randomness a problem?* 🤔

used for...
- **NFTs**: generation of attributes
- **Gaming**: matchmaking, critical hits, draw order, random events,..
- **Process Ordering**: public sales, auctions,..
- **Entity Selection**: random picker

optimally the generated numbers would be..
- actually random 😅 (as close as possible)
- verifiable via cryptographic proof
- tamper proof
- scalable & cheap (if you are a dev 👨🏻‍💻)

<!--
# verifiable
- es waere gut, wenn jeder Interaktionsteilnehmer selbst pruefen koennte, ob alles fair war
-->

---

# <span class="flex"> <img src="/chainlink-symbol-blue.svg" class="w-8 mr-4" />VRF 🎲</span>

*How does we use it?*

```solidity
unit256 public randomResult;
function fulfillRandomness(uint256 requestId, unit256[] randomness) internal override {
      randomResult = (randomness[0] % 50) + 1;
}
```

Fulfilling request isn't free:
- gas price
- callback gas
- verification gas
- gas lane
- callback gas limit

<!--
- gas lane: maximum and gas, welches man bereit ist fuer eine request zu zahlen
-->

---

# <span class="flex"> <img src="/chainlink-symbol-blue.svg" class="w-8 mr-4" />VRF 🎲</span>

 <div class="container mx-auto flex flex-column justify-center h-auto">
    <div class="mb-2">
        <img src="/chainlink-vrf.svg" class="h-50 rounded object-center"/>
        <a href="https://chain.link/chainlink-vrf" class="italic text-xs">Source</a>
    </div>
</div>

<br />

- on-chain block data is used as input
- random results is verified on-chain **before** it can be consumed

<br />

### ⇢ this is an advantagous paradigm even for off-chain applications
