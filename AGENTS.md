# Base44 Dev Environment

## Project Overview
This is **thelastkadymusic** — an independent music label project. The repo is currently a blank slate: it contains only a README, a LICENSE, and an empty `Mon_site_de_base.html` ("My base site" in French). There is no application code, framework, or backend yet.

## Running the App
```bash
docker compose -f docker-compose.base44.yml up -d
```
- Serves the repo directory on **host port 3000** via a Python static file server (`python -m http.server`).
- The preview shows a directory listing until real HTML/content is added to `Mon_site_de_base.html` or an `index.html` is created.
- No external credentials or secrets are needed.
- Changes to files in the repo are immediately visible (static server, no build step).

## Notes
- The repo root directory has restrictive permissions (700), which prevented nginx's worker process from reading bind-mounted files. The Python server runs as root and is not affected.
- No dependencies, no migrations, no build step — this is a static-only project at present.
