# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to
[Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## Types of Changes

- **Added** for new features
- **Changed** for changes in existing functionality
- **Deprecated** for soon-to-be removed features
- **Removed** for now removed features
- **Fixed** for any bug fixes
- **Security** for vulnerability fixes

# Versions

## [1.7.6]

### Fixed

- `[Web]` re-enable info/warning banner on 3D scene
- `[Web]` semantic snapshot history loading

## [1.7.1]

### Added

- `[Android]` `[iOS]` OTA (over the air) update
- `[Android]` `[iOS]` poi created notification toast (local notification, only
  shown to user created the poi)
- `[Web]` Localizaitons for PIDB
- `[Web]` Bulk update fixture depth page

### Fixed

- `[Android]` `[iOS]` users able to set poi below floor plane (min mark height:
  30cm)
- `[Android]` `[iOS]` photo rotation when taking photos landscape/upside-down
- `[Android]` `[iOS]` show vertical path up to the destination when navigating

## [1.7.0]

- dev version, see changes in 1.7.1

## [1.6.4]

### Changed

- `[Android]` `[iOS]` fix poi navigation header display

## [1.6.3]

### Changed

- `[Android]` hide sorting button (modal system needs a refactor in android)

### Fixed

- `[Android]` `[iOS]` fail to scan same product right after deletion on the same
  shelf (csa-792)
- `[Android]` `[iOS]` move image processing on take photos task/habit/poi to
  background (csa-795)
- `[Android]` `[iOS]` `[Web]` back from shevles list goes back to fixtures list
  and not sections list (csa-794)
- `[iOS]` sorting in task/habit list (csa-788)

## [1.6.2]

### Fixed

- `[Android]` `[iOS]` disallow scanning of products on scan mode, when no
  shelf/product is selected
- `[Android]` incorrect cropping of photos
- `[iOS]` photos taken are upside down
- `[Android]` `[iOS]` localization texts (csa-793)

## [1.6.1]

### Fixed

- `[Android]` `[iOS]` error when scanning second product

## [1.6.0]

### Added

- `[Web]` insights and reconstructions (feature flagged off for now)
- `[Android]` Update to date android build
- `[Android]` `[iOS]` Scan anywhere for semantic shelves
- `[Android]` `[iOS]` `[Web]` Danish and Norwegian language support

### Fixed

- `[Android]` `[iOS]` disallow scanning of mirrored QR code
- `[Android]` `[iOS]` `[Web]` app language reverts back to system language after
  killing app
- `[Android]` `[iOS]` `[Web]` fail to sign in first time/occasionally
- `[Android]` app icon display
- `[Android]` `[iOS]` note/habit placement marker, now 0.5m instead of 2m from
  the camera

## [0.5.8]

### Fixed

- `[Web]` needing to signin 2 times on first sign in

## [0.5.7]

### Fixed

- `[Web]` avoid Cactus opening in auth window when users have tab with signed in
  session
- `[Web]` points of interest focusing button

## [0.5.6]

### Fixed

- `[Web]` points of interest positioning on web

## [0.5.5]

### Fixed

- `[iOS]` place map marker pole displayed when in user calibration

## [0.5.4]

### Fixed

- `[iOS]` in push notification on click when user is in domainSelect
- `[iOS]` in app notification on click

## [0.5.3]

### Added

- `[iOS]` add coordinate system (coord) value in pose in frontend

### Fixed

- `[iOS]` habit not (visually) not updated after title edit, when user navigates
  and back
- `[iOS]` clicking on notification no longer routes to loading page

## [0.5.2]

### Added

- `[iOS]` add/modify/remove/place points of interest (csa-714)
- `[iOS]` points of interest navigation (csa-489)
- `[iOS]` enable push notifications (csa-740)
- `[Web]` page for product info for PIDB
- `[Web]` points of interest display (csa-734)

### Fixed

- `[iOS]` wrong profile named display after (csa-737)
- `[iOS]` user signed out after kill app and relaunch (csa-738)
- `[iOS]` no domains shown after account switch (csa-739)
- `[Web]` more intuitive web 3d control (csa-753)

### Removed

- `[Web]` `[Internal]` modify staging_api_url/staging_dds_url in local storage
  to route to different posemesh urls

## [0.4.10]

### Fixed

- `[iOS]` Failed to fetch lighthouse data when accessing a domain after first
  time login

## [0.4.9]

### Fixed

- `[Web]` Incorrect semantic selection when switching domains

## [0.4.8]

### Added

- `[Web]` Batch set all fixture depths at once (csa-704)
- `[Interal]` Script for bumping versions, updating in all necessary places

### Fixed

- `[iOS]` Japanese Text Overflow in Settings Screen (csa-728)
- `[Web]` Domain select page search bar format

## [0.4.7]

### Fixed

- `[iOS]` error when entering task list

## [0.4.6]

### Changed

- `[iOS]` using last part of version number as build number

## [0.4.5]

### Changed

- `[web]` using last part of version number as build number

## [0.4.4] (126)

Both:

- support Metric & Imperial system (csa-702)
- display version text before sign in (csa-696)
- add viewer mode support on the frontend (csa-568)

Web:

- clicking on fixture in 3d view selects it (csa-703)
- allow selection of empty shelf (csa-573)
- improved performance on 3d scene for domains with a lot of fixtures/products
  (csa-715)
- allow only numbers/decimals for fixture depth (csa-469)
- add heatmap for how updated the product locations are (csa-721)

iOS:

- add analytics property semantic_fixture_update_handle (csa-707)
- upgrade unity 2022.3.26f1 -> 2022.3.62f3 for security upgrade (csa-708)
- add feature flag for pointing amplitude dev or prod (csa-659)
- add pull down to refresh for lists (csa-657)
- fix wrong routing after taking photos in tasks (csa-712)
- fix missing localizations on user name update dialog (csa-710)
- fix button label in note details screen (csa-483)

internal:

- fix client code override in zitadel
- rename variables e.g. EXPO_PUBLIC_ZITADEL_ISSUER → EXPO_PUBLIC_AUTH_ISSUER,
  remove zitadel references (csa-713)
- add coordinate and portal visualizations as debug features

## [0.4.3]

both:

- use Joystick for feature flags for different customers (csa-363)
- save local Joystick config backup and use it when Joystick is not reachable
  (csa-670)
- remove the need for users to enter client code (csa-634)
- select zitadel account on signin
- allow client code change for individual users (csa-693)

iOS:

- hide tasks and habits for ICA (csa-430)
- hide habits on mobile (new backend for habits is not implemented)
- store barcode validation rules to joystick, not hardcoded in client (csa-647)
- show teams tab for tasks (csa-695)

web:

- Load product image on product selection (testable on Cactus backend version
  0.2.5) (csa-660, csa-694)
- More intuitive 3D scene control (csa-525)
- show swidish number format for prices
- add change language button in doaminSelect
- move local csv toggle to domain select
- fixture depth m to cm (csa-667)

## [0.4.2]

both:

- properly track auth expire time, storing auth credentials

iOS:

- updated fixture/section/shelf frames on AR view
- advanced handles for fixture movement
- cut and paste fixtures
- refresh tasks when screen comes into focus
- fix websocket update to Unity when deleting fixtures

web:

- resizable panels
- updated fixture name/depth editing
- improved visuals for vertical scroll bar on windows

## [0.4.1]

Web:

- no longer sign in with small window from OAuth
- ~~improved web socket connection~~ (the fix has problem, will remove it for
  this version)
- disallow modifications on fixtures/sections name and depth when viewing on a
  past date.
- fixed product names loading on first load

Mobile:

- support UPC barcode validation for client codes starting with **2** (Tractor
  supply)
- better handling on clashing update for semantic shelves. (i.e. 2 people
  updating the same thing at the same time)
- support fixture creation from right to left
- localization fixes
- fixed product names loading on first load

## [0.3.2] (83)

### Added

- changelog.md file
- Local CSV data support for product names and sales data for sementic shelf
- historic semantic shelf data
- view diff of product placement between start and end date
- secret management in iOS build script
- (web) button to snap to fixture/section/shelf/product in 3D view
- (web) fixture depth display
- Japanese localizations
- (web) admin page
- UI for adding multiple shelves and sections at once in AR mode

### Changed

- support sementic shelf on Neovici parsor
- hide occlusions
- updated fixture editing UI
- Consolidated analytic events

### Fixed

- refetching of data when background/foreground/change tab

### Removed

- heartbeat
- esl related code

## [0.3.1] - AWE Version (iOS/Web)

### Added

- Semantic self support

### Changed

- UI overhaul

## [feature/salling-client-csv from 0.2.3] - Salling Version (Web)

### Added

- Local CSV data support for product names and sales data

## [0.2.3] - ICA Production Version (Web)

### Added

- ICA production version features

### Changed

- moved out from mono repo

## [0.2.2] - ICA Production Version (iOS 82)

### Fixed

- wrong posemesh credential used in Unity

## [0.2.1] - ICA Production Version (iOS 65)

### Added

- ICA production version features
