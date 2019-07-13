---
title: Password manager
---

# Password manager

## Disable password manager

CIS Version 1.2.0 October 21st, 2011 2.5.2

### `signon.rememberSignons`

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `false` |

See also the related policy `"OfferToSaveLogins": false`.

### `services.sync.prefs.sync.signon.rememberSignons`

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `false` |

## Disable websites autocomplete (FF30+)

Don't let sites dictate use of saved logins and passwords.

### `signon.storeWhenAutocompleteOff`

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `false` |

See also the related policy `DisableMasterPasswordCreation`

## When password manager is enabled, lock the password storage periodically

CIS Version 1.2.0 October 21st, 2011 2.5.3

Disable Prompting for Credential Storage.

// Advanced user settings when password manager is enabled
//lockPref("security.ask_for_password", 2);

| Item       | Value |
| ---------- | ----- |
| Status     | `disabled` |
| FF Default | ? |
| LibreWolf  | `2` |

## When password manager is enabled, lock the password storage every 1 minutes (default: 30)

### `security.password_lifetime`

| Item       | Value |
| ---------- | ----- |
| Status     | `disabled` |
| FF Default | ? |
| LibreWolf  | `5` |
