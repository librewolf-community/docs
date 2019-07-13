---
title: Cookies
---

# Cookies

Also see [tracking protection settings](/docs/user-settings/tracking-protection) for other cookies settings.

## Accept Only 1st Party Cookies

Blocking 3rd-party cookies breaks a number of payment gateways

CIS 2.5.1

### `network.cookie.cookieBehavior`

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `0` |
| LibreWolf  | `1` |

See also: http://kb.mozillazine.org/Network.cookie.cookieBehavior#1

## Make cookies expire at the end of the session (when the browser closes)

### `network.cookie.lifetimePolicy`

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default |  |
| LibreWolf  | `2` |

- `0`: until they expire (default)
- `2`: until you close Firefox
- `3`: for n days

See also: http://kb.mozillazine.org/Network.cookie.lifetimePolicy#2

## Disable Cookie Exception Button

### `pref.privacy.disable_button.cookie_exceptions`

Warning: This locks the button regardless of its value. This is a bug in FF.

| Item       | Value |
| ---------- | ----- |
| Status     | disabled |
| FF Default |  |
| LibreWolf  | `false` |

## Enable support for same-site cookies (FF60+)

### `network.cookie.same-site.enabled`

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `true` |

See also:

- https://bugzilla.mozilla.org/795346
- https://blog.mozilla.org/security/2018/04/24/same-site-cookies-in-firefox-60/
- https://www.sjoerdlangkemper.nl/2016/04/14/preventing-csrf-with-samesite-cookie-attribute/

## Disable HTTP sites setting cookies with the "secure" directive (FF52+)

### `network.cookie.leave-secure-alone`

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `true` |

See also:

- https://developer.mozilla.org/Firefox/Releases/52#HTTP

## Set third-party cookies to session-only

<!-- Quote from LF follows. I don't think I fully understand it.  -->
Set third-party cookies (i.e ALL) (if enabled, see above pref) to session-only and (FF58+) set third-party non-secure (i.e HTTP) cookies to session-only.

`.sessionOnly` overrides `.nonsecureSessionOnly` except when `.sessionOnly=false` and `nonsecureSessionOnly=true`. This allows you to keep HTTPS cookies, but session-only HTTP ones.

See also:

- https://feeding.cloud.geek.nz/posts/tweaking-cookies-for-privacy-in-firefox

### `network.cookie.thirdparty.sessionOnly`

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `false` |
| LibreWolf  | `true` |

See also:

- http://kb.mozillazine.org/Network.cookie.thirdparty.sessionOnly

### `network.cookie.thirdparty.nonsecureSessionOnly`

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `false` |
| LibreWolf  | `true` |
