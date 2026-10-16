# Contributing to Mosca

Thank you for helping build Mosca, an open-source end-to-end (E2E) test automation tool. This guide sets the rules for proposing and merging changes. Mosca is pre-alpha, so the process will evolve. If something here is wrong or unclear, open an issue or send a fix.

## Ground rules

1. **Be respectful.** Assume good intent, give specific and kind feedback, and stay on topic. Maintainers may edit or remove comments and block accounts that harass or discriminate against others.
2. **Discuss before you build.** Open an issue and agree on the approach before you start anything larger than a typo or a small documentation fix.
3. **Keep changes small.** Submit one logical change per pull request.
4. **Submit original work.** Contribute only work that you wrote or have the right to license under the MIT License. Never copy code, documentation, screenshots, file formats, or other assets from Tricentis Tosca or any other proprietary product.
5. **Protect secrets.** Never commit credentials, tokens, private keys, internal URLs, or personal data.
6. **Report vulnerabilities privately.** Follow [SECURITY.md](SECURITY.md). Never use public issues or pull requests for security problems.
7. **Stay truthful.** Document what exists today and label planned work as planned.

## Ways to contribute

- Report a bug or request a feature in [GitHub Issues](https://github.com/ram-ai-wq/mosca/issues).
- Ask a question by opening an issue.
- Improve the documentation: fix errors, clarify steps, and add verified examples.
- Review open pull requests and share constructive feedback.
- Write code or tests for an issue that a maintainer has accepted.

### Reporting a bug

Search the [existing issues](https://github.com/ram-ai-wq/mosca/issues) first, then include:

- What you did, what you expected, and what happened instead.
- The Mosca version or commit, your operating system, and any relevant tool versions.
- The smallest steps or test that reproduce the problem.
- Logs or screenshots with every secret and piece of personal data removed.

### Requesting a feature

Describe the problem you want to solve, your proposed solution, and the alternatives you considered.

## Development setup

Mosca has no source code, build, or test tooling yet, so there is nothing to compile or run. This section will list prerequisites and commands once the implementation language and toolchain are chosen. Until then you need only [Git](https://git-scm.com/) and a text editor. Optional AI tooling is covered in [AI-assisted development](#ai-assisted-development).

## Workflow

1. Fork the repository on GitHub and clone your fork.
2. Create a branch from the latest `main` named `<type>/<short-description>`, for example `docs/clarify-project-status`. Use the commit types below as prefixes.
3. Make your change, and update the affected documentation in the same branch.
4. Run every check that exists. There are none yet; this step will list them when they are added.
5. Commit with [Conventional Commits](#commit-messages).
6. Push your branch and open a pull request against `main`.
7. Answer review comments with follow-up commits, and keep your branch up to date with `main`.

## Commit messages

Follow [Conventional Commits 1.0.0](https://www.conventionalcommits.org/en/v1.0.0/):

```text
<type>(<scope>): <summary>

<body, optional>

<footer, optional>
```

- **Type:** one of `feat`, `fix`, `docs`, `refactor`, `perf`, `test`, `build`, `ci`, `chore`, `style`, or `revert`.
- **Scope:** optional; the area you changed, such as `readme` or `gitignore`.
- **Summary:** imperative mood ("add", not "added"), no trailing period, 50 characters when possible and 72 at most.
- **Body:** only when the reason is not obvious. Explain why, not what, and wrap lines at 72 characters.
- **Footer:** reference issues with `Closes #123`. Mark a breaking change with `!` after the type or scope and a `BREAKING CHANGE:` footer.

Examples:

```text
docs(readme): rewrite overview and project status
chore(gitignore): ignore local environment files
```

## Pull requests

- Target `main`. Give the pull request a title in the commit format, because maintainers may squash commits on merge.
- Describe what changed and why, link the issue with `Closes #123`, and say how you verified the change.
- Keep the diff focused: no unrelated refactors, formatting churn, or generated files.
- Open a draft pull request for work in progress.
- Explain any change to `.github/hooks/`, `.github/copilot-instructions.md`, `.vscode/`, or `.agents/`. These files run or steer tools on every contributor's machine, so maintainers review them with extra care.
- A maintainer must approve the pull request before it is merged. Review is best-effort, with no guaranteed response time.

Complete this checklist before you request a review:

- [ ] The change is focused and linked to an issue (trivial fixes excepted).
- [ ] Commits follow Conventional Commits.
- [ ] Tests are added or updated when behavior changes, once test tooling exists.
- [ ] Documentation is updated in the same pull request.
- [ ] Changes to `README.md` follow the [README rules](.github/instructions/readme.instructions.md).
- [ ] No secrets, internal URLs, personal data, or generated artifacts are included.
- [ ] I wrote this work or have the right to submit it under the MIT License.
- [ ] I described any significant AI assistance in the pull request.

## Documentation rules

- Write in English, in plain language and the present tense.
- Update documentation in the same pull request as the change that requires it.
- Every `README.md` follows the [README rules](.github/instructions/readme.instructions.md).
- Use relative links for files in this repository, tag every fenced code block with a language, and avoid emoji in headings and bullets.
- Save files as UTF-8 with one trailing newline and no trailing whitespace.

## AI-assisted development

AI coding assistants are optional. You can contribute without them, and you remain responsible for everything you submit, whoever or whatever wrote it. This repository ships configuration for three optional tools that make assistants more efficient.

| Tool | Purpose | Configuration in this repository |
|------|---------|----------------------------------|
| [CodeGraph](https://github.com/colbymchenry/codegraph) | Local code index that gives assistants semantic code search over MCP | [`.vscode/mcp.json`](.vscode/mcp.json). The `.codegraph/` index is generated locally and ignored by Git. |
| [RTK](https://github.com/rtk-ai/rtk) | Command-line proxy that shortens shell output before an assistant reads it | [`.github/copilot-instructions.md`](.github/copilot-instructions.md) and [`.github/hooks/rtk-rewrite.json`](.github/hooks/rtk-rewrite.json) |
| [Caveman](https://github.com/JuliusBrussee/caveman) | Skills that make assistants answer tersely: `caveman`, `caveman-commit`, `caveman-review`, `caveman-help` | [`.agents/skills/`](.agents/skills), pinned by [`skills-lock.json`](skills-lock.json) |

The configuration is committed, so each tool only needs to be installed on your machine. Restart your editor or assistant afterward so it loads the hooks and MCP servers. Third-party licenses are listed in [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).

### Install the tools

CodeGraph needs [Node.js](https://nodejs.org/):

```bash
npm install -g @colbymchenry/codegraph
codegraph install
```

`codegraph install` connects CodeGraph to the assistants on your machine. Then build the local index from the repository root:

```bash
codegraph init -y
```

RTK installs from a package manager:

```bash
winget install rtk-ai.rtk   # Windows
brew install rtk            # macOS and Linux
rtk gain                    # must print a savings dashboard
```

Another unrelated project named `rtk` exists on crates.io. If `rtk gain` fails, you installed the wrong package.

The Caveman skills are already in `.agents/skills/`. If that folder is missing, restore it from the lock file:

```bash
npx skills experimental_install
```

### Rules for AI assistants

- Read this file and the matching files in [`.github/instructions/`](.github/instructions) before you change anything.
- Make the smallest change that satisfies the request, and do not refactor unrelated code.
- Do not invent features, versions, commands, or benchmarks. If a fact is unknown, ask a maintainer or leave it out.
- Never commit secrets, `.env` files, keys, or the `.codegraph/` index.
- Write code, comments, documentation, and pull request text in normal prose. Use terse commit messages only when they still follow the [commit rules](#commit-messages).
- Run the available checks, and report what you could not verify.
- Do not push to `main` or merge pull requests unless a maintainer explicitly asks you to. Otherwise, open a pull request.

## Security

Report vulnerabilities privately by following [SECURITY.md](SECURITY.md). If you commit a secret by accident, revoke or rotate it immediately, because deleting it from Git history is not enough.

## License

By submitting a contribution, you agree to license it under the [MIT License](LICENSE), the same license as the project. You keep your copyright, and no contributor license agreement (CLA) or sign-off is required. Do not add third-party code or assets unless their license is compatible with MIT and you add an entry to [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).
