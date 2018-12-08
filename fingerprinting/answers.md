# Answers Cloud Services / Foresee (`https://www.foresee.com/`)

This script is classified as "fingerprinting" for the following reasons:

### Policy Review

1. Answers Cloud Services uses the Foresee SDK (subsidiary of Answers Cloud Services) to provide a variety of services including fingerprinting. Their developer documentation includes definitions of their cookie passed parameters, including fingerprint:
> Fingerprint (fp) - Anonymous identifier for site visitor, used for cookieless tracking in 19.4.0+.

### Technical Review

1. Script uses canvas to perform font fingerprinting and calculate other properties
```
  var Binder = function(bridge) {
    /** @type {string} */
    this.browser = bridge;
    /** @type {string} */
    this.sig = "not detected";
    this.ready = new self.FSEvent;
    this._detect();
  };
  /**
   * @return {undefined}
   */
  Binder.prototype._detect = function() {
    var value;
    var iterator = _.proxy(function(obj) {
      /** @type {string} */
      this.sig = obj;
      this.ready.fire(obj);
    }, this);
    /** @type {!Array} */
    var textBuffer = [];
    /** @type {!Navigator} */
    var n = navigator;
    var browser = this.browser;
    if (win != win.top) {
      /** @type {(Array<string>|null)} */
      var quoteMatch = location.search.match(/uid=([\d\w]*)/i);
      if (quoteMatch && quoteMatch[1]) {
        /** @type {string} */
        value = quoteMatch[1];
      }
    }
    if (!(value && "not detected" != value || !browser.supportsLocalStorage)) {
      value = localStorage.getItem("_fsPRINT_");
    }
    if (!value) {
      textBuffer = self.trim(navigator.userAgent.replace(/[0-9\.\/\\\(\);_\-]*/gi, "")).split(" ");
      textBuffer.push(n.language || "");
      textBuffer.push(n.hardwareConcurrency || "");
      textBuffer.push(n.platform || "");
      textBuffer.push(n.vendor || "");
      textBuffer.push(n.appName || "");
      textBuffer.push(n.maxTouchPoints || "");
      textBuffer.push(n.doNotTrack || "false");
      textBuffer.push(browser.os.name || "false");
      textBuffer.push(browser.os.version || "false");
      textBuffer.push(this._getCanvasPrint());
      value = self.md5(textBuffer.join(""));
      this.sig = value;
      if (browser.supportsLocalStorage) {
        localStorage.setItem("_fsPRINT_", value);
      }
    }
    _.nextTick(function() {
      iterator(value);
    });
  };
  /**
   * @return {?}
   */
  Binder.prototype._getCanvasPrint = function() {
    try {
      /** @type {!Element} */
      var canvasDrawBG = document.createElement("canvas");
      var ctx = canvasDrawBG.getContext("2d");
      /** @type {string} */
      var tempPathText = "ForeSee,CloudUser <canvas> 1.0";
      return canvasDrawBG.width = 250, canvasDrawBG.height = 30, ctx.textBaseline = "top", ctx.font = "14px 'Arial'", ctx.textBaseline = "alphabetic", ctx.fillStyle = "#f60", ctx.fillRect(125, 1, 62, 20), ctx.fillStyle = "#069", ctx.fillText(tempPathText, 2, 15), ctx.fillStyle = "rgba(102, 204, 0, 0.7)", ctx.fillText(tempPathText, 4, 17), canvasDrawBG.toDataURL();
    } catch (t) {
      return "nocanvas";
    }
  };
  /** @type {function(string): undefined} */
  self.Fingerprint = Binder;
```
