# Changelog

What changed in the tool and its documentation, newest first. Each entry starts with a status word:

- **Added:** new in the repository.
- **Changed:** works or reads differently from before.
- **Fixed:** was wrong, now corrected.

Versions follow the `version` in `pyproject.toml`. Only `v0.2.1-alpha` is published as a GitHub release; the earlier versions are points in the git history, and their entries below are short because that is all their release notes recorded.

## Unreleased

- **Added:** `CONTRIBUTING.md`, `SECURITY.md` and this changelog.
- **Changed:** the README is rewritten for a first-time visitor, with two figures under `assets/readme/`. Its quick start no longer calls `gct restate` without a subcommand, which exited with an error.
- **Changed:** the README says that Docling reading and the climatebert sentence filter are off unless turned on.
- **Fixed:** the README citation no longer says arXiv; the paper was never submitted there.
- **Fixed:** `gct extract` no longer joins a dated period header to the metric wording of a claim.
- **Changed:** the clone address is `GoCarbonTracker-Hq/go-carbon-tracker`.

## 0.2.1-alpha, 2026-11-02

- **Added:** metric list v3, with count and currency unit families, so headcount, board, safety, spend and financial totals form series next to emissions, energy, water and waste. See `docs/matching.md`.
- **Changed:** a workspace made by an older version upgrades through migration 0023 the first time this version opens it.

## 0.2.0-alpha, 2026-10-25

- **Added:** an optional Docling reading mode for `gct read`.
- **Added:** version 2 of the scorer used to measure extraction against a gold set.
- **Added:** `segment` as a reporting boundary.
- **Added:** `gct infer` proposes each claim's period and boundary from the report's wording.
- **Changed:** figure headers that run over several lines are read as one header, and segment names are matched by their longest form.

## 0.1.5-alpha, 2026-10-25

- **Added:** flag candidates and their four-type taxonomy are shown in the viewer.

## 0.1.4-alpha, 2026-10-25

- **Added:** `gct flag propose`, which lists claims a reviewer may want to look at, grouped by a four-type taxonomy. A candidate is a proposal; only a reviewer raises a flag.

## 0.1.3-alpha, 2026-10-25

- **Added:** an optional sentence filter in `gct extract` that uses the `climatebert/environmental-claims` model on the user's computer.

## 0.1.2-alpha, 2026-10-24

- **Changed:** the public README was restored and brought up to date.

## 0.1.1-alpha, 2026-10-24

- **Fixed:** extraction and viewer problems found after the first preview.

## 0.1.0-alpha, 2026-10-24

- **Added:** the first developer preview.
