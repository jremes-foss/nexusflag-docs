# NexusFlag Documentation Source

This repository contains the official documentation source code for **NexusFlag**, a lightweight, high-performance, open-source CTF (Capture The Flag) API built with FastAPI and SQLAlchemy.

The live documentation site is published at: **[https://jremes-foss.github.io/nexusflag-docs/](https://jremes-foss.github.io/nexusflag-docs/)**

---

## Repository Structure

## Local Development

You can preview and edit the documentation locally before pushing changes.

### Prerequisites

- Python 3.9+
- Pip: Package installer for Python

### Setup & Local Server

Clone the repository:

```
git clone git@github.com:jremes-foss/nexusflag-docs.git
cd nexusflag-docs
```

Install Mkdocs Material:

```
pip install mkdocs-material
```

Start the local preview server:

```
mkdocs serve
```

View in browser: Open `http://127.0.0.1:8000` in your web browser. The server automatically reloads whenever you edit files inside `docs/` folder.

## Deployment Workflow

Documentation deployment is fully automated via GitHub Actions (`.github/workflows/deploy.yml`). Whenever changes are pushed to the `main` branch, the deployment workflow builds the MkDocs site and deploys it directly to GitHub pages.

## Related Repositories

Main application repository: [NexusFlag](https://github.com/jremes-foss/NexusFlag).

## License

The documentation content in this repository is licensed alongside the NexusFlag project under the GNU Affero General Public License v3.0 (AGPL-3.0).

