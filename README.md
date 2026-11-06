# DSH Schema Migration Proof

**Maintainer / Author：He Fangsheng (贺方升 / 贺去病; Dosen) · [hequbing.com](https://www.hequbing.com)**

Offline, content-addressed evidence for recorded DeepSeek Harness schema migrations. It verifies fixed fixture envelopes for output determinism, idempotent reruns, reversible rollback, required invariants and explicit lossy-field disclosure without executing a migration or returning data bodies.

This is not a migration runner, database tool, recovery system, or second surface-contract verifier. `dsh-recovery-proof` tests isolated restore drills; `dsh-surface-contract-proof` compares ToolRuntime/MCP/CLI envelopes; `dsh-lineage` records object/action relationships. This project scores the evidence produced by a migration test harness whose tool revision and source/target schemas are pinned.

The manifest contains only stable IDs and SHA-256 digests. Body-, data-, payload-, secret-, credential-, prompt- and message-shaped fields are rejected. A required invariant that is missing, failed or unobserved fails closed. A reversible migration must prove rollback, and a lossy fixture must enumerate every disclosed loss field.

## Surfaces

- DSH: `dsh_schema_migration_inspect`, `dsh_schema_migration_verify`.
- CLI: `dsh-schema-migration-proof verify --workspace-root examples --migration migration.json --artifact-dir artifacts`.
- MCP: `schema_migration_inspect_inline`, `schema_migration_verify_inline`; bounded inline JSON only, no filesystem, network, child process or migration execution.

```sh
dsh plugin --profile web add github:dongsheng123132/dsh-schema-migration-proof
npm test
npm run check
npm run smoke:plugin
npm run smoke:mcp
```

MIT
