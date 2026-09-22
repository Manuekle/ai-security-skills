# RAG Threat Patterns

Review for:

## Cross-tenant retrieval
Index/query metadata fails to constrain organization or user scope.

## Ingestion poisoning
A source injects misleading or malicious content into the trusted knowledge corpus.

## Indirect prompt injection
Retrieved text attempts to alter agent/tool policy.

## Metadata loss
Tenant/source/sensitivity metadata disappears during chunking or reindexing.

## Stale authorization
A user's permissions change but indexed/retrieved content remains accessible.

## Deletion mismatch
Primary content is deleted while chunks, embeddings, caches or derived artifacts remain.

## Sensitive embedding pipeline
Raw content is sent to an embedding provider contrary to data handling requirements.

## Cache leakage
Semantic/retrieval caches omit tenant or authorization context in their keys.
