# Privacy Policy

**Application:** QuestGun (`com.questgun.arcade`)
**Publisher:** SludgeSoft
**Effective date:** 18 August 2026
**Last updated:** 18 August 2026

---

## Summary

**QuestGun does not collect, store, transmit or share any personal data.**

The application has no network capability. It requests no Android permissions
of any kind, and contains no analytics, advertising, crash-reporting or
telemetry components. Nothing you do in QuestGun leaves your headset.

The remainder of this policy explains that in the detail the Meta Horizon Store
requires.

---

## 1. Who we are

QuestGun is published by SludgeSoft, an independent sole-trader software
developer. Contact details are in section 11.

For the purposes of UK GDPR and the EU General Data Protection Regulation,
SludgeSoft would be the data controller for any personal data processed through
QuestGun. As set out below, we do not process any.

## 2. What data we collect

**None.**

We collect no personal data, no device identifiers, no usage analytics, no
crash reports, no advertising identifiers, no location data, no voice or audio
recordings, no camera imagery, no hand or body tracking data, no eye tracking
data, and no account information.

We do not ask you to create an account, sign in, or provide any information
about yourself.

## 3. Why there is nothing to collect

This is verifiable rather than a promise, which is why we state it plainly:

- **No network permission.** QuestGun's Android manifest declares no
  permissions at all — including no `INTERNET` permission. Android therefore
  prevents the application from opening any network connection. It is not that
  we choose not to send data; the application is technically incapable of
  sending it.
- **No third-party SDKs.** QuestGun's only external dependency is the Khronos
  OpenXR loader, which is the standard library used to talk to the headset's VR
  runtime. There is no analytics library, no advertising library, no crash
  reporting service and no social integration.
- **No storage permission.** QuestGun reads and writes only inside its own
  application-specific directory, which Android grants to every app without a
  permission request. It cannot read your photos, documents, downloads, or any
  other application's data.

## 4. Data stored on your device

QuestGun reads files that **you** place into its own application directory:

```
/sdcard/Android/data/com.questgun.arcade/files/
```

This includes emulator core files, game data, and an optional `autoload.txt`
configuration file. These files are supplied entirely by you, remain on your
device, and are never read for any purpose other than running the software you
have asked QuestGun to run. They are never transmitted anywhere.

Uninstalling QuestGun removes this directory and everything in it, in the normal
Android manner.

## 5. Headset sensor data

To function as a virtual reality application, QuestGun receives head and
controller position data from the headset's OpenXR runtime while it is running.
This is used solely and immediately to draw the correct image for your eyes and
to calculate where your controller is aiming.

This data is held in memory for the duration of a single frame, is never
recorded, never written to storage, and never transmitted. QuestGun does not use
hand tracking, eye tracking, face tracking, body tracking, passthrough camera
imagery, or the microphone.

## 6. Third-party emulator cores

QuestGun is a frontend, not an emulator. It loads emulator "cores" that **you**
download and install yourself, from sources of your choosing such as the
libretro project.

These cores are independent third-party software, not written, distributed or
controlled by SludgeSoft. This privacy policy does not cover them. Their
behaviour is governed by their own authors and licences. Because QuestGun holds
no network permission, a core running inside QuestGun is also unable to reach
the network — but you should still satisfy yourself as to the provenance of any
software you install.

## 7. Data sharing and selling

We do not share, sell, rent, disclose or transfer personal data to anyone,
because we do not have any. There are no third-party recipients, no data
processors, and no international data transfers.

## 8. Children's privacy

The Meta Horizon Store requires users to meet Meta's own minimum age
requirements, and virtual reality headsets carry their own manufacturer age
guidance which you should follow.

QuestGun collects no data from anyone, of any age. We therefore do not knowingly
collect personal information from children, and could not do so if we wished to.

## 9. Your rights

Under UK GDPR, EU GDPR, the California Consumer Privacy Act and comparable
legislation, you have rights to access, correct, delete, port and restrict the
processing of your personal data, and to object to it.

We hold no personal data about you, so there is nothing for us to retrieve,
amend or erase. You are welcome to contact us to confirm this, and we will
respond to any such request.

## 10. Changes to this policy

If QuestGun's data practices ever change — for example if an optional online
feature were added in a future version — this policy will be updated before that
version is released, and the "last updated" date above will change. Material
changes will be noted in the application's store listing release notes.

## 11. Contact

Questions about this privacy policy, or about privacy in QuestGun generally:

- **GitHub:** <https://github.com/sludgesoft-a11y>
- **Email:** <sludgesoft@gmail.com>

---

*QuestGun is not affiliated with, endorsed by, or associated with Meta
Platforms, Inc., the libretro project, or any manufacturer or rights holder of
any arcade or console hardware or software.*
