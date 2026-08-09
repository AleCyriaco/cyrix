# cyrix

Lazy senior dev mode as a single Claude desktop (Cowork) skill — forces the
simplest, shortest solution that actually works: YAGNI, stdlib before custom
code, native platform features before dependencies, one line before fifty.

Clean port of [ponytail](https://github.com/DietrichGebert/ponytail) by Dietrich
Gebert (MIT), renamed and repackaged as one installable skill for the Claude
desktop app.

## Install (Claude desktop / Cowork)

Download `cyrix.skill` and click **Save skill**. Or add the `cyrix/` folder as a
skill under Settings → Capabilities.

## Use

Type `/cyrix` (or say "modo preguiçoso" / "be lazy"). Levels:
`/cyrix lite|full|ultra` (default `full`). Turn off: "modo normal".

## Update

After editing `cyrix/SKILL.md`, rebuild the bundle and re-save it in the app
(Settings → Capabilities) — the installed copy does not follow the repo:

```bash
python3 -c "import zipfile; z=zipfile.ZipFile('cyrix.skill','w',zipfile.ZIP_DEFLATED); z.write('cyrix/SKILL.md'); z.write('LICENSE','cyrix/LICENSE'); z.close()"
```

Install it once, in one place. A second copy under `~/.claude/skills/cyrix`
costs its whole `description` in every session, used or not.

## Contents

- `cyrix/SKILL.md` — the skill
- `cyrix.skill` — prebuilt one-click bundle
- `LICENSE` — MIT

The frontmatter `description` is deliberately terse: it loads in every session,
while the body only loads when the skill fires. Keep new trigger phrases out of
it unless they earn their tokens.

## Credit

Ruleset by Dietrich Gebert ([ponytail](https://github.com/DietrichGebert/ponytail), MIT).
This is a renamed port for the Claude desktop app.
Ruleset synced with ponytail's 7-rung ladder and comprehension-first guard (Aug 2026).
