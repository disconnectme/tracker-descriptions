# Mineralt (`mineralt.io`)

This domain is classified as "cryptomining" for the following reasons:

### Policy Review

1. The main website `https://mineralt.io` describes its service as a javascript crypto miner.

> Use safe javascript browser miner to mine cryptocurrency online, using your web site visitors’ CPU power. The most effective web miner on the market with the highest mining ratio

### Technical Review
Mineralt has been identified using several different domains:
- gramombird.com
- mepirtedic.com
- besstahete.info
- feesocrald.com
- analytics.blue
- pampopholf.com
- tulip18.com
- mineralt.io
- istlandoll.com
- dinorslick.icu

Observered on: http://ictlounge.com
- CPU utilization
    - Baseline load: 388.23%
    - Cryptomining script blocked: 14.39%

Raw log:
```
{
    "WhenNotBlocked": {
        "test_webpage": "http://ictlounge.com",
        "isBlockingMiners": false,
        "miners": [
            "tulip18.com"
        ],
        "miner_requests": [
            "https://tulip18.com/amo.js"
        ],
        "run_stats": {
            "cpu": 388.2296195652174,
            "memory": "490.3 MB"
        },
        "workers_created": [
            "blob:https://ictlounge.com/3514c841-7432-4e71-951e-657d78af9455",
            "blob:https://ictlounge.com/3514c841-7432-4e71-951e-657d78af9455",
            "blob:https://ictlounge.com/3514c841-7432-4e71-951e-657d78af9455",
            "blob:https://ictlounge.com/3514c841-7432-4e71-951e-657d78af9455",
            "blob:https://ictlounge.com/3514c841-7432-4e71-951e-657d78af9455"
        ]
    },
    "WhenBlocked": {
        "test_webpage": "http://ictlounge.com",
        "isBlockingMiners": true,
        "miners": [
            "tulip18.com"
        ],
        "miner_requests": [
            "https://tulip18.com/amo.js"
        ],
        "run_stats": {
            "cpu": 14.38548197492163,
            "memory": "429.9 MB"
        },
        "workers_created": []
    }
}
```