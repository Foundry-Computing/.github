# Repository Standards

## Classification system

Foundry repositories should be classified as one of:

- core platform
- application
- integration
- infrastructure
- knowledge archive
- user interface
- automation
- library
- experimental
- archived

## Minimum active-repository baseline

Each active repository should eventually document:

- purpose
- owner and maintainers
- lifecycle status
- supported environments
- dependencies
- build instructions
- test instructions
- release process
- backup or recovery considerations
- security sensitivity
- AI access level

## Delivery model

Recommended defaults for active repositories:

- default branch `main`
- protected default branch
- pull-request-based changes
- at least one required approving review
- dismissed approvals when new commits are pushed
- conversation resolution before merge
- status checks when tests exist
- prevention of force pushes
- prevention of branch deletion
- squash merge preferred
- automatic deletion of merged branches where appropriate

## Community-health baseline

Repositories should adopt or inherit:

- README
- documented LICENSE decision
- CONTRIBUTING guide
- SECURITY policy
- CODE_OF_CONDUCT
- SUPPORT guidance
- issue templates
- pull request template
- CODEOWNERS
- Dependabot configuration where applicable

See `REPOSITORY-ADOPTION-CHECKLIST.md` for rollout guidance.
