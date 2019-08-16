---
title: WebRTC
---

Disable because it is very efficient for fingerprinting.

## Disable WebRTC getUserMedia, screen sharing, audio capture, video capture

See also:

- https://wiki.mozilla.org/Media/getUserMedia
- https://blog.mozilla.org/futurereleases/2013/01/12/capture-local-camera-and-microphone-streams-with-getusermedia-now-enabled-in-firefox/
- https://developer.mozilla.org/en-US/docs/Web/API/Navigator

### `media.navigator.enabled`

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `false` |

### `media.navigator.video.enabled", false`

Note: Deprecated in Firefox

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `false` |

### `media.getusermedia.browser.enabled`

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `false` |

### `media.getusermedia.screensharing.enabled`

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `false` |

### `media.getusermedia.audiocapture.enabled`

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `false` |

## Disable WebRTC (Web Real-Time Communication)

See also: https://www.privacytools.io/#webrtc

## `media.peerconnection.use_document_iceservers`

Note: Deprecated Active

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `false` |

## `media.peerconnection.identity.enabled`

Note: Deprecated Active

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `false` |

## `media.peerconnection.identity.timeout`

Note: Deprecated Active

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | ? |
| LibreWolf  | `1` |

## `media.peerconnection.turn.disable`

Note: Deprecated Active

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `false` |
| LibreWolf  | `true` |

## `media.peerconnection.ice.tcp`

Note: Deprecated Active

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `false` |

## `media.peerconnection.use_document_iceservers`

Note: Deprecated Active

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `true` |
| LibreWolf  | `false` |

## Limit WebRTC IP leaks if using WebRTC

See also:

- https://bugzilla.mozilla.org/buglist.cgi?bug_id=1189041,1297416
- https://wiki.mozilla.org/Media/WebRTC/Privacy

### `media.peerconnection.ice.default_address_only`

FF42–FF50

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `false` |
| LibreWolf  | `true` |

### `media.peerconnection.ice.no_host`

FF51+

| Item       | Value |
| ---------- | ----- |
| Status     | `lock` |
| FF Default | `false` |
| LibreWolf  | `true` |
