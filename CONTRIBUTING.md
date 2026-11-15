# Contributing

Reports are the most useful contribution. If `gct` reads a figure wrongly, misses one, or a command fails, open an [issue](https://github.com/GoCarbonTracker-Hq/go-carbon-tracker/issues) with the command you ran and what it printed.

Do not attach a real company report, a workspace folder or a package unless you are free to publish it. Issues are public. If the problem only shows on a private document, describe the page (a table with merged header cells, a figure in a footnote) or rebuild it on the sample report in `examples/`. `gct troubleshoot export` writes a folder with the version and the run log; read it before you attach it, for the reasons under [Status](README.md#status).

A security problem goes through the private form described in [SECURITY.md](SECURITY.md), not an issue.

## Pull requests

Small fixes to the code, tests and documentation are welcome. For anything larger, such as a new command, a new reading step or a change to the stored data, open an issue first so the approach can be agreed before you write it.

Set up the contributor install ([docs/setup.md](docs/setup.md) has the detail):

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -e '.[dev]'
pip install 'setuptools>=77'
pytest
```

Before you open a pull request:

- Run `pytest` and paste its last line (`N passed, M failed`) into the description. Some tests skip when a tool is absent; `pytest -rs` says which.
- Add or change a test for any behaviour you change.
- If you change what a command does, update the page under `docs/` that describes it.
- Keep one topic per pull request.

`main` is protected: changes reach it through a pull request.

## Things the tests hold in place

- **The README.** Several tests read `README.md` and require the sections Setup, Status, Claims and What works today, with certain sentences in them (`tests/test_setup_guide.py`, `tests/test_troubleshoot.py`, `tests/test_models.py`). If you edit the README, run those three files.
- **Privacy wording.** No document may promise that a sanitised output is free of private content. The tests reject that wording because the sharing features are not verified ([Status](README.md#status)).
- **The stored data.** Tables are append-only. A change to the schema needs a numbered migration under `gct/workspace/migrations/` and an entry in [docs/migrations.md](docs/migrations.md).
- **The viewer.** The built viewer in `gct/viewer_dist/` is committed, so users never need Node. If you change the source under `viewer/`, rebuild it as [viewer/README.md](viewer/README.md) describes and commit the build with the source.

## Licence of contributions

The project is under the [MIT licence](LICENSE), and contributions are accepted under the same licence. If you copy or adapt code from elsewhere, add a row to [ORIGINS.md](ORIGINS.md) with its source and licence.
