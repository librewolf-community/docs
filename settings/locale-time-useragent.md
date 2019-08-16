---
title: Locale/Time/Useragent
---

# Locale/Time/Useragent

```js
// Pref : 0864 : disable date/time picker (FF57+ default true)
// This can leak your locale if not en-US
// [1] https://trac.torproject.org/projects/tor/ticket/21787
// Does this work efficiently with resistFingerprinting ??
lockPref("dom.forms.datetime", false);

// Pref : Prevent leaking application locale/date format using JavaScript
// https://bugzilla.mozilla.org/show_bug.cgi?id=867501
// https://hg.mozilla.org/mozilla-central/rev/52d635f2b33d
// Already applied by resistFingerprinting ?
lockPref("javascript.use_us_english_locale", true);

// Pref : Set Accept-Language HTTP header to en-US regardless of Firefox localization
// https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept-Language
// Already applied by resistFingerprinting ?
lockPref("intl.regional_prefs.use_os_locales", false);

// Pref : Locale and useragent.
// Already applied by resistFingerprinting ?
lockPref("intl.locale.requested", "en-US");

// Pref : Spoof User-agent (re-enabled)
// See https://gitlab.com/librewolf-community/librewolf/issues/26
lockPref("general.useragent.override", "Mozilla/5.0 (Windows NT 6.1; rv:45.0) Gecko/20100101 Firefox/45.0, 45");

// Pref : This does not work with resistFingerprinting. Still needed for ESR.
lockPref("general.appname.override", "Netscape");
lockPref("general.appversion.override", "5.0 (Windows)");
lockPref("general.platform.override", "Win32");
lockPref("general.oscpu.override", "Windows NT 6.1");
```
