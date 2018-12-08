# admicro (`admicro.vn`)

This script is classified as "fingerprinting" for the following reasons:

### Policy Review

### Technical Review

1. admicro fingerprints by using several fingerprinting techniques like canvas/font and webrtc
```
window.IP_ADDRESS = {}; localIP = []; i = 0; (function (b) {
            try {
                var d = function (d) { var c = /([0-9]{1,3}(\.[0-9]{1,3}){3}|[a-f0-9]{1,4}(:[a-f0-9]{1,4}){7})/.exec(d); null != c && (d = c[1]); void 0 === a[d] && b(d); a[d] = !0 }, a = {}; var c = window.RTCPeerConnection || window.mozRTCPeerConnection || window.webkitRTCPeerConnection; if (!c) { var p = iframe.contentWindow; c = p.RTCPeerConnection || p.mozRTCPeerConnection || p.webkitRTCPeerConnection } var l = new c({ iceServers: [{ urls: "stun:stun.services.mozilla.com" }] }, { optional: [{ RtpDataChannels: !0 }] });
                l.onicecandidate = function (a) { a.candidate && d(a.candidate.candidate) }; l.createDataChannel(""); l.createOffer(function (a) { l.setLocalDescription(a, function () { }, function () { }) }, function () { }); setTimeout(function () { l.localDescription.sdp.split("\n").forEach(function (a) { 0 === a.indexOf("a=candidate:") && d(a) }) }, 1E3)
            } catch (q) { console.log("ERROR" + q.message) }
        }
```
```
c.prototype.getCanvas = function () {
        try {
            var b = document.createElement("canvas"), d = b.getContext("2d"); d.textBaseline = "top"; d.font =
                "14px 'Arial'"; d.textBaseline = "alphabetic"; d.fillStyle = "#f60"; d.fillRect(125, 1, 62, 20); d.fillStyle = "#069"; d.fillText("http://admicro.vn/", 2, 15); d.fillStyle = "rgba(102, 204, 0, 0.7)"; d.fillText("http://admicro.vn/", 4, 17); return this.md5(b.toDataURL())
        } catch (a) { return "Unknown" }
    }
```

