---
name: modpack-creator
description: Makes and publishes Modpack packs - turns a person's own workflow, scripts or prompts into a pack other people can run from Claude, or builds one from scratch; tests it in Modpack's sandbox and publishes it. Use when someone wants to share, package, sell or publish their setup or a tool on Modpack.
---

# Making Modpack packs

## Where

- **With a shell (Claude Code):** the modpack CLI, `npx @modpack.md/cli <command>`. Add `--json` to read its results.
  - `login` once (in the browser). `init` in an empty folder scaffolds a pack. `check` validates it offline, every issue at once.
  - `test` builds it and replays its example on Modpack; exit 0 means ready. `publish --visibility private|unlisted|public [--price 0.10]`. `status` lists the person's packs.
  - `logs` and `exec -- <command>` debug a draft in its build sandbox.
- **In chat (no shell):** the tools `get_share_guide`, `test_pack`, `get_report`, `publish_pack` and `my_packs`.

## Someone's own setup: the share guide comes first

- Before any file of the person's own setup leaves their computer, get the share guide (`get_share_guide`; `modpack init` prints it) and follow it there: clean the copy, ask at most 3 questions, check nothing private is left, compare results.
- Keep their private terms (names, clients, domains, …) in a file outside the pack folder.
  - CLI: `modpack check --private-terms FILE`, then `modpack test --private-terms FILE --share-report report.json`.
  - Chat: `test_pack` with `private_terms` (fingerprints made with the guide's key) and `share_report`.
  - Only fingerprints leave the computer, never the terms.

## The handle

- The first time, ask the person which public handle they want. It's in their pack links; suggest one from their name.
- Pass it once: `modpack test --handle <handle>`, or `test_pack`'s `handle`. The pack id is `<handle>/<pack>`.

## Test, fix, test again

- Each failed check in the report says what failed, where (file and line) and the fix. Apply the fixes and test again.
- Testing is charged to the person's creator balance (cents). Don't publish until the report says ready.

## Publishing

- Ask who should see it: only them (private), anyone with the link (unlisted), or everyone (public). A price per run is optional (0 to 5 USD).
- A pack's first share, the Creator Agreement (once) and wider visibility need the person's own confirmation on Modpack. Give them the link that `publish_pack` or `modpack publish` returns.
- New versions that ask for no new access need nothing more.

## Never

- Confirm, accept or approve anything for the person: publishing, the agreement, prices, payments. Those are theirs, on Modpack.
- Send files or data the person didn't choose, or their private terms themselves.
