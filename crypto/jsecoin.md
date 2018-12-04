# JSECoin (`jsecoin.com`)

Script: `https://load.jsecoin.com/server/load/1103/vk.com/`

This script is classified as "cryptomining" for the following reasons:

### Policy Review

1. The main website `https://jsecoin.com` describes its service as a javascript crypto miner.

> JSECoin could be the solution. An unobtrusive code snippet is placed on your site which then runs the JSECoin miner on your visitors' devices whilst they browse your website.

### Technical Review

1. Script checks available crypto APIs before performing various actions

```
      if (window.crypto && window.crypto.subtle) {
        stringify(code, i).then(function(i) {
          if (i.substr(0, d) === get(d)) {
            /** @type {boolean} */
            rc = true;
            call_user_is_writing(selector + "," + i + "," + options.pubID + "," + options.uniq + "," + options.siteID + "," + options.subID);
            console.log("Found Hash! : " + i);
          }
        });
      } else {
```
