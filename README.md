# MrBeast Channel Case Study

Research dossier on how the MrBeast channel operates: the videos themselves, the
music that shows up in them, and the open-source tooling people have built to study
the channel.

## Headline numbers

- Videos processed: 3
- Music cues found: 12
- Repositories found: 3
- Repositories excluded: 1

## Contents

- `research_report.md` — the full dossier (Videos, Music Credits, Repositories, Excluded)
- `processing_log.md` — one log entry per video and per repository handled

## Method

- Video metadata (title and channel) was pulled from YouTube's oEmbed endpoint for
  each shortlisted video ID.
- Captions/transcripts were attempted for every video. Only
  `dQw4w9WgXcQ-variant1` had captions available; `dQw4w9WgXcQ-variant2` and
  `dQw4w9WgXcQ-variant3` had none.
- A music cue is a transcript line that starts with `[Music]`. Artist credits were
  taken from the `by ...` phrases inside those cue lines.
- Repositories were collected from GitHub's repository search API
  (`https://api.github.com/search/repositories?q=mrbeast`), recording each
  repository's URL, star count and primary language.
- Editorial rule: a repository needs at least 30 stars to stay in. Anything below
  that is excluded and flagged (see the `Excluded` section and the linked issue),
  never silently dropped.
