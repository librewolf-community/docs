---
title: DRM/CDM
---

# DRM/CDM

## Main DRM/CDM settings

DRM is disabled because it's a closed source blob.

EME stands for "Encrypted Media Extensions".

### `media.eme.enabled`

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `false` |

### `media.gmp-provider.enabled`

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `false` |

### `media.gmp-manager.url`

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | ? |
| LibreWolf  | `"data:text/plain,"` |

### `media.gmp-manager.url.override`

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | ? |
| LibreWolf  | `"data:text/plain,"` |

### `media.gmp-manager.updateEnabled`

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `false` |

### `media.gmp.trial-create.enabled`

Specific to Windows 10.

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `false` |

## Disable widevine CDM (Content Decryption Module)

### `media.gmp-widevinecdm.visible`

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `false` |

### `media.gmp-widevinecdm.enabled`

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `false` |

### `media.gmp-widevinecdm.autoupdate`

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `false` |

## Disable automatic downloading of OpenH264 codec

Q. Why is there OpenH264?

A. https://support.mozilla.org/en-US/kb/open-h264-plugin-firefox

Q. How to manually install OpenH264?

A. https://support.mozilla.org/en-US/questions/1029174

See also:

- https://support.mozilla.org/en-US/kb/how-stop-firefox-making-automatic-connections#w_media-capabilities
- https://andreasgal.com/2014/10/14/openh264-now-in-firefox/

If you want to enable this, WebRTC needs to be enabled too.

### `media.gmp-gmpopenh264.enabled`

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `false` |

### `media.gmp-gmpopenh264.autoupdate`

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `false` |

### `media.peerconnection.video.enabled`

Note: Deprecated active.

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `false` |

## Force OpenH264 On (Not necessary)

### `media.peerconnection.video.h264`

Note: Disabled.

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `false` |
| LibreWolf  | `true` |

## Adobe Primetime

### `media.gmp-eme-adobe.enabled`

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `false` |

## IJWY To Shut Up

### `media.gmp-manager.certs.1.commonName`

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `"aus5.mozilla.org"` |
| LibreWolf  | `""` |

### `media.gmp-manager.certs.2.commonName`

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `"aus5.mozilla.org"` |
| LibreWolf  | `""` |
