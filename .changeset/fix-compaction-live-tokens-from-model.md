---
"@martian-engineering/lossless-claw": patch
---

Fix LCM compaction `observedTokens` to prefer the host-observed, model-returned prompt token count from `runtimeContext.usage` / `lastCallUsage` / `promptCache.lastCallUsage` over the stale `maintenance.currentTokenCount` counter. The deferred-compaction drain now consults the persisted compaction-telemetry snapshot as an additional fallback. Resolves the "compacted but still over target" wedge that pinned long sessions (e.g. session 996 on the `zte / co-claw` 128k model) into an unrecoverable loop.