# AGENTS.md

This repo is a public Claude Code plugin: slash commands, a skill and reference files under
`.claude/`, which `install.sh` copies into a user's project. `CLAUDE.md` imports this file.

## Review guidelines

For Codex's GitHub reviews of this repo:

- Flag what would break or endanger something: incorrect behaviour, security problems or exposed
  secrets, data loss, broken migrations or deploys, and changed behaviour with no test. Mark these
  P0 or P1.
- In this repo, these are P1 as well:
  - Anything secret or private in this public repo: API keys, real call recordings or transcripts,
    customer or consultant names.
  - `install.sh` overwriting or deleting files in the user's project (it copies with `cp -n` and
    asks before touching an existing install).
  - A command that sends call data anywhere other than the services the README names (the Claude
    API, and Deepgram for transcription).
  - A new folder under `.claude/` that `install.sh` doesn't copy, or a command added or renamed
    without the README's command table updated.
- Do not flag wording, tone, formatting or style in prose (docs, plans, comments, commit messages),
  naming preferences, or refactors the change did not need.
- In docs and plans, flag only statements that are wrong against the code, or instructions that
  cannot be followed as written.
- One finding per root cause. If you are not confident a finding is real, leave it out.
