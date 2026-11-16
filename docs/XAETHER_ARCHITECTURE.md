# XAETHER VERSE architecture baseline

## Purpose

This repository begins as a fork of Open 3D Engine. The long-term product is **XAETHER VERSE**, a persistent living world and Home Hub experience, not a separate game built beside an engine.

## Core structure

- **XAETHER VERSE runtime:** The O3DE fork evolves into the foundational runtime for the XAETHER VERSE.
- **XAE Studio:** XAE Studio is the modular creation package that lives inside the XAETHER VERSE. It brings together the protected builder system and the everyday member creation system without making either one a separate outside application.
- **XAEforge:** XAEforge is the protected advanced builder, software, engineering, and developer system inside XAE Studio and the XAETHER VERSE.
- **XAEmerge:** XAEmerge is the everyday member creation system inside XAE Studio and the XAETHER VERSE for voice-led ideas, object scans, photos, video, uploads, previews, and approved publishing.
- **Creator access:** Approved creators, developers, employees, contractors, and authorized AI agents receive role-based, scoped access through XAEforge.

## XAE Studio package

XAE Studio is a modular package inside the XAETHER VERSE, not a separate application. It has two connected but independently replaceable sides:

- **XAEforge:** the advanced workspace for approved builders, developers, employees, contractors, and authorized AI agents. It provides secure workspaces, code and project tools, build and test tools, previews, publishing, permissions, and approval gates.
- **XAEmerge:** the simple creation experience for everyday members. Members can speak an idea, scan an object, upload photos or video, review an AI-generated proposal, and submit it into their personal Home Hub, social spaces, or the shared Verse under the appropriate permissions and approval rules.

XAEforge and XAEmerge share documented interfaces for assets, previews, permissions, publishing, and world placement. Either side can evolve without forcing a rewrite of the other side or the rest of the XAETHER VERSE.

## Local-first foundation

The core engine and world experience must be designed to run locally on each supported device. Android delivery is packaged as an application for testing and distribution through Google Play and the Samsung Galaxy Store. Local device and emulator testing are first-class development paths.

Networked services must be additive rather than required for core local operation. Synchronization, social presence, shared worlds, publishing, and community services should use clear interfaces so they can evolve independently of the local runtime.

## Universal modular design requirement

Every XAETHER VERSE feature and component must be built as a modular design from day one. This includes XAE Studio, XAEforge, XAEmerge, the Home Hub, social systems, world areas, downtowns, lots, buildings, interiors, avatars, economy services, capture tools, publishing, and future systems.

Each module must be independently buildable, testable, updateable, replaceable, and scalable without requiring a rebuild of the full Verse.

1. Keep XAETHER modules behind explicit interfaces and contracts.
2. Isolate O3DE-derived integrations behind adapters where practical.
3. Avoid embedding XAETHER product rules directly into unmodified upstream engine code unless there is no clean extension point.
4. Keep XAETHER-owned code, data schemas, tooling, and tests in clearly named modules.
5. Replace O3DE-derived components gradually as XAETHER-owned equivalents are ready, without a single disruptive separation effort.
6. Retain required upstream license and notice material for code that remains derived from O3DE.
7. Define streaming, loading, and performance boundaries for every world-facing module so the runtime loads only the nearby or actively used pieces.

This structure ensures XAETHER VERSE can progressively become its own engine while preserving a stable, buildable product throughout the transition.

## XAEforge core, first build layer

The first major XAETHER-specific build layer is the core XAEforge system inside the runtime:

- secure creator workspaces
- role-based permissions and temporary scoped access
- project and source-control integration
- build, test, preview, and publishing workflows
- approval gates for sensitive systems and releases
- auditability for privileged actions

Once this core exists, later XAETHER VERSE systems can be built and expanded through it: Home Hub creation, social spaces, persistent world systems, creator publishing, economy services, avatars, and other world features.

## XAEmerge member creation layer

**XAEmerge** is the everyday member creation layer inside the XAETHER VERSE. It is distinct from XAEforge, which remains the protected software, engineering, and advanced builder environment.

XAEmerge lets regular members contribute to their Home Hub, social spaces, and world experience without using developer tools. The first version must support:

- voice descriptions that an AI turns into proposed assets or experiences
- object scans, photos, video, and uploads that an AI converts into proposed 3D content
- clear previews before anything is added to a Home Hub, social space, or shared world
- member ownership, privacy controls, permissions, and approval rules for every contribution
- modular interfaces between capture, AI generation, asset processing, preview, publishing, and shared-world placement

XAEmerge is a local-first module. Capture, drafts, previews, and personal Home Hub work should function locally where practical. Shared publishing, collaboration, and social distribution remain additive networked services behind explicit interfaces.

## Home Hub module

The Home Hub is a first-class modular XAETHER VERSE system, not a hard-coded screen or a one-off world map. It is a member's primary personal space and must remain independently buildable, testable, and replaceable.

The initial Home Hub module includes:

- member identity and Home Hub profile data
- local capture, scan, photo, video, and upload intake through XAEmerge
- personal home scenes, owned assets, layouts, and saved drafts
- preview and approval flows before personal or shared-world publishing
- privacy, ownership, access, and sharing controls
- adapters to social spaces, world travel, avatar systems, economy services, and notifications

The Home Hub owns its personal-state rules. It connects to other modules through documented interfaces, so social, scanning, rendering, or publishing components can change without breaking the member's Home Hub.

## Downtown and world construction modules

Downtowns and other world areas must also be modular. A city is assembled from independently managed world components rather than one permanent, indivisible build.

Each downtown must separate:

- open lots and parcels, aligned as closely as practical to real-world lot parcels and preserved for future development
- districts and zoning or world-rule data
- roads, transit, utilities, and public spaces
- exterior buildings, interiors, and interactive services
- environmental systems such as lighting, weather, sound, and traffic
- local ownership, permissions, economy hooks, and publishing rules

A downtown composition module coordinates those pieces, while each lot, building, interior, service, and district remains independently updateable. The runtime should stream only the nearby areas and features a member is using, rather than loading an entire downtown or universe at once.

## Developer documentation rule

Coders do not need to guess the architecture. Every module must carry a short technical guide that states:

1. its purpose and ownership
2. its local-first behavior and performance boundaries
3. its data model and permission model
4. the public interfaces it provides and depends on
5. its tests, build path, and replacement path from O3DE-derived code
6. how it fits into the XAE Studio, Home Hub, world, or other relevant modular composition

## Implementation rule

Every new XAETHER feature proposal must identify its module boundary, local-first behavior, permissions model, interfaces to other modules, performance and streaming boundaries where relevant, and a replacement path if it depends on O3DE-derived code.
