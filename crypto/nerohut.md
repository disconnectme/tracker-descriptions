# NeroHut (`nerohut.com`)

This domain is classified as "cryptomining" for the following reasons:

### Policy Review

1. TBD

### Technical Review
NeroHut has been identified using the following domains:
- nerohut.com
- nhsrv.cf

Observered on: http://webfreer.com
- CPU utilization
    - Baseline load: 29.76%
    - Cryptomining script blocked: 13.37%

Raw log:
```
{
    "WhenNotBlocked": {
        "test_webpage": "http://webfreer.com",
        "isBlockingMiners": false,
        "miners": [
            "nerohut.com"
        ],
        "miner_requests": [
            "https://nerohut.com/srv/?key=0fc7e2a5fe172c0b7fb20ab45eaf39eb"
        ],
        "run_stats": {
            "cpu": 29.7563025210084,
            "memory": "512.3 MB"
        },
        "workers_created": [
            "blob:https://nhsrv.cf/94672bb1-4bf9-424c-9b7b-3fbdf8ca91c3",
            "blob:https://nhsrv.cf/aa8ff8f1-4c0d-4638-91c3-235f4af81377",
            "blob:https://nhsrv.cf/b4529bd4-051d-4573-a063-6b80bbbe8d3a",
            "blob:https://nhsrv.cf/8510f1a8-3839-48be-892e-c763b3aed4a7",
            "blob:https://nhsrv.cf/90574b5f-a020-4e8d-9a72-ab4439ef033f",
            "blob:https://nhsrv.cf/fcf17cda-1602-4ac1-871e-ca48cf27233f",
            "blob:https://nhsrv.cf/801026e5-4063-4081-8072-f8dbdd8b99ac",
            "blob:https://nhsrv.cf/b4ff23c1-013f-4919-83bf-e5dc18fd0019",
            "blob:https://nhsrv.cf/b8762dd8-dfdd-40e4-bff4-2e9758b29807",
            "blob:https://nhsrv.cf/9064275f-418c-4c0f-9ec4-756dddc15c09",
            "blob:https://nhsrv.cf/116ec33c-375b-44cc-a34e-15cc4173b4c0",
            "blob:https://nhsrv.cf/323faead-22bc-4082-a959-5d02b881dbb3"
        ]
    },
    "WhenBlocked": {
        "test_webpage": "http://webfreer.com",
        "isBlockingMiners": true,
        "miners": [
            "nerohut.com"
        ],
        "miner_requests": [
            "https://nerohut.com/srv/?key=0fc7e2a5fe172c0b7fb20ab45eaf39eb"
        ],
        "run_stats": {
            "cpu": 13.36764705882353,
            "memory": "410.8 MB"
        },
        "workers_created": []
    }
}
```