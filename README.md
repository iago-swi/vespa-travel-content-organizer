# Vespa Travel Content Organizer

A desktop application project for organizing the photos, videos, GPS tracks and travel journals collected during Vespa roadtrips. The common workflow is to prepare a trip, inspect an import preview, and organize media by day, device and content type.

This public repository brings together **two independently developed AI-assisted versions**: one created with **Claude**, the other with **ChatGPT**. They are separate implementations, not interchangeable editions of a single codebase. Their features, folder structures, dependencies and configuration formats may differ. Consolidation preserves both variants; it does not merge their application code or imply profile compatibility.

## Choose a version

| Folder | Implementation | Start here |
| --- | --- | --- |
| [`claude/`](claude/) | Python 3.9+ and Tkinter; import, GPX-assisted geolocation and travel-journal tools | [Claude README](claude/README.md) · [Changelog](claude/CHANGELOG.md) |
| [`chatgpt/`](chatgpt/) | Python 3.12+ and PySide6; configurable trip organization, import preview, verified copies, optional ExifTool and diagnostics | [ChatGPT README](chatgpt/README.md) · [French manual](chatgpt/Manuel-application-FR.md) · [English manual](chatgpt/Manuel-application-EN.md) |

Consult each version's documentation for its exact capabilities and limitations. ExifTool support and behavior differ between variants. Neither application's dependencies need to be installed merely to browse this repository.

```text
vespa-travel-content-organizer/
├── README.md
├── claude/     # Claude implementation, documentation and build scripts
└── chatgpt/    # ChatGPT implementation, documentation and build scripts
```

## Run locally

Clone the common repository:

```sh
git clone https://github.com/iago-swi/vespa-travel-content-organizer.git
cd vespa-travel-content-organizer
```

### Claude version

With Python 3.9+ and Tkinter available:

```sh
cd claude
python vespa_organizer.py
```

On Windows, you can also use `claude/Vespa Organizer.bat`. See the [variant README](claude/README.md) for optional ExifTool installation and the Windows build process.

### ChatGPT version

On Windows with Python 3.12+, run `chatgpt/Lancer.cmd`, or use PowerShell:

```powershell
cd chatgpt
py -3 -m venv .venv
.venv\Scripts\python.exe -m pip install -r requirements.txt
.venv\Scripts\python.exe app.py
```

Run launchers and build scripts from their respective variant directories. Windows build instructions remain in each variant's README; this repository does not provide a shared launcher or a unified release binary.

## Origins and preserved Git history

Both source repositories were public, used `main` as their default branch, and had no other branches or tags when checked on **19 November 2026**.

| Variant | Source repository | Imported branch | Original tip commit | Original commits |
| --- | --- | --- | --- | --- |
| Claude | [iago-swi/vespa-travel-content-organizer-claude](https://github.com/iago-swi/vespa-travel-content-organizer-claude) | `main` | `e23886ac74b520d28dca0b10f8380065a4be4b36` | 3 |
| ChatGPT | [iago-swi/vespa-travel-content-organizer-chatgpt](https://github.com/iago-swi/vespa-travel-content-organizer-chatgpt) | `main` | `ccefae3c0227369a12f02324b00e006bf10df185` | 2 |

Each variant was imported using **`git subtree add` without `--squash`**. All original commits remain reachable from this repository's `main` branch with their original hashes, authors, dates and commit messages. Each imported folder initially matches the corresponding source tree exactly. Older commits naturally show the files at their original repository-root paths; the subtree merge places them in the lowercase variant folders.

To inspect the complete history:

```sh
git log --all --graph --decorate --oneline
```

The source repositories remain unchanged. GitHub issues, pull requests, release downloads and repository settings are not part of Git commit history and have not been migrated.

## Maintaining the variants

Keep changes within the appropriate folder unless they concern the common documentation. To import future source updates with full history, start from a clean working tree and run from the common repository root:

```sh
git subtree pull --prefix=claude https://github.com/iago-swi/vespa-travel-content-organizer-claude.git main
git subtree pull --prefix=chatgpt https://github.com/iago-swi/vespa-travel-content-organizer-chatgpt.git main
```

Do not add `--squash` when preserving the source history. Resolve any conflicts, review the resulting changes and validate the affected variant before pushing.

## Licensing and personal data

Existing license files and third-party notices are preserved within their respective folders. Consolidation does not introduce a new blanket license or change the licensing of either implementation or its dependencies.

Keep actual trip media, personal profiles, local paths, credentials and diagnostic exports out of version control. Use synthetic data for examples and tests.
