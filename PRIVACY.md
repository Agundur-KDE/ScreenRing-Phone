# Privacy and permissions

ScreenRing Phone 0.6.0-alpha.2 · Updated 22 November 2026

ScreenRing Phone sends incoming cellular-call alerts to receivers you pair on
your local network. It does not transmit conversation audio, operate a developer
cloud account, or include advertising or analytics SDKs.

## What the Android app processes

| Data / permission | Purpose |
| --- | --- |
| Phone state / `READ_PHONE_STATE` | Detect an incoming call, answer and end, with separate tracking for active SIMs. Outgoing calls do not produce alerts. |
| Incoming number / optional `READ_CALL_LOG` | When caller details are enabled, obtain the incoming number from Android's phone-state broadcast. The implementation does not load call history. |
| Contact name / optional `READ_CONTACTS` | Look up a matching name locally for the incoming number. The contact list is not uploaded. |
| Notifications | Show the ongoing foreground-service notification. |
| Network access | Connect to the destination addresses and ports you configure. |

You can use generic incoming-call alerts without the optional number/contact
permissions. Android permissions can be withdrawn in system settings.

## Local storage and paired receivers

Destination addresses, ports, phone label, a random device identifier, pairing
keys, monitoring choices and delivery status are stored in the app's private
storage. Pairing keys are protected by Android's app isolation, without additional
Android Keystore wrapping. The app disables Android backup and device transfer.
Current call details and pending delivery state are held in process memory.

Name, number and phone label are encrypted in transit to paired receivers.
Device/call identifiers and event types remain visible in protocol headers.
Message-bound authenticated replies confirm delivery; the pairing key is never
sent over the network. Keep it private and pair only with receivers you trust.

KFritz and ScreenRing TV process the alerts locally and may display caller details
to people near their screens. KFritz can retain entries in its recent-call history;
see the receiver's settings and documentation for its storage and deletion.
The phone app does not automatically erase data already received by another device.

## Stop, reset and remove

**Stop forwarding** stops monitoring but keeps your setup. Android's **Clear app
data** or uninstall removes the phone app's local settings and pairing; setup is
then required again. Revoke or replace pairing keys separately on each receiver.
There is no developer account to delete.

App diagnostic messages record delivery status and event type, not intentionally
caller names, numbers or pairing keys. Android manages its own diagnostic buffers.

## Downloads and support

GitHub hosts this repository, release downloads and issue tracker under its own
[privacy statement](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement).
Those services are separate from the app's local call transport. Public README
badges are served by Shields.io when the repository page is viewed.

For help, use [the issue tracker](https://github.com/Agundur-KDE/ScreenRing-Phone/issues).
**Do not post real caller data, phonebooks, unredacted logs, pairing keys or
signing files in a public issue.** For private security reports, use
[the maintainer contact published by KFritz](https://github.com/Agundur-KDE/kfritz/blob/main/package/metadata.json).

This notice describes this Android build. Separate TV distribution and Google
Play declarations are outside the scope of this phone download.
