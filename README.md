# Nestbolt for Claude Code

Free sheet nesting for laser cutters, CNC routers, plasma, waterjet, fabric and leather. Give Claude your SVG or DXF
part outlines and a sheet size, and Nestbolt fits the parts onto fixed sheets so the job uses the least material.
It checks every layout and saves per-sheet SVG or DXF cut files.

This repository holds only the Claude Code plugin: the `nestbolt` MCP server entry and a skill that tells Claude when
and how to use it. Nestbolt itself, its source and its benchmarks are at
[skulitom/Nestbolt](https://github.com/skulitom/Nestbolt).

## Install

1. Download the Nestbolt v0.1.0 release archive for your system (Windows x64, Linux x64 or macOS Apple silicon) from
   [the release page](https://github.com/skulitom/Nestbolt/releases/tag/v0.1.0). Check it against `SHA256SUMS`, then
   put `nestbolt-mcp` on your PATH.
2. In Claude Code:

   ```
   claude plugin install nestbolt --marketplace skulitom/nestbolt-plugin
   ```

3. Restart Claude Code in the folder that holds your part files.

Then ask in your own words, for example: "Nest everything in shop/order-118.dxf on a 1000 x 500 mm plate, 5 mm from the
edge and 4 mm between parts, and save the DXF for the plate."

## What it runs and sends

- **What it runs:** the plugin starts `nestbolt-mcp` from your PATH, with no arguments. It runs in the folder you
  opened in Claude Code, and it reads and writes only the part and layout files you name there.
- **What it sends:** nothing. Nestbolt has no account, no API key, no telemetry and no network access; nothing is
  uploaded.
- **What it doesn't include:** the plugin downloads and installs nothing itself.

If the `nestbolt` tools don't appear, `nestbolt-mcp` isn't on your PATH. Install it as in step 1 and restart
Claude Code.

## Licence

MIT. See [LICENSE](LICENSE).
