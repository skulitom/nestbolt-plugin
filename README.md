# Nestbolt for Claude Code

Free sheet nesting for laser cutters, CNC routers, plasma, waterjet, fabric and leather. Give Claude your SVG or DXF
part outlines and a sheet size, and Nestbolt fits the parts onto fixed sheets so the job uses the least material.
It checks every layout and saves per-sheet SVG or DXF cut files.

This repository holds the Claude Code plugin: the `nestbolt` MCP server entry, a skill that tells Claude when and how
to use it, and eval cases in `evals/`. Nestbolt itself, its source and its benchmarks are at
[skulitom/Nestbolt](https://github.com/skulitom/Nestbolt).

## Install

1. Download the Nestbolt v0.1.0 release archive for your system (Windows x64, Linux x64 or macOS Apple silicon) from
   [the release page](https://github.com/skulitom/Nestbolt/releases/tag/v0.1.0). Check it against `SHA256SUMS`, then
   put `nestbolt-mcp` on your PATH.
2. In a terminal:

   ```
   claude plugin install nestbolt --marketplace skulitom/nestbolt-plugin
   ```

   Or inside Claude Code: `/plugin marketplace add skulitom/nestbolt-plugin`, then `/plugin install nestbolt@nestbolt`.

3. Restart Claude Code in the folder that holds your part files.

If you already added the `nestbolt` marketplace from skulitom/Nestbolt, keep using it, or remove it first
(`claude plugin marketplace remove nestbolt`): both marketplaces are named `nestbolt` and hold the same plugin.

Then ask in your own words, for example: "Nest everything in shop/order-118.dxf on a 1000 x 500 mm plate, 5 mm from the
edge and 4 mm between parts, and save the DXF for the plate."

## What it runs, writes and sends

- **What it runs:** the plugin starts `nestbolt-mcp` from your PATH, with no arguments.
- **What it reads and writes:** only files inside the folder you opened in Claude Code (or `NESTBOLT_WORKSPACE`, if
  set). It reads the part and layout files you name, and writes its results as new files, by default under a
  `nestbolt/` folder there: part libraries, and per-run folders with the job, layout, report and an SVG and DXF per
  sheet. It never overwrites a file.
- **What it sends:** nothing. Nestbolt has no account, no API key, no telemetry and no network access; nothing is
  uploaded.
- **What it may fetch:** the plugin itself downloads nothing. If `nestbolt-mcp` isn't installed, the skill tells
  Claude to offer, with your agreement, to download the v0.1.0 archive for your system from
  [Nestbolt's GitHub release](https://github.com/skulitom/Nestbolt/releases/tag/v0.1.0), check it against that
  release's `SHA256SUMS`, and put `nestbolt-mcp` in a folder on your PATH.
- **Eval cases:** `evals/` holds test cases with mocked replies for `claude plugin eval`. Claude Code never loads them
  when you use the plugin.

If the `nestbolt` tools don't appear, `nestbolt-mcp` isn't on your PATH. Install it as in step 1 and restart
Claude Code.

## Licence and privacy

MIT. See [LICENSE](LICENSE). [Privacy](PRIVACY.md): it runs on your computer and sends nothing. Report a security problem privately, as [SECURITY.md](SECURITY.md) says.
