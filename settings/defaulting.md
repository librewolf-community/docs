---
title: Defaulting
---

```js
// Pref : Preferred language for displaying websites.
// The first settings overflow the second one
defaultPref("privacy.spoof_english", 2);
//defaultPref("intl.accept_languages", "en-US, en"); //This make lang windows unusable

// Pref : 1606: ALL: set the default Referrer Policy
// 0=no-referer, 1=same-origin, 2=strict-origin-when-cross-origin, 3=no-referrer-when-downgrade
// [NOTE] This is only a default, it can be overridden by a site-controlled Referrer Policy
// [1] https://www.w3.org/TR/referrer-policy/
// [2] https://developer.mozilla.org/docs/Web/HTTP/Headers/Referrer-Policy
// [3] https://blog.mozilla.org/security/2018/01/31/preventing-data-leaks-by-stripping-path-information-in-http-referrers/
defaultPref("network.http.referer.defaultPolicy", 3); // (FF59+) default: 3
defaultPref("network.http.referer.defaultPolicy.pbmode", 2); // (FF59+) default: 2

// Pref : 1701: enable Container Tabs setting in preferences (see 1702) (FF50+)
// [1] https://bugzilla.mozilla.org/1279029
defaultPref("privacy.userContext.ui.enabled", true);
// Pref : 1702: enable Container Tabs (FF50+)
// [SETTING] General>Tabs>Enable Container Tabs
defaultPref("privacy.userContext.enabled", true);
// Pref : 1703: enable a private container for thumbnail loads (FF51+)
defaultPref("privacy.usercontext.about_newtab_segregation.enabled", true); // default: true in FF61+
// Pref : 1704: set long press behaviour on "+ Tab" button to display container menu (FF53+)
// 0=disables long press, 1=when clicked, the menu is shown
// 2=the menu is shown after X milliseconds
// [NOTE] The menu does not contain a non-container tab option
// [1] https://bugzilla.mozilla.org/1328756
defaultPref("privacy.userContext.longPressBehavior", 2);

// Pref : (FF57+)
defaultPref("browser.download.autohideButton", false);

// Pref : enable "Find As You Type"
defaultPref("accessibility.typeaheadfind", true);

// Pref : disable autocopy default [LINUX]
defaultPref("clipboard.autocopy", false);

// Pref : 0=none, 1-multi-line, 2=multi-line & single-line
defaultPref("layout.spellcheckDefault", 2);

// Pref : closeWindowWithLastTab
defaultPref("browser.tabs.closeWindowWithLastTab", false);

// Pref : middle-click enabling auto-scrolling [WINDOWS] [MAC]
defaultPref("general.autoScroll", false);

// Pref : 1601: ALL: control when images/links send a referer
// This breaks a lot of sites. This is mitigating by an extension.
// 0=never, 1=send only when links are clicked, 2=for links and images (default)
//defaultPref("network.http.sendRefererHeader", 1);

// Pref : 2620: enable Firefox's built-in PDF reader
// [SETTING] General>Applications>Portable Document Format (PDF)
// This setting controls if the option "Display in Firefox" in the above setting is available
// and by effect controls whether PDFs are handled in-browser or externally ("Ask" or "Open With")
// PROS:   pdfjs is lightweight, open source, and as secure/vetted as any pdf reader out there (more than most)
//         Exploits are rare (1 serious case in 4 yrs), treated seriously and patched quickly.
//         It doesn't break "state separation" of browser content (by not sharing with OS, independent apps).
//         It maintains disk avoidance and application data isolation. It's convenient. You can still save to disk.
// CONS:   You may prefer a different pdf reader for security reasons
// CAVEAT: JS can still force a pdf to open in-browser by bundling its own code (rare)
defaultPref("pdfjs.disabled", false);

// Pref : 2210: block popup windows
// [SETTING] Privacy & Security>Permissions>Block pop-up windows
defaultPref("dom.disable_open_during_load", true);

// Pref : 2203 : open links targeting new windows in a new tab instead
// User Settings : Migrated to Defaulting : Links pop-up open in new tab
// This stops malicious window sizes and some screen resolution leaks.
// You can still right-click a link and open in a new window.
// [TEST] https://people.torproject.org/~gk/misc/entire_desktop.html
// [1] https://trac.torproject.org/projects/tor/ticket/9881
defaultPref("browser.link.open_newwindow", 3);
defaultPref("browser.link.open_newwindow.restriction", 0);

// Pref : Defaulting Settings : Proxy
defaultPref("network.proxy.autoconfig_url", "");
defaultPref("network.proxy.autoconfig_url.include_path", false);
defaultPref("network.proxy.socks_remote_dns", true);
defaultPref("network.proxy.socks_version", 5);

// Pref : Defaulting Settings : Bookmark should by default open in newtab instead of
// replacing the current page
defaultPref("browser.tabs.loadBookmarksInTabs", true);

// Pref : Debugging settings
defaultPref("devtools.debugger.remote-enabled", false);
defaultPref("devtools.chrome.enabled", false);

// Pref : site_specific_overrides useragent
defaultPref("general.useragent.site_specific_overrides", false);

// Pref : Display all sections by default
defaultPref("extensions.ui.experiment.hidden", false);
// These two are not needed (they are set to true automatically when their list is empty)
//defaultPref("extensions.ui.dictionary.hidden", false);
//defaultPref("extensions.ui.locale.hidden", false);
```
