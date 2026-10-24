# gs-devops public releases

Published packages of **gs-devops**, Galil Software's DevOps agents and skills for Claude Code.
The source repository is private. This repository holds only what engineers need to install and
upgrade the package:

- **Releases**: one per version (`vX.Y.Z`), each with `gs-devops-X.Y.Z.zip` and its `.sha256`.
  The ZIP contains the agents, skills, installer, package README and release notes. It does not
  contain the source repository, development records, customer data, credentials or transcripts.
- **`latest.json`**: the newest version, its SHA-256 and release link. The package's upgrade commands
  read it. No GitHub login is needed for it or for the downloads.

Everything here is written by the private repository's release workflow. Don't edit files here;
the next release overwrites them.

## Install

1. Download `gs-devops-X.Y.Z.zip` and `gs-devops-X.Y.Z.zip.sha256` from the latest release.
2. Check the archive: `shasum -a 256 -c gs-devops-X.Y.Z.zip.sha256` (Linux: `sha256sum -c`).
3. Extract it, read its `README.md`, then run `python3 install.py --dry-run` and `python3 install.py`.

## Upgrade

In Claude, run `/devops-upgrade-check`, then `/devops-upgrade`. The upgrade shows a preview first,
refuses to overwrite local changes and keeps a backup of the replaced files.

Installed versions from before downloads moved here (0.4.0 and earlier) can't fetch from this
repository themselves. Upgrade those once with the helper from the latest ZIP:

```bash
python3 gs-devops-X.Y.Z/skills/gs-devops-core/scripts/package_manager.py upgrade
python3 gs-devops-X.Y.Z/skills/gs-devops-core/scripts/package_manager.py upgrade --apply --version X.Y.Z
```

The first command only previews. The second replaces the package after you've reviewed the preview.
