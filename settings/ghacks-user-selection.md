---
title: Ghacks User-selection
---

# Ghacks User-selection

```js
// Pref : 0335 : disable Telemetry Coverage [FF64+]
// [1] https://blog.mozilla.org/data/2018/08/20/effectively-measuring-search-in-firefox/
lockPref("toolkit.coverage.endpoint.base", "");
lockPref("toolkit.coverage.opt-out", true); // [HIDDEN PREF]

// DOWNLOADS
// Pref : 2652: disable adding downloads to the system's "recent documents" list
lockPref("browser.download.manager.addToRecentDocs", false); //do not disable
// Pref : 2653: disable hiding mime types (Options>General>Applications) not associated with a plugin
lockPref("browser.download.hide_plugins_without_extensions", false); //do not disable

// Pref : 2617: remove webchannel whitelist
// Default value:
// "https://content.cdn.mozilla.net https://input.mozilla.org https://support.mozilla.org https://install.mozilla.org"
lockPref("webchannel.allowObject.urlWhitelist", "");

// Pref : 2730b: disable offline cache on insecure sites (FF60+)
// [1] https://blog.mozilla.org/security/2018/02/12/restricting-appcache-secure-contexts/
lockPref("browser.cache.offline.insecure.enable", false); // default: false in FF62+

// Pref : 2614: limit HTTP redirects (this does not control redirects with HTML meta tags or JS)
// [NOTE] A low setting of 5 or less will probably break some sites (e.g. gmail logins)
// To control HTML Meta tag and JS redirects, use an extension.
// Default: 20
lockPref("network.http.redirection-limit", 10);

// Pref : 2731: enforce websites to ask whether to store data for offline use
// [1] https://support.mozilla.org/questions/1098540
// [2] https://bugzilla.mozilla.org/959985
lockPref("offline-apps.allow_by_default", false);

// EXTENSIONS
// Pref : 2660: lock down allowed extension directories
// [SETUP-CHROME] This will break extensions that do not use the default XPI directories
// [1] https://mike.kaply.com/2012/02/21/understanding-add-on-scopes/
// [1] archived: https://archive.is/DYjAM
lockPref("extensions.enabledScopes", 5); // (hidden pref)
// Breaks all default themes (including dark) starting with FF68.0+

// Tor-compatibility-patch
lockPref("extensions.autoDisableScopes", 15); //Tor value must be 0
// Pref : 2663: enable warning when websites try to install add-ons
// [SETTING] Privacy & Security>Permissions>Warn you when websites try to install add-ons
lockPref("xpinstall.whitelist.required", true); // default: true

// Pref : 2306: disable push notifications (FF44+)
// web apps can receive messages pushed to them from a server, whether or
// not the web app is in the foreground, or even currently loaded
// [1] https://developer.mozilla.org/docs/Web/API/Push_API
lockPref("dom.push.enabled", false);
lockPref("dom.push.connection.enabled", false);
lockPref("dom.push.serverURL", ""); //default "wss://push.services.mozilla.com/"
lockPref("dom.push.userAgentID", "");

// Pref : 2683: block top level window data: URIs (FF56+)
// [1] https://bugzilla.mozilla.org/1331351
// [2] https://www.wordfence.com/blog/2017/01/gmail-phishing-data-uri/
// [3] https://www.fxsitecompat.com/en-CA/docs/2017/data-url-navigations-on-top-level-window-will-be-blocked/
lockPref("security.data_uri.block_toplevel_data_uri_navigations", true); // default: true in FF59+

// Pref : 2618: disable exposure of system colors to CSS or canvas (FF44+)
// [NOTE] see second listed bug: may cause black on black for elements with undefined colors
// [1] https://bugzilla.mozilla.org/buglist.cgi?bug_id=232227,1330876
lockPref("ui.use_standins_for_native_colors", true); // (hidden pref)
// Fix for widget.content.gtk-theme-override;Adwaita:light

// Pref : 0403: disable individual unwanted/unneeded parts of the Kinto blocklists
// What is Kinto?: https://wiki.mozilla.org/Firefox/Kinto#Specifications
// As Firefox transitions to Kinto, the blocklists have been broken down into entries for certs to be
// revoked, extensions and plugins to be disabled, and gfx environments that cause problems or crashes
lockPref("services.blocklist.onecrl.collection", ""); // revoked certificates
lockPref("services.blocklist.addons.collection", "");
lockPref("services.blocklist.plugins.collection", "");
lockPref("services.blocklist.gfx.collection", "");

// Pref : disable showing about:blank as soon as possible during startup (FF60+)
// When default true (FF62+) this no longer masks the RFP resizing activity
// [1] https://bugzilla.mozilla.org/1448423
lockPref("browser.startup.blankWindow", false);

// Pref : 2428: enforce DOMHighResTimeStamp API
// [WARNING] Required for normalization of timestamps and any timer resolution mitigations
lockPref("dom.event.highrestimestamp.enabled", true); // default: true

// Pref : 0516 : disable Onboarding (FF55+)
// Onboarding is an interactive tour/setup for new installs/profiles and features. Every time
// about:home or about:newtab is opened, the onboarding overlay is injected into that page
// [NOTE] Onboarding uses Google Analytics [2], and leaks resource://URIs [3]
// [1] https://wiki.mozilla.org/Firefox/Onboarding
// [2] https://github.com/mozilla/onboard/commit/db4d6c8726c89a5d6a241c1b1065827b525c5baf
// [3] https://bugzilla.mozilla.org/863246#c154
// Pref : URL that kicks off the UI tour
lockPref("privacy.trackingprotection.introURL", "");

// Pref : 0703 : disable HTTP Alternative Services (FF37+)
// [1] https://www.ghacks.net/2015/08/18/a-comprehensive-list-of-firefox-privacy-and-security-settings/#comment-3970881
// [2] https://www.mnot.net/blog/2016/03/09/alt-svc
lockPref("network.http.altsvc.enabled", false);
lockPref("network.http.altsvc.oe", false);

// Pref : 0709 : disable using UNC (Uniform Naming Convention) paths (FF61+)
// [1] https://trac.torproject.org/projects/tor/ticket/26424
lockPref("network.file.disable_unc_paths", true); // (hidden pref)

// Pref : 0710 : disable GIO as a potential proxy bypass vector
// Gvfs/GIO has a set of supported protocols like obex, network, archive, computer, dav, cdda,
// gphoto2, trash, etc. By default only smb and sftp protocols are accepted so far (as of FF64)
// [1] https://bugzilla.mozilla.org/1433507
// [2] https://trac.torproject.org/23044
// [3] https://en.wikipedia.org/wiki/GVfs
// [4] https://en.wikipedia.org/wiki/GIO_(software)
lockPref("network.gio.supported-protocols", ""); // (hidden pref)

// Pref : 0809 : disable location bar suggesting "preloaded" top websites (FF54+)
// [1] https://bugzilla.mozilla.org/1211726
lockPref("browser.urlbar.usepreloadedtopurls.enabled", false);

// Pref : 0810 : disable location bar making speculative connections (FF56+)
// [1] https://bugzilla.mozilla.org/1348275
lockPref("browser.urlbar.speculativeConnect.enabled", false);

// Pref : 0850e: disable location bar one-off searches (FF51+)
// [1] https://www.ghacks.net/2016/08/09/firefox-one-off-searches-address-bar/
lockPref("browser.urlbar.oneOffSearches", false);

// Pref : 0911 : prevent cross-origin images from triggering an HTTP-Authentication prompt (FF55+)
// [1] https://bugzilla.mozilla.org/1357835
lockPref("network.auth.subresource-img-cross-origin-http-auth-allow", false); //Deprecated Active

// Pref : 1030 : disable favicons in shortcuts
// URL shortcuts use a cached randomly named .ico file which is stored in your
// profile/shortcutCache directory. The .ico remains after the shortcut is deleted.
// If set to false then the shortcuts use a generic Firefox icon
lockPref("browser.shell.shortcutFavicons", false);

// Pref : 1032 : disable favicons in web notifications
lockPref("alerts.showFavicons", false); // default: false

// Pref : 1201 : disable old SSL/TLS "insecure" renegotiation (vulnerable to a MiTM attack)
// [WARNING] <2% of secure sites do NOT support the newer "secure" renegotiation, see [2]
// [1] https://wiki.mozilla.org/Security:Renegotiation
// [2] https://www.ssllabs.com/ssl-pulse/
lockPref("security.ssl.require_safe_negotiation", true);

// Pref : 1205 : disable TLS1.3 0-RTT (round-trip time) (FF51+)
// [1] https://github.com/tlswg/tls13-spec/issues/1001
// [2] https://blog.cloudflare.com/tls-1-3-overview-and-q-and-a/
lockPref("security.tls.enable_0rtt_data", false); // (FF55+ default true)

// Pref : 1272 : display advanced information on Insecure Connection warning pages
// Only works when it's possible to add an exception
// i.e. it doesn't work for HSTS discrepancies (https://subdomain.preloaded-hsts.badssl.com/)
// [TEST] https://expired.badssl.com/
lockPref("browser.xul.error_pages.expert_bad_cert", true);

// Pref : 1407 : disable special underline handling for a few fonts which you will probably never use [RESTART]
// Any of these fonts on your system can be enumerated for fingerprinting.
// [1] http://kb.mozillazine.org/Font.blacklist.underline_offset
lockPref("font.blacklist.underline_offset", "");

// Pref : 1408 : disable graphite which FF49 turned back on by default
// In the past it had security issues. Update: This continues to be the case, see [1]
// [1] https://www.mozilla.org/security/advisories/mfsa2017-15/#CVE-2017-7778
lockPref("gfx.font_rendering.graphite.enabled", false);

// Pref : 1604 : CROSS ORIGIN: control the amount of information to send (FF52+)
// Pref : 0=send full URI (default), 1=scheme+host+port+path, 2=scheme+host+port
lockPref("network.http.referer.XOriginTrimmingPolicy", 0);

// Pref : 1605 : ALL: disable spoofing a referer
// [WARNING] Spoofing effectively disables the anti-CSRF (Cross-Site Request Forgery) protections that some sites may rely on
// Default false
lockPref("network.http.referer.spoofSource", false);

// Pref : 1801 : set default plugin state (i.e. new plugins on discovery) to never activate
// Pref : 0=disabled, 1=ask to activate, 2=active - you can override individual plugins
lockPref("plugin.default.state", 1);
lockPref("plugin.defaultXpi.state", 1);

// Pref : 2026 : disable canvas capture stream (FF41+)
// [1] https://developer.mozilla.org/docs/Web/API/HTMLCanvasElement/captureStream
lockPref("canvas.capturestream.enabled", false);

// Pref : 2027 : disable camera image capture (FF35+)
// [1] https://trac.torproject.org/projects/tor/ticket/16339
lockPref("dom.imagecapture.enabled", false); // default: false

// Pref : 2028 : disable offscreen canvas (FF44+)
// [1] https://developer.mozilla.org/docs/Web/API/OffscreenCanvas
lockPref("gfx.offscreencanvas.enabled", false); // default: false

// Pref : 2201 : prevent websites from disabling new window features
// [1] http://kb.mozillazine.org/Prevent_websites_from_disabling_new_window_features
lockPref("dom.disable_window_open_feature.close", true);
lockPref("dom.disable_window_open_feature.location", true); // default: true
lockPref("dom.disable_window_open_feature.menubar", true);
lockPref("dom.disable_window_open_feature.minimizable", true);
lockPref("dom.disable_window_open_feature.personalbar", true); // bookmarks toolbar
lockPref("dom.disable_window_open_feature.resizable", true); // default: true
lockPref("dom.disable_window_open_feature.status", true); // status bar - default: true
lockPref("dom.disable_window_open_feature.titlebar", true);
lockPref("dom.disable_window_open_feature.toolbar", true);

// Pref : 2202 : prevent scripts from moving and resizing open windows
lockPref("dom.disable_window_move_resize", true);

// Pref : 2426 : disable Intersection Observer API (FF53+)
// Took almost a year to complete, three versions late to 'stable' (as default false),
// number 1 cause of crashes in nightly numerous times, and is (primarily) an
// ad network API for "ad viewability checks" down to a pixel level
// [1] https://developer.mozilla.org/docs/Web/API/Intersection_Observer_API
// [2] https://w3c.github.io/IntersectionObserver/
// [3] https://bugzilla.mozilla.org/1243846
lockPref("dom.IntersectionObserver.enabled", false);

// Pref : 2601 : prevent accessibility services from accessing your browser [RESTART]
// [SETTING] Privacy & Security>Permissions>Prevent accessibility services from accessing your browser
// [1] https://support.mozilla.org/kb/accessibility-services
lockPref("accessibility.force_disabled", 1);

// Pref : 2606 : disable UITour backend so there is no chance that a remote page can use it
lockPref("browser.uitour.enabled", false);
lockPref("browser.uitour.url", "");

// Pref : 2611 : disable middle mouse click opening links from clipboard
// [1] https://trac.torproject.org/projects/tor/ticket/10089
// [2] http://kb.mozillazine.org/Middlemouse.contentLoadURL
lockPref("middlemouse.contentLoadURL", false);

// Pref : 2616 : remove special permissions for certain mozilla domains (FF35+)
// [1] resource://app/defaults/permissions
lockPref("permissions.manager.defaultsUrl", "");
```
