---
"@martian-engineering/lossless-claw": patch
---

Treat a threshold sweep that made progress but still misses the ideal target as settled when the projected post-sweep prompt stays within the token budget. Stored compaction cannot shrink fixed runtime framing (anchors, tool schemas, fresh tail), so an in-budget projection no longer pins deferred-compaction debt behind a summary spend backoff — avoiding near-budget degradation getting stuck on the host's raw-transcript precheck. Without an observed prompt token count, the previous strict judgment is preserved.
