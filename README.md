# DB Workspace (dbws): downloads

**Database development with guard rails, for humans and AI agents.** One `db` command for SQL Server, PostgreSQL,
MySQL and SQLite across LOCAL, DEV, QA, UAT and PROD: schema snapshots you can search offline, task-based changes
with dry runs and typed confirmations, and a read-only MCP server so AI agents (Claude Code, Copilot, Qwen) can help
without being able to change your data.

Free to use, including for work. Closed source: this repository only hosts the releases.

## Install (latest: 0.9.0)

Needs Python 3.10+ and git. For SQL Server also Microsoft ODBC Driver 18.

```powershell
# recommended: pipx puts `db` on your PATH in its own environment (https://pipx.pypa.io)
pipx install "dbws[all] @ https://github.com/nitinkokane3/dbws-releases/releases/download/v0.9.0/dbws-0.9.0-py3-none-any.whl"

# or in a virtual environment
python -m venv .venv
.venv\Scripts\pip install "dbws[all] @ https://github.com/nitinkokane3/dbws-releases/releases/download/v0.9.0/dbws-0.9.0-py3-none-any.whl"
```

Extras: `sqlserver`, `postgres`, `mysql`, `mcp`, `ui`, `chat`, or `all`.
Verify a manual download against `SHA256SUMS` in the release: `certutil -hashfile <file> SHA256` (Windows) or
`sha256sum <file>` (Linux/macOS).

## Start

```powershell
db init my-databases      # a workspace folder: config, AI agent rules, hooks, docs, git repository
cd my-databases
db doctor                 # checks drivers, config and credentials
db sample ; db use sample --env local ; db schema pull
db ui                     # local web UI: add your databases with the wizard
```

The workspace's own README and `docs/` explain daily use. Upgrading: install the new version the same way, then
run `db init --refresh` in each workspace and review the changes with `git diff`.

## Your data

Everything runs on your machine: no telemetry, no account. Credentials stay in the operating system's credential
vault. The optional chat sends questions, schema information and capped query results to Anthropic's API with your
own key; leave out the `chat` extra if that is not acceptable for your data.

## License, support

Free to use under the [freeware license](LICENSE) (you may share unmodified copies at no charge; no modifying or
reselling). Open-source components: [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).

Problems or questions: open an issue here, attaching the file from `db doctor --report` (it replaces server and
database names with aliases and contains no credentials, SQL or data), or e-mail nitinkokane3@gmail.com.
