# Founder Meeting #002

**Date:** July 18, 2026  
**Company:** B3YOND Co.  
**Founder:** Kristian Lopez-Reyes  
**Product:** Working name under review  

## Meeting Purpose

Begin the first technical prototype for B3YOND Co.'s real-world networking product.

The goal of Day 2 was to create a functioning Android foundation and verify that Bluetooth Low Energy capabilities could be detected safely across different Android versions.

## Accomplishments

- Created the Android application using Kotlin and Jetpack Compose.
- Connected the Android project to the product repository.
- Established a feature-branch and pull-request workflow.
- Created the initial Event Mode prototype screen.
- Added Bluetooth hardware capability detection.
- Added Bluetooth Low Energy capability detection.
- Added BLE advertising capability detection.
- Added runtime permission handling for Android 12 and newer.
- Fixed a crash caused by accessing protected Bluetooth information before permission was granted.
- Tested the application on an Android emulator.
- Tested the application on a physical Android 11 phone.
- Tested the application on a physical Android 16 phone.
- Confirmed that both physical phones support BLE and BLE advertising.
- Confirmed that unsupported emulator capabilities are handled without crashing.

## Technical Findings

### Android 11

- The Nearby Devices permission prompt is not used.
- Bluetooth capability detection works.
- BLE advertising is supported on the tested device.
- Actual BLE scanning may still require location permission.

### Android 16

- Nearby Devices permission is required.
- The permission request works correctly.
- Bluetooth capability detection works after permission is granted.
- BLE advertising is supported on the tested device.

### Android Emulator

- Useful for UI and permission-flow testing.
- BLE advertising is unavailable in the current emulator configuration.
- The application handles the limitation safely.

## Problems Encountered

The first Bluetooth capability implementation attempted to read protected Bluetooth properties before runtime permission had been granted.

This caused the application to crash on the physical Android phone.

The implementation was corrected by:

- Checking permission status before accessing protected APIs.
- Requesting Nearby Devices permission on Android 12 and newer.
- Catching unexpected `SecurityException` errors.
- Displaying unavailable states instead of crashing.

## Decisions

### Decision P-005 — Physical Phones Required for BLE Validation

BLE advertising and discovery testing will use physical Android phones.

The emulator will continue to be used for general UI and application testing.

### Decision P-006 — Permission Checks Before Bluetooth Access

PocketPass will verify all required permissions before accessing protected Bluetooth functionality.

Permission denial must never cause the application to crash.

### Decision P-007 — Support Multiple Android Permission Models

The prototype will support:

- Android 11 and earlier using the legacy permission model.
- Android 12 and newer using Nearby Devices permissions.

## Current Prototype Status

The application can currently:

- Launch successfully.
- Display Event Mode controls.
- Detect Bluetooth hardware availability.
- Detect whether Bluetooth is enabled.
- Detect BLE support.
- Detect BLE advertising support.
- Request Nearby Devices permission when required.
- Handle unsupported capabilities safely.

The application does not yet scan for or advertise identifiers.

## Next Engineering Task

```text
feat: support BLE permissions across Android versions
```

After permission handling is complete, the next milestone is the first real phone-to-phone test:

1. Phone A advertises a temporary anonymous identifier.
2. Phone B scans for PocketPass-compatible advertisements.
3. Phone B displays the detected identifier.
4. No personal information is exchanged.

## Open Product Question

The working product name remains under review.

Names explored include:

- SecondMeet
- NewLink
- NLink
- MeetKind
- PeerLink
- PeerThread
- CommonKind

No final product name has been selected.

## Day 2 Status

**Completed successfully.**

B3YOND Co. now has its first functioning Android prototype foundation and its first verified hardware tests.