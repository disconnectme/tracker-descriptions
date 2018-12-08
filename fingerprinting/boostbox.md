# BoostBox (`https://www.boostbox.com.br/`)

This script is classified as "fingerprinting" for the following reasons:

### Policy Review

### Technical Review
```
      keys = this.userAgentKey(keys);
      keys = this.languageKey(keys);
      keys = this.colorDepthKey(keys);
      keys = this.deviceMemoryKey(keys);
      keys = this.pixelRatioKey(keys);
      keys = this.hardwareConcurrencyKey(keys);
      keys = this.screenResolutionKey(keys);
      keys = this.availableScreenResolutionKey(keys);
      keys = this.timezoneOffsetKey(keys);
      keys = this.sessionStorageKey(keys);
      keys = this.localStorageKey(keys);
      keys = this.indexedDbKey(keys);
      keys = this.addBehaviorKey(keys);
      keys = this.openDatabaseKey(keys);
      keys = this.cpuClassKey(keys);
      keys = this.platformKey(keys);
      keys = this.doNotTrackKey(keys);
      keys = this.pluginsKey(keys);
      keys = this.canvasKey(keys);
      keys = this.webglKey(keys);
      keys = this.webglVendorAndRendererKey(keys);
      keys = this.adBlockKey(keys);
      keys = this.hasLiedLanguagesKey(keys);
      keys = this.hasLiedResolutionKey(keys);
      keys = this.hasLiedOsKey(keys);
      keys = this.hasLiedBrowserKey(keys);
      keys = this.touchSupportKey(keys);
      keys = this.customEntropyFunction(keys);
```

```
    ge : function(value) {
      /** @type {string} */
      var ret = "";
      (new Fingerprint2({
        excludeDeviceMemory : true,
        excludeJsFonts : true,
        excludeFlashFonts : true,
        detectScreenOrientation : false,
        preprocessor : function(css, type) {
          return "user_agent" === css ? parse() : type;
        }
      })).get(function(a, canCreateDiscussions) {
        ret = $Flab.sha256.hxd(a);
      });
      return ret;
    }
```