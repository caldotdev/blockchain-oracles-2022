# <span class="flex"> <img src="/chainlink-symbol-blue.svg" class="w-8 mr-4" />Any API 📦</span>

- enables smart contracts to access **ANY** external API
- uses decentralized oracle network

```solidity {1,18|3|4|5-9|10-12|14-15|all}
...

function requestVolumeData() public returns (bytes32 requestId) {
  Chainlink.Request memory req = buildChainlinkRequest(jobId, address(this), this.fulfill.selector);

  req.add('get', 'https://min-api.cryptocompare.com/data/pricemultifull?fsyms=ETH&tsyms=USD');
     
  req.add('path', 'RAW,ETH,USD,VOLUME24HOUR');

  // Multiply the result by 1000000000000000000 to remove decimals
  int256 timesAmount = 10**18;
  req.addInt('times', timesAmount);

  // Sends the request
  return sendChainlinkRequest(req, fee);
}

...

```

<!--
- wir wollen Handelsvolumen von ETH/USD abfragen
- erstellen request
- fuegen URL und attribute hinzu
- normalisieren
- schicken request raus
-->
