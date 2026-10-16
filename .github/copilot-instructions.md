# Project instructions

- Follow [CONTRIBUTING.md](../CONTRIBUTING.md) for the workflow, commit messages, and pull requests.
- Every `README.md` must follow [.github/instructions/readme.instructions.md](instructions/readme.instructions.md).
- Do not invent features, versions, or commands. Label planned work as planned.
- Never commit secrets or the `.codegraph/` index. Report vulnerabilities privately per [SECURITY.md](../SECURITY.md).

<!-- rtk-instructions v2 -->
# RTK — Token-Optimized CLI

**rtk** is a CLI proxy that filters and compresses command outputs, saving 60-90% tokens.

## Rule

Always prefix shell commands with `rtk`:

```bash
# Instead of:              Use:
git status                 rtk git status
git log -10                rtk git log -10
cargo test                 rtk cargo test
docker ps                  rtk docker ps
kubectl get pods           rtk kubectl get pods
```

## Meta commands (use directly)

```bash
rtk gain              # Token savings dashboard
rtk gain --history    # Per-command savings history
rtk discover          # Find missed rtk opportunities
rtk proxy <cmd>       # Run raw (no filtering) but track usage
```
<!-- /rtk-instructions -->
