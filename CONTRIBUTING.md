# Contributing

## Start with an issue

Begin with an existing GitHub Issue or open one before significant work. Check
the Foundry Development project to avoid duplicating active or planned work.
Meaningful pull requests should link to an Issue unless they are urgent repairs
or trivial documentation corrections.

## Work boundaries

- Confirm the canonical source and ownership boundary before implementation.
- Keep changes focused and preserve repository-specific architecture boundaries.
- Record blocking dependencies rather than silently changing scope.
- Put architecture decisions in repository documentation or ADRs when behavior,
  ownership, or security boundaries change.

## Validation and review

- Include tests and validation evidence appropriate to the change.
- Document documentation updates, rollout impact, rollback considerations, and
  remaining risks in the pull request.
- Do not bypass branch protections or required reviews.
- Human approval is required for destructive, security-sensitive,
  privilege-expanding, or release-affecting changes.

## AI-assisted work

AI may inspect, draft, implement, test, document, and prepare pull requests, but
must operate within the repository's AI contribution policy. AI contributors
must disclose material uncertainty, document tests performed, and must not
approve or merge their own protected work.

Repository-specific contribution and security instructions take precedence.
