# DSH Schema Migration Proof

对 DeepSeek Harness schema 迁移的离线内容寻址证据层。它只核验固定 fixture envelope：输出确定性、重复执行幂等、可逆回滚、必需不变量以及有损字段披露；绝不执行迁移、连接数据库或返回数据正文。

它不是迁移运行器，也不复制恢复演练、跨表面契约或血缘账本。`dsh-recovery-proof` 验证隔离恢复，`dsh-surface-contract-proof` 比较 ToolRuntime/MCP/CLI envelope，`dsh-lineage` 记录对象关系；本插件只给固定工具 revision 与 source/target schema 的迁移测试证据判分。

manifest 仅含稳定 ID 与 SHA-256。正文、data、payload、秘密、凭据、prompt、message 形字段会被拒绝；必需不变量缺失、失败或未观察都会失败闭合。DSH/CLI 只读 workspace 内显式文件并向 `artifactDir` 写回读验证产物；MCP 只处理有界内联 JSON。

MIT
