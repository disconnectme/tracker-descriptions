# AdScore (`http://www.adscoremarketing.com/`)

This script is classified as "fingerprinting" for the following reasons:

### Policy Review

### Technical Review

```
        k = function() {
            try {
                var c = A(),
                    d = document.createElement("canvas");
                d.width = 200;
                d.height = 200;
                var b = d.getContext("2d");
                b.beginPath();
                b.rect(0, 0, 200, 200);
                b.fillStyle = "black";
                b.fill();
                var g = d.toDataURL();
                b.beginPath();
                b.rect(0, 0, 200, 200);
                b.fillStyle = "white";
                b.fill();
                var e = d.toDataURL(),
                    p = b.createLinearGradient(0, 0, 200, 0);
                p.addColorStop(0, "blue");
                p.addColorStop(1, "white");
                b.fillStyle = p;
                b.fillRect(0, 0, 200, 200);
                b.rotate(1 * Math.PI / 180);
                b.font = "14px 'Arial'";
                b.textBaseline = "alphabetic";
                b.fillStyle = "#f60";
                b.fillRect(0, 15, 200, 15);
                b.beginPath();
                b.moveTo(0, 0);
                b.quadraticCurveTo(50, 150, 180, 180);
                b.bezierCurveTo(190, -40, 100, 50, 100, 50);
                b.lineTo(30, 10);
                b.lineWidth = 1;
                b.strokeStyle = "#222222";
                b.stroke();
                b.fillStyle = "#069";
                b.fillText("mmiillII,)#!>\u26c4\u26c7\u12b9\u102a\u07f7\u058e\u17d8",
                    2, 15);
                b.fillStyle = "rgba(102,204,0,0.7)";
                b.fillText("mmiillII,)#!>\u26c4\u26c7\u12b9\u102a\u07f7\u058e\u17d8", 4, 17);
                p = d.toDataURL();
                A();
                f = A() - c;
                A();
                p = B(p.substr(p.length - 100));
                bt = B(g.substr(g.length - 100) + e.substr(e.length - 100)).substr(0, 8);
                A();
                c = [];
                c.push(bt);
                c.push(p);
                c.push("");
                c.push("");
                return c
            } catch (G) {
                return ""
            }
        }();
```
