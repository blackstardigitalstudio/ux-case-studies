# UX Case Study — Orbix Play
**Streaming Player · Daily Use · Mobile/TV**

> Audit by Matteo Stella — Digital Product & UX Operations
> Method: daily use + friction mapping + competitive analysis

## Context

**Orbix Play** is an IPTV streaming application used daily to play video content from local folders and remote feeds. The app is functional and stable — but presents two significant friction areas that impact the viewing and browsing experience.

This audit is not theoretical: the friction points identified emerge from real, repeated use.

## Friction Point #1 — Aspect Ratio Control During Playback

### The Problem

When playing a video, the app offers no control to modify the aspect ratio of the video being played.

**What happens in practice:**
- 4:3 content (vintage series, documentaries) is displayed with fixed black bars, with no adaptation possible
- Cinematic 21:9 or 2.35:1 content shows horizontal bars that cannot be removed or reduced
- The user cannot choose between fit, fill, stretch, crop or zoom based on personal preference
- On widescreen or ultrawide displays, the result is often suboptimal

### Root Cause

The app fixes the video renderer to a rigid aspect ratio (likely 16:9 default) without exposing this variable to the user via in-player controls.

### Friction Score

| Dimension | Level |
|---|---|
| Frequency | High — occurs on any non-16:9 content |
| Experience impact | High — changes the perceived quality of the video |
| Workaround difficulty | High — no in-app alternative exists |

**Friction score: 8/10**

### Competitive Analysis

| App | Solution |
|---|---|
| VLC | In-playback menu: 16:9, 4:3, 16:10, Best Fit, Fill |
| Infuse | Pinch-to-zoom in-player + selectable zoom mode |
| MX Player | Double-tap to cycle between modes |
| Plex | Per-session setting saveable per title |

### Proposed Solution

Option A: Quick toggle button in player overlay cycling FIT > FILL > CROP > ZOOM
Option B: Long press on aspect icon > bottom sheet with all options

Recommended: A as default + B accessible from advanced menu.

### Impact Logic

- Friction reduction: user reaches optimal display in 1 tap instead of 0 options
- Perceived quality: experience feels more premium because the user has control
- Retention: less frustration, fewer session abandonments

## Friction Point #2 — Catalog Grid Customisation

### The Problem

When browsing a folder containing films or series, the display grid is fixed. The user cannot choose columns, switch to list view, change thumbnail size, or sort the catalog layout.

**What happens in practice:**
- On a tablet or TV, the default grid shows a fixed number of columns that doesn't use the available space
- Users with large libraries cannot efficiently scan the catalog
- Users who prefer list view (title + metadata) don't have this option

### Root Cause

The catalog view is hardcoded into a single layout. There is no user configuration logic for the library UI.

### Friction Score

| Dimension | Level |
|---|---|
| Frequency | Medium-high — every browsing session |
| Experience impact | Medium — doesn't block, but degrades navigability |
| Workaround difficulty | High — impossible without settings |

**Friction score: 7/10**

### Competitive Analysis

| App | Solution |
|---|---|
| Plex | Grid/list toggle + tile size selection |
| Infuse | 3 modes: compact grid, expanded grid, list |
| Emby | Per-folder persistent view settings |
| Jellyfin | View toggle + card size slider |

### Proposed Solution

Level 1 (MVP): Add column control icon at top of folder screen: [2 col] [3 col] [4 col] [List]
Level 2: List view with small thumbnail + title + year + duration
Level 3: Per-folder preference persistence

### Impact Logic

- Navigation efficiency: dense grid = less scrolling for large catalogs
- Perceived control: customisation = ownership, higher retention
- Accessibility: users with visual impairments prefer large elements; power users prefer density

## Friction Mapping Summary

| # | Friction | Priority |
|---|---|---|
| 1 | Non-configurable aspect ratio | P0 |
| 2 | Non-customisable grid | P1 |

## UX Principle

Both friction points emerge from the same pattern: the app treats the user as a passive consumer rather than someone with their own preferences. Not offering control over these parameters is not neutrality — it is friction disguised as default.

## Author

**Matteo Stella** — Digital Product & UX Operations
blackstardigitalstudio.com
