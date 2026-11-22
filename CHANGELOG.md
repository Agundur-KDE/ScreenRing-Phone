# Release notes

## 0.6.0-alpha.2

First signed public test candidate, coordinated with **KFritz 0.5.0**.

- Incoming cellular-call alerts on KDE Plasma through the opt-in KFritz receiver.
- Optional encrypted caller number and local contact name; generic alerts work
  without optional number/contact permissions.
- Challenge authentication and message-bound delivery acknowledgements.
- Independent paired destinations for KFritz and the separately distributed TV app.
- Android 8+, ongoing foreground notification and restart recovery after unlock.
- APK accompanied by SHA-256 checksums and the permanent signing-certificate pin.

KFritz 0.4.1 and earlier do not support this receiver. Older receivers replying
with unauthenticated `OK` are incompatible. Update both endpoints together.

No promised WhatsApp/VoIP, outgoing-call alerts, conversation audio or call-control
buttons. This is an alpha, not a compatibility guarantee for every Android device.
