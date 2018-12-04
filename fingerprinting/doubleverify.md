# DoubleVerify (`doubleverify.com`)

Script: `https://cdn.doubleverify.com/dv-measurements234.js`

This script is classified as "fingerprinting" for the following reasons:

### Policy Review

1. Doubleverify states they attempt to identify particular devices - `https://www.doubleverify.com/privacy/`

> and other data including browser configuration parameters such as browser language and session storage and local storage settings, and characteristics of your device such as the CPU class and time zone setting.

> Device identification technology, which analyzes device parameters collected as described above, including IP address and browser header information, to probabilistically identify a particular device. 


### Technical Review

1. Script uses canvas/font fingerprinting to fingerprint users

```
var canvasDrawBG = c.g.createElement("canvas");
if (canvasDrawBG.getContext && canvasDrawBG.getContext("2d")) {
  var ctx = canvasDrawBG.getContext("2d");
  /** @type {string} */
  ctx.textBaseline = "top";
  /** @type {string} */
  ctx.font = "14px Arial";
  /** @type {string} */
  ctx.textBaseline = "alphabetic";
  /** @type {string} */
  ctx.fillStyle = "#f60";
  ctx.fillRect(0, 0, 62, 20);
  /** @type {string} */
  ctx.fillStyle = "#069";
  ctx.fillText("!image!", 2, 15);
  /** @type {string} */
  ctx.fillStyle = "rgba(102, 204, 0, 0.7)";
  ctx.fillText("!image!", 4, 17);
  return canvasDrawBG.toDataURL();
}
```

2. Script probes device properties to attempt to fingerprint users

```
sortable.push(["lang", this.navigator.language || navigator.browserLanguage]);
sortable.push(["tz", d.i.getTimezoneOffset()]);
sortable.push(["hss", this.Yt() ? "1" : "0"]);
sortable.push(["hls", this.Xt() ? "1" : "0"]);
sortable.push(["odb", typeof this.o.openDatabase]);
sortable.push(["cpu", this.navigator.cpuClass || ""]);
sortable.push(["pf", this.navigator.platform || ""]);
sortable.push(["dnt", this.navigator.doNotTrack || ""]);
sortable.push(["canv", this.Ps()]);
```
