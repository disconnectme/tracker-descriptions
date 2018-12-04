# Bluecava (`bluecava.com`)

Script: `https://sync.graph.bluecava.com/js/bc.js`

This script is classified as "fingerprinting" for the following reasons:

### Policy Review

1. BlueCava says that the newest version of its device-fingerprinting technology doesn't require installing cookies on users' computers. Instead, the company recognizes the unique characteristics of users' computers and then compiles information about those people's Web-surfing activity. - `https://www.mediapost.com/publications/article/166916/bluecava-touts-device-fingerprinting.html`

> Says David Norris, CEO of BlueCava, “Once we’ve identified a device, we can provide information about that device’s history so a business can decide how it wants to interact.” - `https://www.clickz.com/device-fingerprinting-firm-bluecava-makes-tracking-opt-outs-easier/46797/`

> You can reset the advertising ID we generate when we recognize your device. This will unlink your device from any of the data that has been accumulated and assigned to that ID. The effect is the same as if you had just gotten a new computer or phone. To reset your advertising ID click the button to the right. Note, that if you reset your advertising ID we will automatically apply the opt-out setting from the old ID to the new one when we create the new one, so if you have opted out above you won’t have to do that again. - `https://bluecava.com/`

2. Bluecava privacy policy states they use cookieless tracking and specifically states they profile installed fonts and "various other properties of a Screen" - `https://bluecava.com/privacy-policy`

> Qualia’s Platform enables our Clients to recognize Screens when their Users visit Sites. In order to do this, we collect information about User’s computers, mobile devices, tablets, and game consoles (“Screens”). The type of information collected via the Platform includes the type of Screen, IP address, browser version, time zone, the fonts installed, browser plug-ins and various other properties of a Screen. Qualia does not collect PII in connection with the Platform.

### Technical Review

1. Script uses canvas/font fingerprinting to fingerprint users

```
    test : function(name) {
      this.h.appendChild(this.d);
      /** @type {!Array} */
      var style = [];
      return style.name = this.s.style.fontFamily = name, style.width = this.s.offsetWidth, style.height = this.s.offsetHeight, this.h.removeChild(this.d), name = name.toLowerCase(), "serif" == name ? style.found = true : style.found = style.width != this.defaultWidth || style.height != this.defaultHeight, style;
    },
    getFontList : function(fonts) {
      this.init();
      /** @type {!Array} */
      var list = [];
      /** @type {number} */
      i = 0;
      for (; i < fonts.length; ++i) {
        if (this.test(fonts[i]).found) {
          list.push(i);
        }
      }
      return list;
    }
```

2. Script probes device properties to attempt to fingerprint users

```
    var init = function(stop) {
      if (c$jscomp$0.config.F.PDF) {
        set(c$jscomp$0.m.PDF);
      }
      if (c$jscomp$0.config.F.Ajax) {
        set(c$jscomp$0.m.Ajax);
      }
      if (c$jscomp$0.config.F.CPU) {
        set(c$jscomp$0.m.CPU);
      }
      if (c$jscomp$0.config.F.Timezone) {
        set(c$jscomp$0.m.Timezone);
      }
      if (c$jscomp$0.config.F.Gears) {
        set(c$jscomp$0.m.Gears);
      }
      if (c$jscomp$0.config.F.Languages) {
        set(c$jscomp$0.m.Languages);
      }
      if (c$jscomp$0.config.F.Plugins) {
        set(c$jscomp$0.m.Plugins);
      }
      if (c$jscomp$0.config.F.General) {
        set(c$jscomp$0.m.General);
      }
      if (c$jscomp$0.config.F.JSEngine) {
        set(c$jscomp$0.m.JSEngine);
      }
      if (c$jscomp$0.config.F.PDFReader) {
        set(c$jscomp$0.m.PDFReader);
      }
      if (c$jscomp$0.config.F.Silverlight) {
        set(c$jscomp$0.m.Silverlight);
      }
      if (c$jscomp$0.config.F.DotNet) {
        set(c$jscomp$0.m.DotNet);
      }
      if (c$jscomp$0.config.F.Display) {
        set(c$jscomp$0.m.Display);
      }
      if (c$jscomp$0.config.F.Fonts) {
        set(c$jscomp$0.m.Fonts);
      }
      if (c$jscomp$0.config.F.Fonts && c$jscomp$0.config.F.Flash) {
        c$jscomp$0.m.Flash(b, function() {
          stop();
        });
      } else {
        stop();
      }
```
