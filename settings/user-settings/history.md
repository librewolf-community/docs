---
title: History
---

## Limit history leak via enumeration (PER TAB: back/forward) - PRIVACY

This is a PER TAB session history. You still have a full history stored under all history.

`2` is the recommended minimum as some pages use it as a means of referral (e.g. hotlinking), `4` or `6` or `10` may be more practical.

### `browser.sessionhistory.max_entries`

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| Minimum    | `1` — current page |
| FF Default | `50` |
| LibreWolf  | `20` |

## Disable Displaying Javascript in History URLs

### `browser.urlbar.filter.javascript`

http://kb.mozillazine.org/Browser.urlbar.filter.javascript

CIS 2.3.6

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `false` |
| LibreWolf  | `true` |

## Default Interface Look

### `browser.uiCustomization.state`

| Item       | Value |
| ---------- | ----- |
| Status     | `default` |
| FF Default | ? |

LibreWolf:

```json
'{"placements":{"widget-overflow-fixed-list":[],"nav-bar":["home-button","downloads-button","back-button","forward-button","stop-reload-button","urlbar-container","add-ons-button","preferences-button","fxa-toolbar-menu-button"],"toolbar-menubar":["menubar-items"],"TabsToolbar":["tabbrowser-tabs","new-tab-button","alltabs-button"],"PersonalToolbar":["personal-bookmarks"]},"seen":["developer-button"],"dirtyAreaCache":["nav-bar","toolbar-menubar","TabsToolbar","PersonalToolbar"],"currentVersion":16,"newElementCount":3}'
```

## UI Density

### `browser.uidensity`

| Item       | Value |
| ---------- | ----- |
| Status     | `default` |
| LibreWolf  | `2` (touch) |

## Disables titlebar if enabled

### `browser.tabs.drawInTitlebar`

| Item       | Value |
| ---------- | ----- |
| Status     | `default` |
| LibreWolf  | `true` |

## Default Home Page

### `startup.homepage_override_url`

| Item       | Value |
| ---------- | ----- |
| Status     | `pref` |
| LibreWolf  | `"about:blank"` |

### `startup.homepage_welcome_url`

| Item       | Value |
| ---------- | ----- |
| Status     | `pref` |
| LibreWolf  | `"about:blank"` |

### `startup.homepage_welcome_url.additional`

| Item       | Value |
| ---------- | ----- |
| Status     | `pref` |
| LibreWolf  | `""` |

## Clear offline site data on shutdown

## `privacy.clearOnShutdown.offlineApps`

| Item       | Value |
| ---------- | ----- |
| Status     | `default` |
| LibreWolf  | `true` |

## Clear offline site data on clear dialog (History/Clear...)

### `privacy.cpd.offlineApps`

Offline Website Data.

| Item       | Value |
| ---------- | ----- |
| Status     | `pref` |
| LibreWolf  | `""` |

## Set time range to "Everything" as default in "Clear Recent History"

### `privacy.sanitize.timeSpan`

This should not be enforced.

| Item       | Value |
| ---------- | ----- |
| Status     | `default` |
| FF Default | ? |
| LibreWolf  | `0` |

## Disable form autofill

Don't save information entered in web page forms and the Search Bar; remember search and form history setting.

### `browser.formfill.enable`

| Item       | Value |
| ---------- | ----- |
| Status     | `default` |
| FF Default | ? |
| LibreWolf  | `false` |

## Defaulting Settings : Clear history when closing

### `privacy.sanitize.sanitizeOnShutdown`

| Item       | Value |
| ---------- | ----- |
| Status     | `default` |
| FF Default | `false` |
| LibreWolf  | `true` |

## Defaulting Settings : Does not remember history

### `places.history.enabled`

| Item       | Value |
| ---------- | ----- |
| Status     | `default` |
| FF Default | `true` |
| LibreWolf  | `false` |

## Settings history settings to custom by default

### `privacy.history.custom`

| Item       | Value |
| ---------- | ----- |
| Status     | `default` |
| FF Default | `false` |
| LibreWolf  | `true` |

## Clear session data on clear dialog (History/Clear...)

Clear session data.

### `privacy.cpd.openWindows`

Note: Disabled.

| Item       | Value |
| ---------- | ----- |
| Status     | `default` |
| FF Default | `false` |
| LibreWolf  | `true` |

Same as `privacy.*.openWindows`, session storage is cleared anyway. Check with storage inspector.

## Clear session restore data (FF34+)

### `privacy.*.openWindows`

Note: Disabled.

Note: There is a several-year old bug associated with these that causes two windows when Firefox restarts.

These are not needed anyway if session restore is disabled (see `Disable the Session Restore service completely`).

### `privacy.clearOnShutdown.openWindows`

Note: Disabled.

| Item       | Value |
| ---------- | ----- |
| Status     | `default` |
| FF Default | `false` |
| LibreWolf  | `true` |

Breaks session restore on crash & some theming extensions. The session is deleted anyway on restart so its not useful. Mitigated with other settings.

## Defaulting Settings : Clear history when closing - Pref : 2803 : Duplicate ?

"sessions" removed from cleaning list as its an important data to keep... The user may add it back in the GUI. This setting works only as a string not as boolean (this seems to be a bug in Firefox).

Also this setting seems to kill following settings so it should be the last

### `privacy.sanitize.pending`

Note: Disabled.

Warning: This erases the settings no matter what.

Its erased if not enforced... and default does not differ a lot (session included in default...)

| Item       | Value |
| ---------- | ----- |
| Status     | `default` |
| FF Default | ? |

LibreWolf:

```json
'[{"id":"shutdown","itemsToClear":["cache","cookies","history","formdata","downloads"],"options":{}}]'
```

## 1006: prevent permissions manager from writing to disk [RESTART]

Note: This means any permission changes are session-only.

See: https://bugzilla.mozilla.org/967812

### `permissions.memory_only`

Note: Disabled.

This is managed by sanitize settings. This is a hidden preference.

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `false` |
| LibreWolf  | `true` |

## Delete Search and Form History

CIS Version 1.2.0 October 21st, 2011 2.5.6

### `browser.formfill.expire_days`

Note: Disabled — Deprecated Active; this is not deprecated. Disabled because it's managed by sanitize settings

Only used in a single test (?). Does not harm to have it.

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `180` |
| LibreWolf  | `0` |

See also:

- User Settings — Session
- User Settings — Autofill settings
