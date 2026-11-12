## Runtime

| Item | Value |
| --- | --- |
| Harness | pi coding agent (managed install) |
| Version | 1.5.2 |
| Provider | LM Studio (`pi-lmstudio` extension) |
| Model | `qwen/qwen3.8-27b` (local, LM Studio 0.4.28) |
| Reasoning level | medium |
| Working directory | `/home/user` |

## Configuration

- **Settings** (`~/.pi/agent/settings.json`): declares the installed extension packages (see below).
- **Web search** (`~/.pi/agent/web-search.json`): provider `searxng`, base URL `http://localhost:8080` (local SearXNG instance).
- **Memory**: enabled via `pi-memory` — long-term notes in `MEMORY.md`, daily logs, and a scratchpad; qmd-powered hybrid (BM25 + semantic) search.

## Installed Extensions (packages)

| Package | Version | Description |
| --- | --- | --- |
| `npm:pi-lmstudio` | 1.5.0 | LM Studio model provider extension (local inference) |
| `npm:pi-web-access` | 0.47.0 | Web search, URL fetching, GitHub repo cloning, PDF extraction, YouTube video understanding |
| `npm:pi-memory` | 0.4.2 | Memory extension: long-term memory, daily logs, qmd-powered semantic search |
| `npm:@tobilu/qmd` | 2.8.3 | QMD — on-device hybrid markdown search (BM25 + vectors + LLM rerank) |
| `npm:@juicesharp/rpiv-ask-user-question` | 2.15.0 | Structured questionnaire tool for asking the user clarifying questions mid-task |

## Skills

| Skill | Source | Description |
| --- | --- | --- |
| `qmd` | `@tobilu/qmd` | Search local markdown knowledge bases, notes, docs, and wikis with QMD — find notes, inspect wikis, answer from indexed markdown |

## Built-in Tools

- `read` — file inspection (text & images)
- `bash` — command execution
- `edit` — precise text-replacement edits
- `write` — create/overwrite files
- `web_search` / `fetch_content` / `get_search_content` — research pipeline (via `pi-web-access`, SearXNG backend)
- `source_check` — evidence gathering for fact-checking
- `memory_read` / `memory_write` / `memory_search` / `memory_forget` / `memory_restore` / `memory_status` — memory management (via `pi-memory`)
- `scratchpad` — persistent to-fix-later checklist
- `ask_user_question` — structured user questionnaires (via `rpiv-ask-user-question`)

## Conventions in Use

- Output files are written only under `~/AI/` or `~/News/`.
- No file deletions without explicit permission.
- No installing packages/tools without asking first.
