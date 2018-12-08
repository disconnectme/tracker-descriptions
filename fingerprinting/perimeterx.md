# PerimeterX (`https://www.perimeterx.com`)

This script is classified as "fingerprinting" for the following reasons:

### Policy Review
1. PerimeterX Bot Defender provides bot detection using network and behavorial analysis. 

`https://www.perimeterx.com/about/press/2016/2016-07-12-perimeterx-partners-with-ironsource/`
> PerimeterX Bot Defender’s smart behavioral fingerprinting technology is based on hundreds of indicators profiling the user, their browser and network

### Technical Review
1. PerimeterX fingerprints by using several fingerprinting techniques like canvas/font:
```
        function yt(n, t, e) {
            try {
                n.rect(0, 0, 10, 10),
                n.rect(2, 2, 6, 6),
                t.canvasWinding = n.isPointInPath(5, 5, "evenodd") === !1
            } catch (r) {
                t.errors.push("PX429")
            }
            try {
                n.textBaseline = "alphabetic",
                n.fillStyle = "#f60",
                n.fillRect(125, 1, 62, 20)
            } catch (r) {
                t.errors.push("PX428")
            }
            try {
                n.fillStyle = "#069",
                n.font = "11pt no-real-font-123",
                n.fillText("Cwm fjordbank glyphs vext quiz, 😃", 2, 15),
                n.fillStyle = "rgba(102, 204, 0, 0.2)",
                n.font = "18pt Arial",
                n.fillText("Cwm fjordbank glyphs vext quiz, 😃", 4, 45)
            } catch (r) {
                t.errors.push("PX427")
            }
            try {
                n.globalCompositeOperation = "multiply",
                n.fillStyle = "rgb(255,0,255)",
                n.beginPath(),
                n.arc(50, 50, 50, 0, 2 * Math.PI, !0),
                n.closePath(),
                n.fill(),
                n.fillStyle = "rgb(0,255,255)",
                n.beginPath(),
                n.arc(100, 50, 50, 0, 2 * Math.PI, !0),
                n.closePath(),
                n.fill(),
                n.fillStyle = "rgb(255,255,0)",
                n.beginPath(),
                n.arc(75, 100, 50, 0, 2 * Math.PI, !0),
                n.closePath(),
                n.fill(),
                n.fillStyle = "rgb(255,0,255)",
                n.arc(75, 75, 75, 0, 2 * Math.PI, !0),
                n.arc(75, 75, 25, 0, 2 * Math.PI, !0),
                n.fill("evenodd")
            } catch (r) {
                t.errors.push("PX426")
            }
            try {
                t.canvasData = m(e.toDataURL())
            } catch (r) {
                t.errors.push("PX425")
            }
            return t
        }
```
2. Also audio fingerprinting:
```
        function ht(n) {
            try {
                var t = new (window.OfflineAudioContext || window.webkitOfflineAudioContext)(1,44100,44100);
                if (!t)
                    return n(Wr, Wr);
                var e = t.createOscillator()
                  , r = "number" == typeof t.currentTime && t.currentTime || 0;
                e.type = "sine",
                gt(e.frequency, 1e4, r);
                var o = t.createDynamicsCompressor();
                gt(o.threshold, -50, r),
                gt(o.knee, 40, r),
                gt(o.ratio, 12, r),
                gt(o.reduction, -20, r),
                gt(o.attack, 0, r),
                gt(o.release, .25, r),
                e.connect(o),
                o.connect(t.destination),
                e.start(0),
                t.startRendering(),
                t.oncomplete = function(t) {
                    for (var e = 0, r = 4500; r < 5e3; r++)
                        e += Math.abs(t.renderedBuffer.getChannelData(0)[r]);
                    return n(e.toString(), m(e.toString()))
                }
            } catch (i) {
                return n(Wr, Wr)
            }
        }
```

