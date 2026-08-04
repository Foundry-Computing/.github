# Release Policy

## Release expectations

Releases should be traceable to reviewed changes, linked issues where relevant,
and recorded validation evidence.

## Approval model

- Human approval is required for meaningful releases.
- Security-sensitive or user-impacting releases require explicit review of risk,
  rollback, and migration impact.
- AI contributors may prepare release artifacts or notes only within approved
  repository scope and must not independently publish protected releases without
  authorization.

## Minimum release record

A release-capable repository should document:

- what changed
- why it changed
- validation performed
- migration impact
- rollback or containment plan
- known limitations or follow-up work

## Emergency repair releases

Emergency repairs should be minimized, documented immediately, and followed by
post-release review and cleanup tasks.
