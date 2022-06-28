# Centralized Oracle: [Provable](https://provable.xyz/)

- easy to use via simple queries
- blockchain agnostic
  - most services live off-chain
  - designed for a blockchain context
  - *Provable HTTP API is also provided*
- military-grade security
  - multiple types of **authenticity proofs**: software & hardware based
  - ensure delivery of untampered data
- 🚨 _"Most of the software we produce is open-source and all the critical pieces are published as such."_
- certified
  - entire external audit trail is published
  - as of now the link is broken 🤔
- flexible & efficient


<!-- 
- einfache queries
- designed für Anwendung im Blockchain-Bereich
- hauptsächlich Ethereum
- hohe Sicherheitsstandards
- Open Source?
- externe Audits
-->

---

# 📦 [Provable](https://provable.xyz/) Query [Example](https://docs.provable.xyz/#ethereum-quick-start)


```solidity{all|9|13}
pragma solidity ^0.4.22;
import "github.com/provable-things/ethereum-api/provableAPI_0.4.25.sol";

contract ExampleContract is usingProvable {

  // rest of contract omitted for brevity...

   function updatePrice() payable {
       if (provable_getPrice("URL") > this.balance) {
           LogNewProvableQuery("Provable query was NOT sent, please add some ETH to cover for the query fee");
       } else {
           LogNewProvableQuery("Provable query was sent, standing by for the answer..");
           provable_query("URL", "json(https://api.pro.coinbase.com/products/ETH-USD/ticker).price");
       }
   }
}
```

<v-click>

Request: `(<data source type>, <query>, <optional: authenticity proof type>)`

</v-click>


<!-- 
- `payable` modifier means that the function can process transactions with non-zero Ether value
- falls der momentane Query-Preis höher als das Guthaben ist ablehnen
- sonst query
-->

---
layout: center
---

# Data Sources & Authenticity Proof Types

<div class="container mx-auto flex flex-column justify-center">
    <div class="mb-4">
        <img src="/provable-auth-types.png" class="h-80 rounded object-center"/>
        <a href="https://docs.provable.xyz/#data-sources" class="italic text-xs">Source</a>
    </div>
</div>

<!--
# URL
- Zugriff auf jegliche API oder Webpage
- zweiter Parameter JSON als POST

# Random
- zufällige Zahl aus Trusted Execution Environment

# WolframAlpha
- direkter Zugriff auf API
- Ergebnisse als String zurückgegeben

# IPFS
- file Inhalt von einem IPFS storage wird geliefert
- IPFS: peer-to-peer hypermedia protocol

# computation
- Ausführung von Anwendung oder script auf sandboxed Amazon Web Service virtual machine
- Ergebnis bis zu 2500 Zeichen lang

-->

---

# [Provable](https://provable.xyz/)'s Downsides

- limited EVM functionality
- inefficient handling of
  - opcodes
  - precompiles
  - precision bound floats
- high gas costs
- absence of confidentiality & privacy...
- ...

In addition to Provable's centralized infrastructure this does sound suboptimal 🤔