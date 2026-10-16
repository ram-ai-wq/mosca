# Third-party notices

Mosca is released under the [MIT License](LICENSE), which covers the original work in this repository. The third-party material listed here keeps its own license.

## Bundled material

### Caveman skills

- **What:** the `caveman`, `caveman-commit`, `caveman-help`, and `caveman-review` agent skills in [`.agents/skills/`](.agents/skills).
- **Source:** the `skills/` directory of [JuliusBrussee/caveman](https://github.com/JuliusBrussee/caveman), copied on 2026-10-16.
- **License:** Apache License 2.0. Copyright 2026 Julius Brussee. The full text is in [`LICENSES/Apache-2.0.txt`](LICENSES/Apache-2.0.txt).
- **Changes:** none. The files are unmodified copies, and [`skills-lock.json`](skills-lock.json) records the source path and content hash of each skill.

"Caveman" is a trademark of its owner. Mosca is an independent project and is not affiliated with or endorsed by the Caveman project.

## Tools that are not bundled

These optional developer tools are installed separately and are not part of this repository. Each has its own license; see its project page. This repository contains only configuration that the tools generated.

| Tool | Project | Generated files in this repository |
|------|---------|------------------------------------|
| RTK | [rtk-ai/rtk](https://github.com/rtk-ai/rtk) | The RTK block in `.github/copilot-instructions.md` and `.github/hooks/rtk-rewrite.json` |
| CodeGraph | [colbymchenry/codegraph](https://github.com/colbymchenry/codegraph) | `.vscode/mcp.json` |
