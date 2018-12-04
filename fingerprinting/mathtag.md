# MediaMath (`mediamath.com`)

Script: `https://mathid.mathtag.com/d/i.js`

This script is classified as "fingerprinting" for the following reasons:

### Policy Review

1. Mediamath purchased Tactads, a provider of "cookieless and cross-device targeting technologies" - `https://www.mediamath.com/news/press-release-mediamath-acquires-tactads-to-enable-cookieless-cross-device-targeting-and-measurement/`

> MediaMath, the creator of the TerminalOne Marketing Operating System™ for digital marketers, today announced its acquisition of Tactads, provider of cookieless and cross-device targeting technologies. Integrated into TerminalOne, these technologies will provide advertisers the ability to communicate with consumers and unify marketing efforts across smartphone, tablet, laptop, desktop, and other devices...

> Tactads, a France-based company, has developed proprietary software that uses sophisticated algorithms to identify and associate devices using statistical techniques...

2. MediaMath privacy policy states they use cookieless tracking and specifically states they profile installed fonts and "similar information" - https://www.mediamath.com/privacy-policy/#Section-2

> The MediaMath ID can be a cookie ID (a unique ID assigned randomly by MediaMath to an unrecognized browser), a mobile advertising ID (a unique ID assigned by the mobile operating system, e.g. Apple ID for Advertising or Android Advertising ID), an OTT TV Device Identifier for Advertising (a unique ID assigned by an OTT TV provider, e.g., Roku ID for Advertising), or a statistical ID (created by MediaMath). We use information about your computer or device to generate the statistical ID, including your operating system, user-agent string, Internet Protocol (“IP”) address, installed fonts, and similar information. This information makes your computer or device distinct enough for our systems to determine within a reasonable probability that they are encountering the same computer or device over time, including in environments where MediaMath cookies are not supported.

### Technical Review

1. Script uses canvas/font fingerprinting to fingerprint users

```
var render = function(type) {
  /**
    * @param {string} id
    * @return {?}
    */
  function init(id) {
    /** @type {boolean} */
    var result = false;
    /** @type {number} */
    var i = 0;
    for (; i < baseFonts.length; i++) {
      if (target == "dom") {
        /** @type {string} */
        s.style.fontFamily = id + "," + baseFonts[i];
        o.appendChild(s);
        /** @type {boolean} */
        var val = s.offsetWidth != defaultWidth[baseFonts[i]] || s.offsetHeight != defaultHeight[baseFonts[i]];
        o.removeChild(s);
      } else {
        if (target == "canvas") {
          /** @type {string} */
          ctx.font = part + " " + id + "," + baseFonts[i];
          /** @type {boolean} */
          val = ctx.measureText(testString).width != defaultWidth[baseFonts[i]];
        }
      }
      /** @type {(boolean|undefined)} */
      result = result || val;
    }
    return result;
  }
  /** @type {!Array} */
  var baseFonts = ["monospace", "sans-serif", "serif"];
  /** @type {string} */
  var testString = "mmmmmmmmmmlli";
  /** @type {string} */
  var part = "72px";
  if (type != "dom") {
    /** @type {string} */
    var target = "canvas";
    /** @type {!Element} */
    var result = document.createElement("canvas");
    /** @type {string} */
    result.width = "100";
    /** @type {string} */
    result.height = "100";
    globalContainer$jscomp$0.appendChild(result);
  }
  if (!result || typeof result.getContext != "function") {
    /** @type {string} */
    target = "dom";
    var o = globalContainer$jscomp$0;
    /** @type {!Element} */
    var s = document.createElement("span");
    /** @type {string} */
    s.style.fontSize = part;
    /** @type {string} */
    s.innerHTML = testString;
    var defaultWidth = {};
    var defaultHeight = {};
    /** @type {number} */
    var i = 0;
    for (; i < baseFonts.length; i++) {
      s.style.fontFamily = baseFonts[i];
      o.appendChild(s);
      defaultWidth[baseFonts[i]] = s.offsetWidth;
      defaultHeight[baseFonts[i]] = s.offsetHeight;
      o.removeChild(s);
    }
  } else {
    var ctx = result.getContext("2d");
    defaultWidth = {};
    /** @type {number} */
    i = 0;
    for (; i < baseFonts.length; i++) {
      /** @type {string} */
      ctx.font = part + " " + baseFonts[i];
      defaultWidth[baseFonts[i]] = ctx.measureText(testString).width;
    }
  }
  /** @type {function(string): ?} */
  this.detect = init;
  /** @type {(string|undefined)} */
  this.method = target;
};
```

2. Script probes device properties to attempt to fingerprint users

```
/** @type {string} */
resultsFromProbes$jscomp$0["bcap"] = [$mime_type, prKey, getWindowData$jscomp$0("navigator", "cookieEnabled")].join("|");
}();
!function() {
/** @type {string} */
resultsFromProbes$jscomp$0["lges"] = [getWindowData$jscomp$0("navigator", "browserLanguage"), getWindowData$jscomp$0("navigator", "language"), getWindowData$jscomp$0("navigator", "userLanguage")].join("|");
}();
!function() {
/** @type {string} */
resultsFromProbes$jscomp$0["ob"] = [getWindowData$jscomp$0("navigator", "appCodeName"), getWindowData$jscomp$0("navigator", "appName"), getWindowData$jscomp$0("navigator", "platform"), getWindowData$jscomp$0("navigator", "cpuClass")].join("|");
}();

var get_date_offset = function(date) {
  /** @type {number} */
  var t = -date.getTimezoneOffset();
  return t !== null ? t : 0;
};

!function() {
  /** @type {string} */
  resultsFromProbes$jscomp$0["sc"] = [getWindowData$jscomp$0("screen", "width"), getWindowData$jscomp$0("screen", "height"), getWindowData$jscomp$0("screen", "availWidth"), getWindowData$jscomp$0("screen", "availHeight"), getWindowData$jscomp$0("screen", "pixelDepth"), getWindowData$jscomp$0("screen", "deviceXDPI"), getWindowData$jscomp$0("screen", "deviceYDPI")].join("|");
}();

PluginDetect$jscomp$0.java = {
mimeType : "application/x-java-applet",
classID : "clsid:8AD9C840-044E-11D1-B3E9-00805F499D93",
DTKclassID : "clsid:CAFEEFAC-DEC7-0000-0000-ABCDEFFEDCBA",
DTKmimeType : "application/npruntime-scriptable-plugin;DeploymentToolkit",

PluginDetect$jscomp$0.quicktime = {
mimeType : ["video/quicktime", "application/x-quicktimeplayer", "image/x-macpaint", "image/x-quicktime"],
progID : "QuickTimeCheckObject.QuickTimeCheck.1",
progID0 : "QuickTime.QuickTime",
classID : "clsid:02BF25D5-8C17-4B23-BC80-D3488ABDDC6B",
minIEver : 7,

PluginDetect$jscomp$0.devalvr = {
mimeType : "application/x-devalvrx",
progID : "DevalVRXCtrl.DevalVRXCtrl.1",
classID : "clsid:5D2CF9D0-113A-476B-986F-288B54571614",

PluginDetect$jscomp$0.flash = {
mimeType : ["application/x-shockwave-flash", "application/futuresplash"],
progID : "ShockwaveFlash.ShockwaveFlash",
classID : "clsid:D27CDB6E-AE6D-11CF-96B8-444553540000",

```
