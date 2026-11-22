# ScreenRing Phone

The Android companion for ScreenRing. It forwards incoming cellular call alerts
to a paired ScreenRing TV app or compatible KFritz desktop receiver over your
local network. It does not transmit conversation audio.

**The first public download is being prepared. No release APK is available here yet.**

This repository provides phone downloads and public documentation. It does not
contain the TV app or the application source code. The TV app is planned for
separate distribution through Google Play.

## Requirements and installation

- Android 8 or newer, with cellular calling for call detection.
- A compatible receiver and a local network that allows the devices to connect.
- A pairing key obtained directly from the intended receiver.

When a release becomes available, download the phone APK and `SHA256SUMS` from
the repository's **Releases** section. Verify the checksum before installing.
`SIGNER.txt` identifies the public signing certificate; later updates must use
the same certificate. A checksum obtained alongside an APK detects corruption;
it does not independently establish the publisher's identity.

The SHA-256 fingerprint of the ScreenRing Phone release signing certificate is:

```text
e126db475859e63617676ac0030acb3ee3b87242779b26cdced241f1a7405d86
```

This is a public certificate fingerprint, not a pairing key. It must match the
APK signing certificate and `SIGNER.txt` when the first download is published.

Android will ask you to permit installation from your browser or file manager.
You can turn this permission off again after installing. Existing development
builds may use a different signing key and cannot be updated in place. Removing
an app deletes its settings and pairing information.

[Deutsche Einrichtung](INSTALL.de.md)

## Setup

1. Install and configure the receiver. For the TV, enable phone reception and
   obtain its address and pairing key. For KFritz, enable its compatible receiver.
2. Enter the destination address and pairing key in ScreenRing Phone. Keep the
   key private; anyone possessing it can authenticate call events.
3. Grant phone-state permission. Caller-number and contact-name permissions are
   optional and are requested only when caller details are enabled.
4. Start forwarding and send a test message. The test does not pause playback.

The app uses an ongoing foreground notification. Unlock the phone once after
a reboot. Manufacturer power-saving restrictions or force-stop can prevent
background operation; reopen the app and start forwarding to recover.

## Data and limitations

Caller details, when enabled and permitted, are encrypted for the receivers you
pair. Device/call identifiers and event types remain visible in the protocol
header. Pairing keys and settings stay in private application storage; Android
backup/device transfer is disabled by the app. ScreenRing has no developer cloud
account, advertising SDK or analytics SDK. Your paired receiver also processes
the events and can display caller details to people near its screen.

No outgoing-call alerts, conversation recording, WhatsApp/other VoIP support or
automatic playback resume are promised. The TV can receive FRITZ!Box landline
calls independently of this phone app. Support and final privacy information
will be provided before the first public release.
