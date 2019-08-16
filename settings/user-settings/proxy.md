---
title: Proxy
---

```js
// Pref : 0706 : remove paths when sending URLs to PAC scripts (FF51+)
// CVE-2017-5384 : Information disclosure via Proxy Auto-Config (PAC)
// [1] https://bugzilla.mozilla.org/1255474
// Does not need to be set as its false by default
// BUG : This locks proxy settings from the panel
// BUG-Fix : Fixed in defaulting section
// MIGRATED : To defaulting section
// WARNING : Do not change this settings here or proxy settings will be locked
//lockPref("network.proxy.autoconfig_url.include_path", false);

// Pref : Send DNS request through SOCKS when SOCKS proxying is in use
// https://trac.torproject.org/projects/tor/wiki/doc/TorifyHOWTO/WebBrowsers
// BUG : This lock proxy settings from the panel
// BUG-Fix : Fixed with defaulting section
// MIGRATED : To defaulting section
// WARNING : Do not change this settings here or proxy settings will be locked
//lockPref("network.proxy.socks_remote_dns", true);
```
