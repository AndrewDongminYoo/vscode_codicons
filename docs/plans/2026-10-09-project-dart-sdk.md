# Project Dart SDK plan

## Approved direction

The operator requested application SDK upgrades and compatible plugin formatting through the PR loop.
The operator approved existing staged changes related to that migration.

## Steps

1. Inspect manifest constraints, staged changes, Trunk settings, and SDK installations in `.github/workflows/`.
2. Disable Trunk Dart formatting and pin installed CI SDKs.
3. Resolve affected manifests and regenerate affected code through its owning generator.
4. Verify non-mutating Dart format checks, analysis, tests, and scoped Trunk checks.
5. Review the complete migration, commit by concern, push, and open a PR for operator merge.

## Verification

An ad hoc YAML inspection found floating or outdated SDK installations before the changes.
The final inspection reads every Flutter action and reusable package-workflow SDK input, plus the Trunk Dart disable list.
It is a manual migration check recorded in Git-local state, not a permanent CI regression test.
Run `flutter pub get`, `dart format --output=none --set-exit-if-changed lib test`, `flutter analyze`, and `flutter test` at each Flutter package root, with existing project-specific roots and exclusions.
Use `dart pub get`, `dart analyze`, and `dart test` for pure Dart workspace packages.
Run `trunk check` for the changed configuration and documents.
Record actual commands and limitations in the PR and Git-local loop state.

Use the existing formatter page width from `analysis_options.yaml` or the declared CI command.
