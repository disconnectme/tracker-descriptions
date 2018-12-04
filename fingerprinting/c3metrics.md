# C3 Metrics (`c3metrics.com`)

This script is classified as "fingerprinting" for the following reasons:

### Policy Review

1. C3 Metrics claims that can universally track users with their fingerprinting technology - `https://c3metrics.com/privacy/`

> Tracking: Universal Identifier with fingerprinting technology unifies the consumer journey into a private & secure infrastructure.

> Data Unification: Distribute attribution credit algorithmically with the Attribution Data Cloud’s constantly updating machine learning.

### Technical Review

1. C3 Metrics appears to be heavily based on an open source fingerprinting library: `https://github.com/Valve/fingerprintjs2`
```
            getPixelRatio: function() {
                return window[_0x4dfd("0x118")] || ""
            },
            screenResolutionKey: function(d) {
                return this[_0x4dfd("0xec")][_0x4dfd("0x119")] ? d : this[_0x4dfd("0x11a")](d)
            },
            getScreenResolution: function(d) {
                var x;
                return x = this[_0x4dfd("0xec")][_0x4dfd("0x11b")] && window[_0x4dfd("0x110")][_0x4dfd("0x73")] > window[_0x4dfd("0x110")].width ? [window.screen[_0x4dfd("0x73")], window[_0x4dfd("0x110")][_0x4dfd("0x72")]] : [window[_0x4dfd("0x110")][_0x4dfd("0x72")], window[_0x4dfd("0x110")][_0x4dfd("0x73")]],
                d[_0x4dfd("0x108")]({
                    key: _0x4dfd("0x11c"),
                    value: x
                }),
                d
            },
            availableScreenResolutionKey: function(d) {
                return this[_0x4dfd("0xec")][_0x4dfd("0x11d")] ? d : this.getAvailableScreenResolution(d)
            },
            getAvailableScreenResolution: function(d) {
                var x;
                return window[_0x4dfd("0x110")][_0x4dfd("0x11e")] && window[_0x4dfd("0x110")].availHeight && (x = this[_0x4dfd("0xec")].detectScreenOrientation ? window[_0x4dfd("0x110")][_0x4dfd("0x11f")] > window[_0x4dfd("0x110")][_0x4dfd("0x11e")] ? [window.screen[_0x4dfd("0x11f")], window[_0x4dfd("0x110")][_0x4dfd("0x11e")]] : [window[_0x4dfd("0x110")][_0x4dfd("0x11e")], window[_0x4dfd("0x110")][_0x4dfd("0x11f")]] : [window[_0x4dfd("0x110")][_0x4dfd("0x11f")], window[_0x4dfd("0x110")][_0x4dfd("0x11e")]]),
                void 0 !== x && d.addPreprocessedComponent({
                    key: _0x4dfd("0x120"),
                    value: x
                }),
                d
            },
            timezoneOffsetKey: function(d) {
                return this[_0x4dfd("0xec")][_0x4dfd("0x121")] || d.addPreprocessedComponent({
                    key: _0x4dfd("0x122"),
                    value: (new Date)[_0x4dfd("0x123")]()
                }),
                d
            }
```

