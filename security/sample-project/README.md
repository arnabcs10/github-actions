# Security Aspects

## Concerns
1. Script Injection
- A value, set outside a Workflow, is used in a Workflow
- Example: Issue title used in a Workflow shell command
- Workflow / command behavior could be changed
- Resolution: Use verified actions only or develop them on own or use env vars when user values are taken into script


2. Malicious Third Party Actions
- Actions can perform any logic, including potentially malicious logic
- Example: A third-party Action that reads and exports your secrets
- Only use trusted Actions and inspect code of unknown / untrusted authors



3. Permission Issues
- Consider avoiding overly permissive permissions
- Example: Only allow checking out code (“read-only”)
- By default, a job has all permissions.
- GitHub Actions supports finegrained permissions control.

We can set job level permissions like this:
```
jobs:
  assign-label:
    permissions:
      issues: write
```
By default every job gets a token assigned and its valid until the job is active - secrets.GITHUB_TOKEN
This token has all the permissions, when we set permissions it gets applied on this token.
We can change the default permissions of this token at the Actions Settings

# Important Links
- https://docs.github.com/en/actions/concepts/security/openid-connect
- https://docs.github.com/en/actions/how-tos/secure-your-work/security-harden-deployments/oidc-in-google-cloud-platform
- General overview & important concepts: https://docs.github.com/en/actions/security-guides/security-hardening-for-github-actions

- More on Secrets: https://docs.github.com/en/actions/security-guides/encrypted-secrets

- Using GITHUB_TOKEN: https://docs.github.com/en/actions/security-guides/automatic-token-authentication

- Advanced - Preventing Fork Pull Requests Attacks: https://securitylab.github.com/research/github-actions-preventing-pwn-requests/

- Security Hardening with OpenID Connect: https://docs.github.com/en/actions/deployment/security-hardening-your-deployments/about-security-hardening-with-openid-connect

