# Audited Media (`https://auditedmedia.com/`)

This script is classified as "fingerprinting" for the following reasons:

### Policy Review

1. https://auditedmedia.com/ 

### Technical Review

1. Script uses canvas/font to fingerprint users and sends calculated fingerprint id and other properties back to Audited Media
```
10: [function(g, u, p) {
        (function() {
            var d = g("../lib_managed/lodash");
            g("./helpers");
            var b = g("murmurhash").v3
              , c = g("browser-cookie-lite")
              , a = "undefined" !== typeof p ? p : this
              , l = window
              , h = navigator
              , q = screen
              , u = document;
            a.hasSessionStorage = function() {
                try {
                    return !!l.sessionStorage
                } catch (f) {
                    return !0
                }
            }
            ;
            a.hasLocalStorage = function() {
                try {
                    return !!l.localStorage
                } catch (f) {
                    return !0
                }
            }
            ;
            a.localStorageAccessible = function() {
                if (!a.hasLocalStorage())
                    return !1;
                try {
                    return l.localStorage.setItem("modernizr", "modernizr"),
                    l.localStorage.removeItem("modernizr"),
                    !0
                } catch (f) {
                    return !1
                }
            }
            ;
            a.hasCookies = function(a) {
                a = a || "testcookie";
                return d.isUndefined(h.cookieEnabled) ? (c.cookie(a, "1"),
                "1" === c.cookie(a) ? "1" : "0") : h.cookieEnabled ? "1" : "0"
            }
            ;
            a.isCanvasSupported = function() {
                var a = document.createElement("canvas");
                return !(!a.getContext || !a.getContext("2d"))
            }
            ;
            a.getCanvasFp = function() {
                var a = []
                  , c = document.createElement("canvas");
                c.width = 2E3;
                c.height = 200;
                c.style.display = "inline";
                var b = c.getContext("2d");
                b.rect(0, 0, 10, 10);
                b.rect(2, 2, 6, 6);
                a.push("canvas winding:" + (!1 === b.isPointInPath(5, 5, "evenodd") ? "yes" : "no"));
                b.textBaseline = "alphabetic";
                b.fillStyle = "#f60";
                b.fillRect(125, 1, 62, 20);
                b.fillStyle = "#069";
                b.fillText("Cwm fjordbank glyphs vext quiz, \ud83d\ude03", 2, 15);
                b.fillStyle = "rgba(102, 204, 0, 0.7)";
                b.font = "18pt Arial";
                b.fillText("Cwm fjordbank glyphs vext quiz, \ud83d\ude03", 4, 45);
                b.globalCompositeOperation = "multiply";
                b.fillStyle = "rgb(255,0,255)";
                b.beginPath();
                b.arc(50, 50, 50, 0, 2 * Math.PI, !0);
                b.closePath();
                b.fill();
                b.fillStyle = "rgb(0,255,255)";
                b.beginPath();
                b.arc(100, 50, 50, 0, 2 * Math.PI, !0);
                b.closePath();
                b.fill();
                b.fillStyle = "rgb(255,255,0)";
                b.beginPath();
                b.arc(75, 100, 50, 0, 2 * Math.PI, !0);
                b.closePath();
                b.fill();
                b.fillStyle = "rgb(255,0,255)";
                b.arc(75, 75, 75, 0, 2 * Math.PI, !0);
                b.arc(75, 75, 25, 0, 2 * Math.PI, !0);
                b.fill("evenodd");
                a.push("canvas fp:" + c.toDataURL());
                return a.join("~")
            }
            ;
            a.detectSignature = function(f) {
                var d = a.isCanvasSupported() ? a.getCanvasFp() : ""
                  , m = "" != c.cookie("__utma") ? c.cookie("__utma") : c.cookie("_ga");
                d = [h.userAgent, [q.height, q.width, q.colorDepth].join("x"), (new Date).getTimezoneOffset(), a.hasSessionStorage(), a.hasLocalStorage(), d, m];
                m = [];
                if (h.plugins)
                    for (var l = 0; l < h.plugins.length; l++) {
                        for (var g = [], p = 0; p < h.plugins[l].length; p++)
                            g.push([h.plugins[l][p].type, h.plugins[l][p].suffixes]);
                        m.push([h.plugins[l].name + "::" + h.plugins[l].description, g.join("~")])
                    }
                return b(d.join("###") + "###" + m.sort().join(";"), f)
            }
            ;
            a.detectTimezone = function() {
                return ""
            }
            ;
            a.detectViewport = function() {
                var a = l
                  , b = "inner";
                "innerWidth"in l || (b = "client",
                a = u.documentElement || u.body);
                return a[b + "Width"] + "x" + a[b + "Height"]
            }
            ;
            a.detectDocumentSize = function() {
                var a = u.documentElement
                  , b = Math.max(a.clientWidth, a.offsetWidth, a.scrollWidth);
                a = Math.max(a.clientHeight, a.offsetHeight, a.scrollHeight);
                return isNaN(b) || isNaN(a) ? "" : b + "x" + a
            }
            ;
            a.detectBrowserFeatures = function(b) {
                var f, m = {
                    pdf: "application/pdf",
                    qt: "video/quicktime",
                    realp: "audio/x-pn-realaudio-plugin",
                    wma: "application/x-mplayer2",
                    dir: "application/x-director",
                    fla: "application/x-shockwave-flash",
                    java: "application/x-java-vm",
                    gears: "application/x-googlegears",
                    ag: "application/x-silverlight"
                }, g = {};
                if (h.mimeTypes && h.mimeTypes.length)
                    for (f in m)
                        if (Object.prototype.hasOwnProperty.call(m, f)) {
                            var p = h.mimeTypes[m[f]];
                            g[f] = p && p.enabledPlugin ? "1" : "0"
                        }
                g.inpriv = "" != c.cookie("privAu") ? c.cookie("privAu") : 0;
                g.abd = "" != c.cookie("abdAu") ? c.cookie("abdAu") : 0;
                "unknown" !== typeof h.javaEnabled && !d.isUndefined(h.javaEnabled) && h.javaEnabled() && (g.java = "1");
                d.isFunction(l.GearsFactory) && (g.gears = "1");
                g.res = q.width + "x" + q.height;
                g.cd = q.colorDepth;
                g.cookie = a.hasCookies(b);
                return g
            }
        }
        )()
    }
```
