---
title: Controversial
---

```js
// Pref : Disable IndexedDB (disabled)
// Pref : 2720: enforce IndexedDB (IDB)
// IDB is required for extensions and Firefox internals (even before FF63)
// To control *website* IDB data, control allowing cookies and service workers, or use
// Temporary Containers. To mitigate *website* IDB, FPI helps (4001), and/or sanitize
// on close (Offline Website Data, see User Settings : History settings) or on-demand (Ctrl-Shift-Del),
// or automatically via an extension. Note that IDB currently cannot be sanitized by host.
// IndexedDB could be used for tracking purposes, but is required for :
// twitter and many sites, some addons, old version of uBlock, session manager in certain cases
// This is mitigated with addons and sanitize settings
// IndexedDB is a low-level API for client-side storage of significant amounts of structured data,
// including files/blobs. This API uses indexes to enable high-performance searches of this data.
// While Web Storage is useful for storing smaller amounts of data, it is less useful for storing
// larger amounts of structured data. IndexedDB provides a solution. This is the main landing page
// for MDN's IndexedDB coverage — "here we provide links to the full API reference and usage guides,
// browser support details, and some explanation of key concepts"
// Also this is cleaned by privacy.clearOnShutdown.offlineApps"
// https://blog.mozilla.org/addons/2018/08/03/new-backend-for-storage-local-api/
// https://developer.mozilla.org/en-US/docs/IndexedDB
// https://en.wikipedia.org/wiki/Indexed_Database_API
// https://wiki.mozilla.org/Security/Reviews/Firefox4/IndexedDB_Security_Review
// http://forums.mozillazine.org/viewtopic.php?p=13842047
// https://github.com/pyllyukko/user.js/issues/8
lockPref("dom.indexedDB.enabled", true); //default true

// Pref : indexedDB Loggingq - disabled for performance
//lockPref("dom.indexedDB.logging.details", false); //default true
//lockPref("dom.indexedDB.logging.enabled", false); //default true

// Pref : 2516 : disable PointerEvents
// [1] https://developer.mozilla.org/en-US/docs/Web/API/PointerEvent
lockPref("dom.w3c_pointer_events.enabled", false);

// Pref : 0702 : disable HTTP2 (which was based on SPDY which is now deprecated)
// HTTP2 adds "multiplexing" and "server push", but does nothing to enhance
// privacy, and in fact opens up a number of server-side fingerprinting opportunities
// [1] https://http2.github.io/faq/
// [2] https://blog.scottlogic.com/2014/11/07/http-2-a-quick-look.html
// [3] https://queue.acm.org/detail.cfm?id=2716278
// [4] https://github.com/ghacksuserjs/ghacks-user.js/issues/107
// Disabled because of [4]
//lockPref("network.http.spdy.enabled", false);
//lockPref("network.http.spdy.enabled.deps", false);
//lockPref("network.http.spdy.enabled.http2", false);
```
