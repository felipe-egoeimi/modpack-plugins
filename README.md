# Modpack plugins for Claude

[Modpack](https://modpack.egoeimi.org) runs packs from Claude: tested tools for work Claude can't do alone, such as live
lead lists, AI visibility and SEO audits, site health checks and a whole site as Markdown. Results come back complete
in the chat, with files as links. Anyone can also make a pack from their own setup and publish it.

This repository is a plugin marketplace with one plugin, `modpack`:

- **The Modpack connector** (remote MCP, `https://mcp.modpack.egoeimi.org/mcp`). You sign in to Modpack once in your
  browser.
- **Two skills:** `modpack` (when and how to use packs) and `modpack-creator` (how to make, test and publish one; with a
  shell it uses the [`modpack` CLI](https://www.npmjs.com/package/@modpack.md/cli)).

## Install

**Claude Code**

```
/plugin marketplace add felipe-egoeimi/modpack-plugins
/plugin install modpack@modpack
```

Then run `/mcp` and sign in to Modpack.

**Claude (web, desktop and Cowork)**: Customize > Plugins > add from GitHub, `felipe-egoeimi/modpack-plugins`. Connect
Modpack from the plugin's Connectors tab.

Spending, new access, publishing and payments are always yours to approve, on Modpack.

## License

Apache-2.0. See [LICENSE](LICENSE).
