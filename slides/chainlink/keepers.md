---
layout: two-cols-one-heading
---

# <span class="flex"> <img src="/chainlink-symbol-blue.svg" class="w-8 mr-4" />Keepers ⚙️</span>

> Decentralized smart contract automation

::left::

<br />
<br />

**Use Cases**

- harvest yield
- automated trading
- trigger asset distribution
- liquidations

<v-click>

- ...

</v-click>

::right::

<br />
<br />

<v-click>

**Currently supported on**

- Ethereum
- Polygon (Matic)
- BNB
- Avalanche
- Fantom

</v-click>

<!--
- will noch nicht zu viel der Smart Contract Presentation vorweg nehmen
-->

---
layout: contained-image-right
image: /chainlink-keepers-overview.png
---

# <span class="flex"> <img src="/chainlink-symbol-blue.svg" class="w-8 mr-4" />Architecture ⚙️</span>

<v-clicks>

- **Upkeeps**
  * outsourced maintenance tasks
  * must be *Keepers-compatible*
- **Keeper registry**: contract that is used to [register](https://docs.chain.link/docs/chainlink-keepers/register-upkeep/) & manage Upkeeps
- **Keepers**: Network nodes

</v-clicks>

<v-click>

<br />
<br />
<br />

### Upkeeps must be sufficiently funded using LINK 💰

</v-click>

<!--
# keeper compatible
- muessen spezielle Interfaces implementieren
- `checkUpkeep`: runs off-chain um zu ueberpruefen, ob performUpkeep ausgefuehrt werden muss
- `performUpkeep`: beinhaltet tatsaechliche Logik
-->

---

# <span class="flex"> <img src="/chainlink-symbol-blue.svg" class="w-8 mr-4" />Creating your Upkeep ⚙️</span>

Choose your trigger (not in a Twitter users way 😅..)

<v-clicks>

- **time-based**
  * scheduled using CRON
- **custom logic**
  * defined in custom smart contract

</v-clicks>

<v-click>

*Remember that we used to send funds with our requests?*
- Upkeeps are funded using the registry

</v-click>

<v-click>

### Summary

</v-click>

<v-clicks>

- Keepers provide a form of decentralized DevOps
- allow for the reduction of gas fees due to off-chain computations
  * [several](https://chainlinktoday.com/prominent-founders-examine-chainlink-keepers-role-in-defis-evolution/) protocols outsourced their maintenance tasks to Keepers
- enables gas fee prediction due to the possibility to set gas fee limits

</v-clicks>

<!--
# reducing gas fees
- checkUpkeep function verbraucht keine Gas-Fees; da off-chain

# gas fee limits
- haben wir bereits bei VRFs angesprochen
-->

<style>

p {
  margin-bottom: 0.5rem;
}

h3 {
  padding-top: 1rem;
}

</style>