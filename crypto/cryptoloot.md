# Cryptoloot (`cryptoloot.com`)

Script: `https://raw.githubusercontent.com/Crypto-Loot/cryptoloot/master/lib/crypta.js`

This script is classified as "cryptomining" for the following reasons:

### Policy Review

1. The main website `https://cryptoloot.com` describes its service as a javascript crypto miner.

> Crypto-Loot offers a Browser based web miner for the Monero Blockchain

### Technical Review

1. Script contains an implementation of the cryptonight hash algorithm

```
function _0x45bcc2() {
  var w = new Worker(CRLT["CRYPTONIGHT_WORKER_BLOB"]);
  _0x293514[_0x57ed("0x4b")](w);
  w["onmessage"] = _0x5a4854;
  setTimeout(function() {
    _0xe5c8f6(w);
  }, 2E3);
}
```
