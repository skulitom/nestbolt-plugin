# Privacy

This plugin and the `nestbolt-mcp` program it starts run on your computer. Neither has an account, telemetry,
analytics or network access, and neither sends your files to the developer or to any other service.

- **What it reads:** the SVG, DXF, LightBurn project (`.lbrn2`, `.lbrn`) and layout files you ask Claude to nest,
  inside the folder you opened in Claude Code (or `NESTBOLT_WORKSPACE`). These are usually part outlines and sheet
  sizes, but they can carry whatever text or images you put in them; LightBurn projects keep their artwork.
- **What it stores:** part libraries, layouts, reports and per-sheet SVG and DXF files, written as new files in that
  folder (by default under `nestbolt/`), until you delete them.
- **What it sends:** nothing. What Claude itself sends to Anthropic while it works is covered by Anthropic's own
  privacy policy, not this one.
- **Optional installs:** if `nestbolt-mcp` is missing, the skill may offer, with your agreement, to download it from
  Nestbolt's GitHub release; that is a normal download from GitHub.

Questions: open an issue on [skulitom/nestbolt-plugin](https://github.com/skulitom/nestbolt-plugin/issues), or report a
security problem privately as [SECURITY.md](SECURITY.md) says.
