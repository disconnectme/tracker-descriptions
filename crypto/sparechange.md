# Sparechange (`Sparechange.io`)

Script: `http://sparechange.io/static/sparechange.js`

This script is classified as "cryptomining" for the following reasons:

### Policy Review

1. The main website `https://sparechange.io` describes its service as a javascript crypto miner.

> A browser based crypto currency miner for your website When a user visits your website, a JavaScript miner runs in their browser, using a tiny amount of power to mine crypto currencies for you.

### Technical Review

1. Script contains a miner object that configures and starts a javascript miner

```
function Miner(spareChangeApiKey, p1, p2) {
    this.spareChangeApiKey = spareChangeApiKey;
    //determine if parameters are old or new style
    if( p1 === parseInt(p1, 10) || typeof p1 == 'undefined' || p1 === null) {
        //p1 = numThreads. p2 = throttlePct
        this.numThreads = p1 || navigator.hardwareConcurrency || 8;
        this.throttlePct = p2 || 0.0;
        this.optIn = 'no';
        this.optInDelay = 10;
        this.targetShares = 0;
    } else {
        //parse p1 as userOptions
        var userOptions = p1;
        this.numThreads = userOptions.numberOfThreads || navigator.hardwareConcurrency || 8;
        this.throttlePct = userOptions.throttlePercent || 0.0;
        if(userOptions.optIn) {
            this.optIn = userOptions.optIn.type || 'no';
            this.optInDelay = userOptions.optIn.delay || 10;
        } else {
            this.optIn = 'no';
            this.optInDelay = 10;
        }
        this.targetShares = userOptions.targetShares || 0;
    }

    this.numSharesSubmitted = 0;
    this.running = false;
    this.optedOut = false;
    this.hashesPerSecond = 0;
    this.hashesDone = 0;
    this.hashesPerThread = {};
    this.connectionOpen = false;
    this.token = null;
}
```
