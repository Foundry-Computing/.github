# REPOSITORY-ADOPTION-CHECKLIST

Use this checklist when bringing a Foundry repository into alignment with the GitHub foundation.

## Repository identity

- [ ] Purpose is documented
- [ ] Repository description is set
- [ ] Topic tags reflect actual product or function
- [ ] Repository classification is documented
- [ ] Lifecycle status is documented
- [ ] Owner and maintainers are documented

## Documentation baseline

- [ ] README exists and explains purpose, setup, and status
- [ ] LICENSE decision is documented
- [ ] CONTRIBUTING guidance exists
- [ ] SECURITY policy exists
- [ ] CODE_OF_CONDUCT applies or is inherited
- [ ] SUPPORT guidance exists
- [ ] CODEOWNERS exists

## Delivery workflow

- [ ] Default branch is `main` or deviation is explicitly documented
- [ ] Changes flow through pull requests
- [ ] Required reviewers are identified
- [ ] Branch protection is configured conservatively
- [ ] Force pushes are blocked on protected branches
- [ ] Branch deletion is blocked on protected branches
- [ ] Merge strategy is documented; squash merge preferred unless justified otherwise
- [ ] Automatic deletion of merged feature branches is enabled where appropriate

## Validation and security

- [ ] Build instructions are documented
- [ ] Test instructions are documented
- [ ] Required status checks are configured when tests exist
- [ ] Dependabot configuration is present where dependency updates are relevant
- [ ] Dependabot alerts and security updates are reviewed
- [ ] Secret scanning availability is checked
- [ ] Code scanning applicability is checked
- [ ] Security sensitivity is documented
- [ ] Backup or recovery considerations are documented

## AI governance

- [ ] Allowed AI access level is documented
- [ ] AI accounts do not administer the repository
- [ ] AI accounts cannot bypass review requirements
- [ ] AI accounts cannot approve their own changes
- [ ] AI-generated changes require attributable commits or PR authorship
- [ ] Tests performed by AI are recorded in PRs

## Recommended rollout order

1. `.github`
2. actively developed core/platform repositories
3. user-facing application and integration repositories
4. infrastructure and automation repositories
5. experimental repositories
6. archival review for dormant repositories
