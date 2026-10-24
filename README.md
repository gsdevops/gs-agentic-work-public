# GS DevOps public package status

This repository contains public version metadata for the private Galil Software GS DevOps package.

## Version discovery

Anonymous clients read `latest.json` on `main` via:
https://raw.githubusercontent.com/gsdevops/gs-agentic-work-public-status/main/latest.json

The private source release workflow updates it after successful package publication. Metadata contains
only package/version, publication time, archive checksum, private release link and download access flag.
No source code, prompts, customer information, credentials or transcripts are published here.

## Package access

The package ZIP remains private. Download requires authorized GitHub access. Public version discovery
does not grant access to the package or trigger automatic installation. Unavailable discovery means
latest version unknown. The GS launcher checks for upgrades; package users explicitly approve updates.
