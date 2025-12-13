# Claude Code Guidelines for This Repository

## Overview

This is a **fork** of [jellyfin/jellyfin](https://github.com/jellyfin/jellyfin), used for personal home server deployment.

## Critical Guidelines

### Avoid Core Data Model Changes

**Above all else, avoid making changes to the core data model that would be difficult to integrate with upstream.**

This means:
- Do not modify database schemas in ways that diverge from upstream
- Do not change entity relationships or primary key structures
- Do not alter serialization formats for persisted data
- Do not add new required fields to existing entities

### Preferred Approach for Changes

1. **Performance optimizations** (like caching) are acceptable as they don't change the data model
2. **Bug fixes** should be upstreamable when possible
3. **New features** should be implemented in a way that could be contributed back to upstream
4. If a data model change is truly necessary, document it clearly and consider the migration path

### Syncing with Upstream

This fork should periodically sync with upstream jellyfin/jellyfin. Keeping changes minimal and non-invasive to the data model ensures smooth rebasing/merging.

### Tagging Strategy

Use `fork/v*` tags to avoid collisions with upstream's `v*` tags:
- Upstream uses: `v10.11.4`
- This fork uses: `fork/v10.11.4`

This allows pulling upstream tags without conflicts.
