# Versioning

This repository holds two separate products. Each one has its own version number, changelog, tags and releases.

| Product | Folder | Changelog | Tag format |
| --- | --- | --- | --- |
| Claude version | [`claude/`](claude/) | [`claude/CHANGELOG.md`](claude/CHANGELOG.md) | `claude-vX.Y.Z` |
| ChatGPT version | [`chatgpt/`](chatgpt/) | `chatgpt/CHANGELOG.md` (created with its next version) | `chatgpt-vX.Y.Z` |

## Version numbers

Versions use three numbers, MAJOR.MINOR.PATCH:

- **MAJOR** changes when an update breaks something that already exists, such as the folder structure or the settings format.
- **MINOR** changes when a new feature is added.
- **PATCH** changes for a fix.

A change that only touches documentation gets no new version, no tag and no release.

## Changelog

Each product keeps a `CHANGELOG.md` in its own folder, with the newest version first. Every version gets a section written for users, in plain language. The same text becomes the notes of its GitHub release.

## How a version is published

Every change reaches the default branch (`main`) through a branch and a pull request. Nothing is committed or pushed directly on `main`.

To publish:

1. Bring `main` up to date locally.
2. Create a branch from it:
   - `release/<product>-vX.Y.Z` for a version, for example `release/claude-v2.10.0`;
   - `docs/<short-name>` for a change to the documentation only.
3. Commit on that branch under the owner's own Git identity, with a plain message and no attribution lines.
4. Push the branch and open a pull request. Title: the version number and a few words. Body: the changelog section for this version, in plain language for users.
5. Merge it with a merge commit (`gh pr merge --merge --delete-branch`), not a squash and not a rebase.
6. Tag the merge commit on `main` with the product's tag (`claude-vX.Y.Z` or `chatgpt-vX.Y.Z`) and create the GitHub release, with the changelog section as its notes. A documentation-only change stops after step 5: no version, no tag, no release.

To only open a pull request, stop after step 4.

## Rules

- Never force-push `main`.
- Never move or delete a tag that has been pushed.
- Never rewrite existing history.
