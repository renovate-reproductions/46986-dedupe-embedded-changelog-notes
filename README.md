# Duplicate embedded changelog notes

Reproduction for [renovatebot/renovate#46986](https://github.com/renovatebot/renovate/pull/46986).

The `nextcloud` datasource returns the changelog of each release with the release itself (embedded notes).
`nextcloud-apps.txt` lists the same app twice, at two different current versions, so both entries update to the same new version in one grouped PR.

## Current behavior

The PR body shows the Calendar release notes of the target version twice, once for each entry.

## Expected behavior

The PR body shows the Calendar release notes of the target version once.
