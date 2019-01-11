# Minescripts (`minescripts.info`)

This domain is classified as "cryptomining" for the following reasons:

### Policy Review

1. TBD

### Technical Review
Minescripts has been identified using the following domains:
- minescripts.info
- sslverify.info

Observered on: http://expert4help.ru
- CPU utilization
    - Baseline load: 453.47%
    - Cryptomining script blocked: 12.74%

Raw log:
```
{
    "WhenNotBlocked": {
        "test_domain": "http://expert4help.ru",
        "isBlockingMiners": false,
        "miners": [
            "minescripts.info",
            "cdn.minescripts.info"
        ],
        "miner_requests": [
            "https://cdn.minescripts.info/c/wKjM.js"
        ],
        "run_stats": {
            "cpu": 453.47300396727,
            "memory": "652.1 MB"
        },
        "workers_created": [
            "blob:https://api.sslverify.info/3688505a-ede5-4f5c-8880-0fd53b6b0fdd",
            "blob:https://api.sslverify.info/3688505a-ede5-4f5c-8880-0fd53b6b0fdd",
            "blob:https://api.sslverify.info/3688505a-ede5-4f5c-8880-0fd53b6b0fdd",
            "blob:https://api.sslverify.info/3688505a-ede5-4f5c-8880-0fd53b6b0fdd",
            "blob:https://api.sslverify.info/3688505a-ede5-4f5c-8880-0fd53b6b0fdd",
            "blob:https://api.sslverify.info/3688505a-ede5-4f5c-8880-0fd53b6b0fdd"
        ]
    },
    "WhenBlocked": {
        "test_domain": "http://expert4help.ru",
        "isBlockingMiners": true,
        "miners": [
            "minescripts.info",
            "cdn.minescripts.info"
        ],
        "miner_requests": [
            "https://cdn.minescripts.info/c/wKjM.js"
        ],
        "run_stats": {
            "cpu": 12.740271885062246,
            "memory": "581.2 MB"
        },
        "workers_created": []
    }
}
```