# Project Dart SDK

## Problem

Trunk system Dart formatting can disagree with the project language version and CI SDK.

## Scope

Use Flutter 3.47.7 and its bundled Dart 3.13.5 for app development and CI.
Disable the Trunk Dart linter so project commands own Dart formatting.
Preserve published package SDK floors and public APIs.
Include existing SDK migration and reproducible generated-code changes, but keep unrelated tool upgrades out.
No UI, native release, device installation, or package publication is included.

## Acceptance

- No enabled `dart@SYSTEM` formatter.
- CI installs the selected SDK explicitly.
- Project dependency resolution, formatting, analysis, and relevant tests pass.
- Generated changes come from the supported generator.

## Constraints

Package language versions follow the lower Dart SDK bound, even when development tools need a newer SDK.
Flutter and Dart commands run sequentially.
