---
title: Miscellaneous
---

# Miscellaneous

```js
// Pref : Disable "Are you sure you want to leave this page?" popups on page close
// https://support.mozilla.org/en-US/questions/1043508
// Does not prevent JS leaks of the page close event.
// https://developer.mozilla.org/en-US/docs/Web/Events/beforeunload
// Disabled by default in Librefox; could be useful on some sites, e.g. banking sites
lockPref("dom.disable_beforeunload", true);

// Pref : Disable geo localisation
lockPref("permissions.default.geo", 2);
```
