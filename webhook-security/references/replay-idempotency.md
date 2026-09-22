# Replay and Idempotency Patterns

A robust consumer should tolerate:

- duplicates
- delayed delivery
- out-of-order events
- provider retries
- consumer retries
- worker crash after partial completion

Useful patterns:

- unique event ID table with atomic insert
- transactional outbox/inbox where warranted
- idempotency key tied to operation scope
- state transition checks rather than blind writes
- retry counters with dead-letter handling

Do not equate signature validity with uniqueness; a valid signed event can still be replayed.
