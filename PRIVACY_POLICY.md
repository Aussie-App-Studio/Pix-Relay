# Privacy Policy — Pix Relay: Auto Photo Sync

**Effective Date:** November 24, 2026  
**Publisher:** Aussie App Studio  
**App Package:** `com.pixrelay.sync`

## Summary

**Pix Relay: Auto Photo Sync does not collect, track, sell, or upload any of your personal data to Aussie App Studio or third-party analytics/ad servers.** Your photos, videos, pairing keys, and transfer logs stay on your own devices and travel directly over your local Wi-Fi or mobile hotspot network.

---

## 1. Zero Developer Data Collection & No Telemetry

Aussie App Studio does not operate any cloud servers for Pix Relay and does **not** collect, store, transmit, or share:
- Personal information (name, email address, phone number, or account credentials)
- Photos, videos, albums, EXIF metadata, or GPS location data
- Usage analytics, behavioral tracking, advertising identifiers, or crash telemetry

## 2. Local Wi-Fi & Hotspot Transfers Only

Pix Relay transfers photos and videos directly between your paired devices (for example, your daily phone and your backup Pixel, or the Pix Relay PC/Mac companion app):
- **Local Discovery:** Uses local LAN UDP broadcast (`UDP 42889`) and Android Network Service Discovery / mDNS (`_pixrelay._tcp.`).
- **End-to-End Local Encryption:** Media and control messages are sent directly over a local TCP connection (`TCP 42888`) protected by **P-256 ECDH** key exchange, **HKDF-SHA256** key derivation, and **AES-256-GCM** encryption, verified via a 6-digit code or QR code during pairing.
- **No Mobile Data Transfers:** Pix Relay filters out cellular network interfaces so media transfers occur strictly over local Wi-Fi or a local Wi-Fi hotspot.

## 3. Permissions We Request & Why

Pix Relay requests only the Android permissions required for local device-to-device photo sync:

- **Photos & Videos (`READ_MEDIA_IMAGES`, `READ_MEDIA_VIDEO`, `READ_MEDIA_VISUAL_USER_SELECTED`, `READ_EXTERNAL_STORAGE`, `WRITE_EXTERNAL_STORAGE`):** Needed to browse folders on a Sender phone, read selected media for transfer, and save received photos and videos on a Receiver Pixel.
- **Media Location (`ACCESS_MEDIA_LOCATION`):** Used on Android 10+ solely so original EXIF GPS coordinates inside your photos are preserved intact when transferred between your own devices. Pix Relay never reads or tracks your live device location.
- **Camera (`CAMERA`):** Optional permission used strictly if you scan a pairing QR code on another device's screen. Camera frames are processed on-device in real time and are never saved or transmitted.
- **Wi-Fi & Local Network (`INTERNET`, `ACCESS_NETWORK_STATE`, `ACCESS_WIFI_STATE`, `CHANGE_WIFI_MULTICAST_STATE`):** Used for local peer discovery and direct encrypted socket transfers on your LAN/hotspot.
- **Background Sync & Notifications (`FOREGROUND_SERVICE`, `FOREGROUND_SERVICE_DATA_SYNC`, `FOREGROUND_SERVICE_CONNECTED_DEVICE`, `WAKE_LOCK`, `RECEIVE_BOOT_COMPLETED`, `REQUEST_IGNORE_BATTERY_OPTIMIZATIONS`, `POST_NOTIFICATIONS`):** Keeps Receiver listening and Auto-Send running reliably while the screen is off, resumes after reboot when enabled, and displays local transfer/battery/storage status notifications.

## 4. Optional User-Configured Features & Third-Party Services

- **Google Photos (on Receiver Devices):** Pix Relay saves received media into your Pixel's local storage (such as `DCIM/Camera` or `Pictures/PixRelay/`). Any subsequent cloud backup is performed by the **Google Photos** app on your device according to your own Google account settings and Google's Privacy Policy.
- **Optional Smart Plug Battery Guard Webhooks:** If you choose to enable Smart Plug Battery Guard in Receiver settings and enter custom webhook URLs, Pix Relay sends an HTTP request exclusively to the URLs you entered when the Receiver battery reaches your configured charge thresholds (e.g., 80% off / 20% on). This feature is disabled by default.
- **Optional External Links:** Tapping external companion download links inside the app opens your device's web browser directly.

## 5. Local Storage, Retention & Deletion

Pix Relay stores its configuration (`pix_relay_prefs` SharedPreferences) and local database (`pix_relay.db` SQLite — paired device keys/names, folder auto-send policies, and SHA-256/fingerprint transfer deduplication records) strictly on your device.

You are in full control of your data:
- Unpair any device inside the **Pairing** tab to delete its stored pairing secret.
- Uninstall the app (or clear app storage in Android Settings) at any time to permanently erase all local settings and transfer history.
- If Android System Backup (`allowBackup`) is enabled on your phone, Android may include app preferences in your personal device backup managed by Google/Android.

## 6. Children's Privacy

Pix Relay does not knowingly collect any personal information from anyone, including children under 13 (or the applicable age in your jurisdiction), as the app collects no personal data at all.

## 7. Changes to This Policy

If this Privacy Policy is updated, the revised version and effective date will be posted on this page.

## 8. Contact

If you have any questions about this Privacy Policy, please contact **Aussie App Studio** at:  
- Email: `aussieappstudio@gmail.com`  
- Privacy Policy Page: https://aussie-app-studio.github.io/Pix-Relay/privacy-policy.html
