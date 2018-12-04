# CoinHive (`coinhive.com`)

Script: `https://coinhive.com/lib/coinhive.min.js`

This script is classified as "cryptomining" for the following reasons:

### Policy Review

1. The main website `https://coinhive.com` describes its service as a javascript crypto miner.

> Coinhive offers a JavaScript miner for the Monero Blockchain (Why Monero?) that you can embed in your website

### Technical Review

1. Script contains an implementation of the cryptonight hash algorithm

```
var CryptonightWASMWrapper = function() {
  this.ctx = _cryptonight_create();
  /** @type {number} */
  this.throttleWait = 0;
  /** @type {number} */
  this.throttledStart = 0;
  /** @type {number} */
  this.throttledHashes = 0;
  this.workThrottledBound = this.workThrottled.bind(this);
  /** @type {null} */
  this.currentJob = null;
  /** @type {!Uint8Array} */
  this.target = new Uint8Array([255, 255, 255, 255, 255, 255, 255, 255]);
  var inputs = Module.HEAPU8.buffer;
  /** @type {!Uint8Array} */
  this.input = new Uint8Array(inputs, Module._malloc(84), 84);
  /** @type {!Uint8Array} */
  this.output = new Uint8Array(inputs, Module._malloc(32), 32);
  self.postMessage("ready");
  self.onmessage = this.onMessage.bind(this);
};
```

2. Network traffic shows script submitting hashes

```
up: {"type":"submit","params":{"version":7,"job_id":"448165886709466","nonce":"0bf389de","result":"eefccc790cd55f37715d07ffedd97652737eff274c747795e4c66f2da81ad100"}}

down: {"type":"hash_accepted","params":{"hashes":256}}
```
