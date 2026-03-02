# Prompt: Build the SCALE 23x Notes Repository

## Context

This prompt is self-contained. Execute it top to bottom with no prior context needed.

You are setting up a conference notes repository for **SCALE 23x** (Southern California Linux Expo),
held in Pasadena, CA. The repo is at the current working directory.

### Current Repo State

The repo contains only one file of substance:

```
prompting/urls.txt
```

That file contains:
- The SCALE 23x schedule URL: `https://www.socallinuxexpo.org/scale/23x/schedule`
- Talk URLs organized by day (Thursday through Sunday), representing the talks the owner
  plans to attend or is interested in.

> **Important**: The URLs in `urls.txt` are **not** listed in chronological order within
> each day. You must fetch each talk page to get the actual start times, then sort
> everything chronologically when building `schedule.md`.

### Target Repo State

You are building this repo to match the quality and structure of the
`snowflake-summit-2025` notes repo (described in detail below). The end result
should be a polished, fully scaffolded conference notes repository with:

1. `README.md` — conference overview and important links
2. `schedule.md` — a schedule table with emoji, date, time, type, location, an
   "attended" checkbox column, and links to each talk's notes file
3. `sessions/` — one markdown file per talk, pre-filled with metadata and the
   conference description, ready for live note-taking

---

## Step 1: Fetch Talk Metadata

For each URL in `prompting/urls.txt`, **fetch the page** and extract:

- **Title** — the full talk title
- **Speaker(s)** — presenter name(s) and affiliation(s)
- **Date** — the specific calendar date (e.g., Friday, March 6, 2026)
- **Time** — start and end time
- **Room / Location** — the room name or track
- **Description** — the full abstract/description text from the conference site

Also fetch the main schedule page (`https://www.socallinuxexpo.org/scale/23x/schedule`)
to confirm exact dates, times, and room names for each talk. Use this page to fill in
any fields not available on individual talk pages, and to confirm the real calendar dates
for each conference day (Thursday–Sunday).

Once you have all the metadata, **sort all talks chronologically** — by date first,
then by start time within each day — before creating any files.

> **Do not hallucinate metadata.** If a field is not available on the page,
> use the placeholder `TBD` rather than guessing.

---

## Step 2: Create `sessions/` Files

Create one markdown file per talk inside `sessions/`. File names must be plain ASCII
lowercase with hyphens — **no emojis, no special characters, no uppercase** anywhere
in any file name.

Use this naming convention:

```
sessions/<short-slug>.md
```

Where `<short-slug>` is a concise slug derived from the talk title (3–5 meaningful words,
not the full verbose URL slug). Examples:
- "Confidential Vector Search Knowledgebase with Homomorphic Encryption" → `confidential-vector-search.md`
- "All Your Keyboards Are Belong Us" → `all-your-keyboards.md`
- "Tectonix Bedrock: Shopify's Monorepo" → `shopify-monorepo.md`
- "OpenSearch: Your Friendly Neighborhood Vector Database" → `opensearch-vector-database.md`

### Session File Template

Each session file must follow this exact template:

```markdown
# [Full Talk Title]

[URL to the talk on the SCALE 23x website]

- **Date**: [e.g., Friday, March 7, 2026]
- **Time**: [e.g., 10:00 - 11:00]
- **Location**: [Room name / track name]
- **Speaker(s)**: [Name, Affiliation]

> [Full abstract/description copied verbatim from the conference page]

## Overview

[One-sentence summary of what this talk is about — write this yourself based on the description]

## Key Points

-
-
-

## Technical Details

-
-

## Resources Mentioned

-

## Personal Thoughts

-
```

**Notes on the template:**
- The description block uses a Markdown blockquote (`>`) — copy it verbatim from the
  conference site.
- `Overview` should be a single sentence you write based on the description (not copied).
- Leave bullet lists with a single `-` placeholder so the file is ready for live notes.
- Add a `## Lab Exercises` section (with a fenced code block placeholder) only for
  talks that appear to be hands-on labs or workshops.
- Add a `## Demo Notes` section only for talks that appear to have a demo component.
- Omit sections that clearly don't apply (e.g., no `## Technical Details` for a
  community/social talk).

---

## Step 3: Create `schedule.md`

Create a schedule table at the root of the repo. **Rows must be sorted chronologically**
— by date first, then by start time within each day.

### Schedule Table Format

```markdown
# SCALE 23x Schedule

My schedule for SCALE 23x — Southern California Linux Expo.

## Schedule Overview

| Date       | Time          | Title                                    | Type    | Location  | Attended | Notes                      |
|------------|---------------|------------------------------------------|---------|-----------|----------|----------------------------|
| YYYY-MM-DD | HH:MM - HH:MM | [emoji] Full Talk Title                  | Session | Room Name | [ ]      | [Notes](sessions/slug.md) |
```

### Column Definitions

- **Date**: ISO format `YYYY-MM-DD`
- **Time**: 24h format, e.g. `10:00 - 11:00`
- **Title**: One emoji prefix + full title. See the emoji selection philosophy below.
  **Emojis appear only in this table column — never in file names or folder names.**
- **Type**: One of `Session`, `Workshop`, `Keynote`, `Activity`, `Meal`
- **Location**: Room name (abbreviated if long)
- **Attended**: Markdown checkbox `[ ]` — the owner updates this to `[x]` after
  attending in person, or `[~]` if they missed it but plan to watch the recording later
- **Notes**: `[Notes](sessions/slug.md)` link for talks with notes files; `-` for
  meals or activities without a notes file

### Emoji Selection Philosophy

Choose one emoji per talk. The emoji should be **specific and creative** — tied directly
to the content, title, or playful wordplay of that particular talk. Avoid generic
category buckets. Think about what single image best represents the spirit of this specific
talk.

Examples of the right approach:
- "OpenCLAW: Non-Engineer's Survival Guide" → 🦞 (the name is literally a claw)
- "Try to Teach a Goldfish to Bark" → 🐠 (it's about a goldfish)
- "All Your Keyboards Are Belong Us" → ⌨️ (keyboards)
- "Confidential Vector Search with Homomorphic Encryption" → 🔒 (encryption/secrecy)
- "Engineering at Ludicrous Speed" → 🚀 (speed, also a Spaceballs reference)
- "Migrating to OpenTelemetry" → 🔭 (telemetry = looking at things from afar)

Each talk should get its own distinct emoji. Only mundane logistical items like meals
or generic networking receptions are candidates for a shared emoji (e.g., 🍽️ for lunch).

At the bottom of `schedule.md`, add an **Event Types** section:

```markdown
## Event Types

- **Keynote**: Main stage presentations
- **Session**: 45–60 minute technical presentations
- **Workshop**: Hands-on or instructor-led sessions
- **Activity**: Networking events and social activities
- **Meal**: Scheduled meal times
```

And a **Watching Later** note:

```markdown
## Watching Later

Talks marked `[~]` in the Attended column were not attended in person but may be
available on YouTube. SCALE typically posts recordings at:
https://www.youtube.com/socallinuxexpo
```

---

## Step 4: Create `README.md`

```markdown
# SCALE 23x Notes

This repository contains my notes and schedule for SCALE 23x —
Southern California Linux Expo, Pasadena, CA.

## Important Links

- [Schedule](https://www.socallinuxexpo.org/scale/23x/schedule)
- [SCALE Website](https://www.socallinuxexpo.org/scale/23x)
- [YouTube (past recordings)](https://www.youtube.com/socallinuxexpo)

## Contents

- [Schedule](schedule.md) — Personal schedule with attended status
- [Sessions](sessions/) — Notes from individual talks

Repository structure generated from [this prompt](prompting/build_repo.md)
and [this URL list](prompting/urls.txt).
```

---

## Full List of Files to Create

After completing all steps, the repo should contain (slugs are suggestions based on
expected titles — use your best judgment based on actual fetched content):

```
README.md
schedule.md
sessions/
  confidential-vector-search.md       ← Thursday
  flink-sql-workshop.md               ← Friday (workshop)
  all-your-keyboards.md               ← Friday
  shopify-monorepo.md                 ← Friday
  small-language-model-tokenizers.md  ← Friday
  python-observability.md             ← Saturday
  ai-reshaping-infra.md               ← Saturday
  migrating-opentelemetry.md          ← Saturday
  openclaw-non-engineers.md           ← Saturday
  security-psychology-misinformation.md ← Saturday
  automotive-flutter-riscv.md         ← Saturday
  opensearch-search-observability.md  ← Saturday
  try-teach-goldfish-bark.md          ← Sunday
  opensearch-vector-database.md       ← Sunday
prompting/
  urls.txt                            ← already exists, do not modify
  build_repo.md                       ← this file, do not modify
```

> Sessions are listed here by day for readability; the actual `schedule.md` rows
> must be sorted by date + start time (the URL list order is not chronological).

---

## Style & Quality Notes

- **Chronological order is required**: Sort all rows in `schedule.md` by date then
  start time. The source URLs in `urls.txt` are not in order — use fetched times.
- **Be faithful to the source**: Copy descriptions verbatim as blockquotes; do not
  paraphrase them.
- **No invented data**: If the schedule page doesn't list a time or room for a talk,
  use `TBD`.
- **No emojis in file names or folder names** — emojis belong only in the Title
  column of `schedule.md`.
- **Consistent template**: All session files must follow the same template structure.
- **The Attended column starts empty** (`[ ]` for all rows) — the owner fills these
  in during and after the conference.
- Do not create any files other than those listed above.
- Do not modify `prompting/urls.txt` or `prompting/build_repo.md`.
