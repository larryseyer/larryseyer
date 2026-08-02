# Deferred work

Opened 2026-08-01 during the licensing-truthfulness pass across the GitHub profile and
larryseyer.com. Everything below was found during that pass and deliberately NOT done, with
the reason recorded.

## IDA's AGPL header sweep — owned by IDA's own session, do not start from here

`/Users/larryseyer/IDA` still has 38 tracked source files whose per-file headers read
"Licensed under the GNU Affero General Public License v3.0 (see LICENSE)", plus stale AGPL
claims in `website/README.md`, `website/src/docs/whitepaper.md`, `docs/IDA_Whitepaper_V11.md`,
`docs/LICENSE-THIRD-PARTY.md`, and `docs/SAMPLE-LICENSE.md`.

That sweep is formally assigned to IDA's own session in
`/Users/larryseyer/AudioDevelopment/OTTO/CROSS_PROJECT_INBOX.md:117` (item 3), together with a
copyright-header sweep of 1,082 files. Doing it from this session would collide with work
already in flight there. Only `IDA/README.md` was corrected here, because the profile defers
to it.

## CC-BY-SA vs CC BY in the published JTF News transcript

`larryseyer.github.io/pages/projects/ChatGPT_Website_Credibility_Rating_Chat.html` says
`CC-BY-SA` at line 1422 and `CC BY` at line 1429 — seven lines apart. The same text is
duplicated in two publicly-served files, `transcript_source.txt` and
`ChatGPT_Website_Credibility_Rating_Chat.txt`.

Left alone deliberately: it is a verbatim published transcript, and silently rewriting a
transcript is a worse truthfulness problem than the inconsistency. `jtfnews/LICENSE.md`
confirms CC BY-SA 4.0 is the correct one. If this is ever corrected, it should be an editor's
note rather than an edit to the quoted text, and all three files must change together.

## Repos with no LICENSE file at all

These default to all-rights-reserved, which may or may not be the intent:

- `larryseyer.github.io` (public — the website itself)
- `IDA2QLPro`
- `OTTO-Interface-Development`
- `raspyramid`
- `AutoSampler`
- `AKAI-APC-40-Mkii-for-Realearn`

## Credentials in the profile repo

`.claude/settings.local.json:37-38` hardcodes `IA_ACCESS_KEY` and `IA_SECRET_KEY` in
plaintext. The file is untracked but was not covered by `.gitignore`, so a `git add -A` would
have committed live credentials. The gitignore has been fixed; the keys should still be
rotated.
