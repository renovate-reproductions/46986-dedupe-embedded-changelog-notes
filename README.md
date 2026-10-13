# Duplicate embedded changelog notes

Reproduction for [renovatebot/renovate#46986](https://github.com/renovatebot/renovate/pull/46986).

The `nextcloud` datasource returns the changelog of each release with the release itself (embedded notes).
All apps in `nextcloud-apps.txt` update together in one grouped PR.

## Samples

1. **Same dependency, two current versions:** Calendar is listed twice (`5.5.0` and `5.5.5`), and both entries update to `5.5.9`.
2. **Different dependencies:** Contacts updates to `7.3.9` in the same PR.
   This is the case fixed by [renovatebot/renovate#46733](https://github.com/renovatebot/renovate/pull/46733): embedded notes of different dependencies must all be kept.

## Current behavior

The PR body shows the Calendar `5.5.9` release notes twice, once for each Calendar entry, and the Contacts `7.3.9` notes once.

## Expected behavior

The PR body shows the Calendar `5.5.9` release notes once and the Contacts `7.3.9` release notes once.
