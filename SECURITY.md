# Security

## Supported versions

GoCarbonTracker is alpha software. Only the newest release gets fixes; see [Releases](https://github.com/GoCarbonTracker-Hq/go-carbon-tracker/releases).

## Reporting a problem

Report a security problem privately, through GitHub's form: open the repository's [Security tab](https://github.com/GoCarbonTracker-Hq/go-carbon-tracker/security) and choose "Report a vulnerability". Please do not open a public issue for it.

Say which version you ran (`gct --version`), what you did, what happened and what you expected. Do not attach a real company report or a workspace with private content; a description or the sample report in `examples/` is enough to start.

The project has one maintainer, so there is no promised response time. You will get a reply on the report itself, and a fix is credited to you in the changelog unless you ask otherwise.

## What counts

Reports are welcome on anything that lets content or access go where the tool says it does not, for example:

- the local service from `gct serve` answering a request without its session key, or from another computer,
- a command sending document content to an outside service without the approvals described in [docs/models.md](docs/models.md),
- a file added with `gct doc add` causing code to run, or a write outside the workspace folder,
- a way private content reaches a sanitised output or a package that is not already listed below.

## Known limits, already documented

The sharing features are not verified to keep private content out, and the README says so under [Status](README.md#status). These known paths are documented there and in [docs/privacy.md](docs/privacy.md), and none is fixed in the current version:

- a credential in a PDF annotation or in a PDF's metadata,
- a credential in a cell of a CSV or XLSX original that a package copies,
- a credential written in fullwidth characters, which stays in the database files inside a package.

You do not need to report these again. A new path of the same kind is worth reporting.
