---
title: DNS
---

# DNS

```js
// Pref : 0707 : disable (or setup) DNS-over-HTTPS (DoH) (FF60+)
// TRR = Trusted Recursive Resolver
// .mode: 0=off, 1=race, 2=TRR first, 3=TRR only, 4=race for stats,
// but always use native result, 5=explicitly turn it off
// [WARNING] DoH bypasses hosts and gives info to yet another party (e.g. Cloudflare)
// [1] https://www.ghacks.net/2018/04/02/configure-dns-over-https-in-firefox/
// [2] https://hacks.mozilla.org/2018/05/a-cartoon-intro-to-dns-over-https/
// BUG : This seems to disable socks_remote_dns ?! need to check with wireshark
// If true, just settings urls to null should be enough to disable
// Without impacting socks_remote_dns
// -------
// Mode 0 is only off because right now that's the default, the default can change.
// Mode 5 means explicitly off, regardless of default.
// https://wiki.mozilla.org/Trusted_Recursive_Resolver
// https://nakedsecurity.sophos.com/2018/08/07/mozilla-faces-resistance-over-dns-privacy-test/#comment-5193521
// -------
lockPref("network.trr.mode", 5);
lockPref("network.trr.bootstrapAddress", "");
lockPref("network.trr.uri", "");

// If your OS or ISP does not support IPv6, there is no reason to have this preference set to false.
lockPref("network.dns.disableIPv6", true);

// Pref : Disable DNS pre-fetching
// http://kb.mozillazine.org/Network.dns.disablePrefetch
// https://developer.mozilla.org/en-US/docs/Web/HTTP/Controlling_DNS_prefetching
lockPref("network.dns.disablePrefetch", true);
lockPref("network.dns.disablePrefetchFromHTTPS", true);
```
