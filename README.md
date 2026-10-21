# USC website publishing

This repository contains automation configuration only. The website source remains in a separate private repository and is read using a repository-scoped, read-only deploy key stored in Actions secrets. Public visitors cannot access that key or the private repository.

The standard public GitHub runner checks for source changes roughly every five minutes (schedules may be delayed by GitHub). It builds and publishes only when the source commit differs from the live website. A manual run is available through Actions. No action artifacts, caches, paid runner types or external subscription are configured.

The workflow publishes to the existing ChatGPT Sites receiver using a separate, website-scoped secret. Publication records contain commit IDs and timestamps, never source files or credentials. A weekly record update keeps this public schedule from becoming inactive.
