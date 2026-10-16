# Security policy

## Supported versions

Mosca is pre-alpha and has no releases yet. Security fixes target the latest commit on the `main` branch only. This section will list supported release lines once releases exist.

## Reporting a vulnerability

**Do not open a public issue, pull request, or discussion for a security problem.**

Report it privately through GitHub:

1. Open the [Security tab](https://github.com/ram-ai-wq/mosca/security) of this repository.
2. Select **Report a vulnerability**, or go straight to the [private report form](https://github.com/ram-ai-wq/mosca/security/advisories/new).
3. Describe the problem using the checklist below.

If the form is not available, open a public issue titled "Security contact request" that contains **no technical details** about the problem. A maintainer will reply there and arrange a private channel.

### What to include

- A description of the vulnerability and its impact.
- The affected file, component, or commit.
- Steps or a minimal proof of concept that reproduce it.
- A suggested fix, if you have one.
- How you want to be credited, if at all.

Remove real credentials and personal data from anything you attach.

## What to expect

Mosca is maintained on a best-effort basis, so there is no guaranteed response time. The maintainers aim to:

1. Acknowledge your report within 7 days.
2. Confirm or dismiss the issue, and keep you informed while they work on a fix.
3. Publish a [GitHub security advisory](https://docs.github.com/en/code-security/security-advisories) with a fix, crediting you unless you prefer to stay anonymous.

Please keep the details private until a fix is released, or for 90 days after your report, whichever comes first. If a fix needs more time, the maintainers will agree on a new date with you.

## Scope

In scope:

- Code and configuration in this repository, including the files under `.github/`, `.vscode/`, and `.agents/`.

Out of scope:

- Vulnerabilities in the tools this repository only configures: [CodeGraph](https://github.com/colbymchenry/codegraph), [RTK](https://github.com/rtk-ai/rtk), and [Caveman](https://github.com/JuliusBrussee/caveman). Report those to their maintainers.
- Vulnerabilities in GitHub or in other third-party services.

## Leaked secrets

If you find a credential in this repository or its history, report it privately as described above and treat it as compromised. If you committed a secret yourself, revoke or rotate it first. Removing it from Git history is not enough.

## Safe use of AI tooling

Agent skills, hooks, and MCP servers run with the permissions of your assistant and can execute commands on your machine. This repository ships such configuration in `.github/hooks/`, `.vscode/mcp.json`, and `.agents/skills/`. Review any change to these files as carefully as code, and report suspicious changes privately.
