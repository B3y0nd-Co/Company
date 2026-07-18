# Decision Log

This document records major company decisions.

Do not delete old decisions. Add new entries below.

---

## July 4, 2026

### Decision #001 — Company Name

**Decision:** Use **B3YOND Co.** as the public company name.

**Reason:** A parent brand capable of supporting multiple future products.

---

### Decision #002 — GitHub Organization Name

**Decision:** Use **B3y0nd Co.** as the GitHub organization name.

**Reason:** GitHub naming availability required a practical variation while keeping the brand recognizable.

---

### Decision #003 — First Product

**Decision:** Build **PocketPass** as the first product.

**Reason:** PocketPass addresses the problem of losing valuable real-world connections.

---

### Decision #004 — Primary Market

**Decision:** Start with professional networking and events.

**Reason:** This market has a clear value proposition and lower barriers to adoption than launching directly as a dating platform.

Dating and community modes remain part of the long-term roadmap.

---

### Decision #005 — Development Strategy

**Decision:** School comes first.

**Reason:** The company will grow through steady, consistent progress rather than unrealistic deadlines.





## July 18, 2026

### Decision #006 — Engineering Development Has Begun

**Decision:** Begin Android-first prototype development for B3YOND Co.'s real-world networking product.

**Reason:** Android provides a practical platform for testing Bluetooth Low Energy discovery and advertising across physical devices.

---

### Decision #007 — Use Physical Devices for Bluetooth Validation

**Decision:** Bluetooth Low Energy advertising and discovery must be validated on physical Android phones.

**Reason:** Android emulators may not accurately support or represent BLE advertising and nearby-device behavior.

---

### Decision #008 — Support Multiple Android Permission Models

**Decision:** The application will support both the legacy Android permission model and the Android 12+ Nearby Devices permission model.

**Reason:** The initial test devices run Android 11 and Android 16, and the product should handle both safely.

---

### Decision #009 — Permission Failures Must Be Safe

**Decision:** Missing or denied Bluetooth permissions must disable affected functionality without crashing the application.

**Reason:** Privacy, reliability, and understandable permission handling are core product requirements.

---

### Decision #010 — Product Name Remains Unresolved

**Decision:** Continue development without locking the final public product name.

**Reason:** The underlying product and technical prototype can progress while naming, trademark, domain, and competitor research continue.

The Android prototype will temporarily use a neutral internal engineering identity.