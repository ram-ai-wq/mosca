---
applyTo: "**/README.md"
---

# README rules

These rules apply to the root `README.md` and every nested `README.md`. Contributors and AI assistants must follow them. For the general workflow, see [CONTRIBUTING.md](../../CONTRIBUTING.md).

## Principles

1. **Truthful.** Describe only what exists today. Label unbuilt work as *Planned*. Never present a roadmap item as a working feature.
2. **Scannable.** The first screen must answer: what is it, what is its status, how do I start or contribute.
3. **Verifiable.** Every command, path, link, and version must be correct when merged. Run a command before documenting it.
4. **Single source of truth.** Link to the detailed document instead of copying its content.
5. **Safe.** No secrets, real credentials, internal URLs, or personal data.

## Required structure (root README)

Keep these sections in this order. Delete a section that has nothing real to say; never leave placeholders.

1. **Title and tagline:** one `#` heading with the project name, then a one-sentence description.
2. **Badges:** license and project status, plus others (CI, release) only once they exist and are accurate. Five at most.
3. **Overview:** what the project is and the problem it solves, in three short paragraphs at most.
4. **Project status:** maturity level, what works, what does not, and a stability warning while pre-1.0.
5. **Features:** list what is available now separately from what is planned.
6. **Getting started:** prerequisites, installation, and a minimal working example. If there is no release, say so.
7. **Contributing:** one short paragraph linking to [CONTRIBUTING.md](../../CONTRIBUTING.md), which owns the workflow and development setup. Do not duplicate them here.
8. **Security:** one short paragraph linking to [SECURITY.md](../../SECURITY.md); vulnerabilities are reported privately.
9. **License:** the license name (MIT) and a link to [LICENSE](../../LICENSE). While third-party material is bundled, also link [THIRD_PARTY_NOTICES.md](../../THIRD_PARTY_NOTICES.md).

Add a table of contents only when the README exceeds about 150 lines. Move long guides to `docs/` and link them.

## Writing style

- Write English in the present tense and active voice. Prefer short sentences and plain words.
- Use sentence case for headings, one `#` heading per file, and no skipped heading levels.
- Keep one paragraph per line (no hard wrapping). Use `-` for bullets.
- Tag every fenced code block with a language (`bash`, `powershell`, `json`, `text`).
- Write link text that describes the target, never "click here". Use relative links for files in this repository.
- Give every image meaningful alt text. Do not use emoji as bullets or in headings.
- Use tables only for reference data or comparisons.
- State facts, not marketing. Back any claim of speed, scale, or superiority with evidence or remove it.
- Name third-party products for identification only, and keep the non-affiliation notice for Tricentis Tosca.

## Commands and examples

- Show the exact command, the platform it targets, and the expected result when it is not obvious.
- Use obvious placeholders such as `<your-token>`. Never paste a real token, password, or key.
- Do not tell readers to pipe a remote script into a shell unless the README links to the script source and the project controls it.
- Pin or state versions when behavior depends on them.

## Maintenance

- Update the README in the same pull request that changes behavior, commands, requirements, or project status.
- Re-run Getting started on a clean checkout before each release.
- Remove stale text immediately. Avoid relative time words ("recently", "soon"); use an absolute date (`YYYY-MM-DD`) when a date is needed.
- Keep file hygiene: UTF-8, one trailing newline, no trailing whitespace.

## Pull request checklist

- [ ] Sections follow the required structure and order.
- [ ] Every statement is true today; planned work is labeled as planned.
- [ ] Commands ran successfully on a clean checkout.
- [ ] Links resolve and badges show accurate values.
- [ ] No secrets, internal URLs, or personal data.
- [ ] Spelling and grammar checked.

## Rules for AI assistants

- Read this file before editing any `README.md`.
- Do not invent features, benchmarks, version numbers, or commands. If a fact is unknown, ask the maintainer or leave it out.
- Make the smallest change that satisfies the request and preserve accurate existing content.
- Do not alter the license text or the non-affiliation notice.
- After editing, walk through the checklist and report anything you could not verify.
