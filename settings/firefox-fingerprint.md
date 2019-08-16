---
title: FireFox fingerprint
---

# FireFox fingerprint

```js
// Pref : Enable hardening against various fingerprinting vectors (Tor Uplift project)
// https://wiki.mozilla.org/Security/Tor_Uplift/Tracking
// https://bugzilla.mozilla.org/show_bug.cgi?id=1333933
lockPref("privacy.resistFingerprinting", true);

// Pref : 4503 : disable mozAddonManager Web API (FF57+)
// [NOTE] As a side-effect in FF57-59 this allowed extensions to work on AMO. In FF60+ you also need
// to sanitize or clear extensions.webextensions.restrictedDomains (see 2662) to keep that side-effect
// [1] https://bugzilla.mozilla.org/buglist.cgi?bug_id=1384330,1406795,1415644,1453988
lockPref("privacy.resistFingerprinting.block_mozAddonManager", true);
```
