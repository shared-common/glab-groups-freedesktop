# glab-groups-freedesktop

Thin GitHub Actions wrapper for the freedesktop.org namespace mirror.

## Scope

- Loads `gh-actions-cfg/glab-groups-freedesktop`
- Calls the reusable workflow in `glab-groups-shared@mcr/main`
- Uses the BWS target PAT secret `GL_PAT_GROUP_FREEDESKTOP_SVC`
- Mirrors the current public top-level `gitlab.freedesktop.org` groups into
  `freedesktop/*` beneath `glab-forks`
- Runs deterministic mirror batch shards with five jobs max in parallel
- Schedules at minute 5 of hours 1, 7, 13, and 19 UTC
- Publishes discovery, plan, report, CSV, JSON, and Parquet artifacts for each run

## Validation

```sh
python3 -m unittest discover -s tests
```
