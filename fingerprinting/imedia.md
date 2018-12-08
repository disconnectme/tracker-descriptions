# iMedia (`http://www.imedia.cz/`)

This script is classified as "fingerprinting" for the following reasons:

### Policy Review

### Technical Review
```
      Plugin.prototype.get = function(options) {
        var name;
        for (name in options) {
          this._options[name] = options[name];
        }
        this._log("-> get fingerprint with options", this._options);
        /** @type {string} */
        var ret = "";
        ret = ret + this._getText();
        if (this._options.canvas) {
          ret = ret + this._getCanvas();
        }
        return ret;
      };
```

```
      Plugin.prototype._drawCanvas = function() {
        /** @type {!Element} */
        var canvas = document.createElement("canvas");
        var ctx = canvas.getContext("2d");
        /** @type {string} */
        ctx.fillStyle = "#fff";
        ctx.fillRect(0, 0, canvas.width, canvas.height);
        /** @type {!Array} */
        var strings = [];
        /** @type {number} */
        var rown = 25;
        [32, 64, 96, 256].forEach(function(i, canCreateDiscussions) {
          /** @type {string} */
          var value = "";
          /** @type {number} */
          var j = 0;
          for (; j < rown; j++) {
            /** @type {string} */
            value = value + String.fromCharCode(i + j);
          }
          strings.push(value);
        });
        [{
          "font" : "14px droid sand mono,ubuntu,serif",
          "fill" : "rgba(255, 30, 30, 0.3)",
          "stroke" : "rgba(30, 30, 255, 0.3)"
        }, {
          "font" : "12pt helvetica,arial,sans-serif",
          "fill" : "rgba(30, 255, 30, 0.3)",
          "stroke" : "rgba(255, 255, 30, 0.3)"
        }].forEach(function(label, m1) {
          /** @type {number} */
          var y = 0;
          /** @type {number} */
          var i = 0;
          ctx.font = label.font;
          ctx.fillStyle = label.fill;
          ctx.strokeStyle = label.stroke;
          strings.forEach(function(text, h1) {
            /** @type {number} */
            var ty = (1 + h1 + m1 / 3) * 20;
            ctx.strokeText(text, 0, ty);
            ctx.fillText(text, 0, ty);
          });
        });
        this._log(canvas);
        return canvas;
      };
```