# Security

This plugin never executes migrations, opens databases, starts child processes or discovers live state. It validates explicit, revision-bound, digest-only evidence and rejects body-, data-, payload-, credential-, prompt- and message-shaped fields.

DSH/CLI read one bounded workspace-relative regular file, reject traversal and symlinks, and write only beneath an explicit workspace-relative `artifactDir` with content addressing and read-back verification. MCP accepts bounded inline JSON and performs no filesystem or network access.

Report vulnerabilities through GitHub Security Advisories without attaching private data or credentials.
