---
title: Do not track
---

# Do not track

```js
// Set to enforce; choice was left to the user in a previous version
lockPref("privacy.donottrackheader.enabled", true);

// Pref : 1610: (36+) set DNT "value" to "not be tracked" (FF21+)
// [1] http://kb.mozillazine.org/Privacy.donottrackheader.value
// [-] https://bugzilla.mozilla.org/1042135#c101
lockPref("privacy.donottrackheader.value", 1);
```
