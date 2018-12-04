

# Webmine (`webmine.cz`)

Script: `https://authedwebmine.cz/377c8c5a-614e-4175-a4e3-9d41d607c855`

This script is classified as "cryptomining" for the following reasons:

### Policy Review

1. The main website `https://webmine.cz` describes its service as a javascript crypto miner.

> We are offering a Javascript miner that can be embedded to your website. This way you can earn XMR with spare CPU power of your website users in the following three steps.

### Technical Review

1. Script contains an implementation of the cryptonight hash algorithm

```
var CryptonightWASMWrapper = function() {
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
