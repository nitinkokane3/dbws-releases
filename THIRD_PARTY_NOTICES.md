# Third-party notices

dbws includes (vendored) or depends on the following open-source components. Each is used under its own license.

## Included in the package (`dbws/ui/static/`)

| Component | Version | License | Source |
|---|---|---|---|
| htmx | 2.0.4 | 0BSD (Zero-Clause BSD) | https://github.com/bigskysoftware/htmx |
| Pico CSS | 2.0.6 | MIT | https://github.com/picocss/pico |
| Mermaid | 11.4.1 | MIT (the bundle includes dependencies under MIT, ISC, Apache-2.0 and similar permissive licenses) | https://github.com/mermaid-js/mermaid |

When you update a vendored file, update this table and keep the file's license header.

## Python dependencies (installed by pip, not bundled)

| Package | Extra | License |
|---|---|---|
| PyYAML | core | MIT |
| keyring | core | MIT |
| pyodbc | sqlserver | MIT |
| psycopg / psycopg-binary | postgres | LGPL-3.0-only (used unmodified as a separately installed library) |
| PyMySQL | mysql | MIT |
| mcp | mcp | MIT |
| fastapi | ui | MIT |
| uvicorn | ui | BSD-3-Clause |
| Jinja2 | ui | BSD-3-Clause |
| Markdown | ui | BSD-3-Clause |
| python-multipart | ui | Apache-2.0 |
| httpx | ui | BSD-3-Clause |
| anthropic | chat | MIT |
| openai | chat | Apache-2.0 |
| boto3, botocore (via anthropic[bedrock]) | chat-bedrock | Apache-2.0 |
| google-auth (via anthropic[vertex]) | chat-vertex | Apache-2.0 |

Their transitive dependencies carry their own licenses; `pip-licenses` in an installed environment lists them all.
Licenses as reported by the package metadata; re-check when dependency ranges change.
