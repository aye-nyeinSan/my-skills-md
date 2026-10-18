---
name: weekly-report
description: "Build the user's private weekly report from their GitHub commits and PRs, ClickUp tasks, Slack threads, and calendar: what they did, wins, what they learned (including AI tools), blockers, feedback, and next week's plan. Use when the user asks for their weekly report, weekly review, week summary, or 'what did I do this week'."
---

# Weekly report

Make a short, honest report of the user's week. The report is **for the user only**. It helps them see their progress, remember wins, and prepare for 1:1s with their manager and coffee chats with their PM.

## Rules

- **Read only.** Never post, send, comment, change tasks, or share the report. Show it to the user, and save it only if they ask.
- **Only the user's own work.** Filter every source to the user. Do not report on other people.
- **Facts first.** Every item must come from a source or from the user. Do not invent numbers, impact, or praise. If you guess, say so.
- **Keep private things private.** Do not copy secrets, tokens, customer personal data, or private DM text into the report. Summarize instead.

## 1. Set the week

Default: Monday of this week until today, in the user's time zone. If today is Monday, use last week (Monday to Sunday). If the user names a range, use it. Write the range at the top of the report.

## 2. Collect the facts

Use the tools that are connected. If a source is not connected or fails, skip it, and say so in "Sources" at the end. Do not stop.

| Source | What to collect |
|---|---|
| **GitHub** | PRs the user opened, merged, or reviewed in the range; commits they authored. Get PR title, repo, state, and link. Use the GitHub tools, `gh`, or `git log --author` in local repos. |
| **ClickUp** | Tasks assigned to the user that were closed or changed status in the range; tasks in progress; overdue tasks. Get name, status, and link. |
| **Slack** | Threads the user started or replied in, mentions of the user, and messages they sent about decisions, help given, or blockers. Use search with `from:me` and the date range. |
| **Calendar** | Meetings the user attended: 1:1s, planning, demos, interviews, coffee chats. Skip declined events and focus blocks. |

Then group the facts:

- Link items that are the same work (a ClickUp task, its PR, and the Slack thread about it). Report them as **one** item with all links.
- Drop noise: tiny fix-up commits, bot messages, and automatic updates.

## 3. Ask the user (short)

After collecting, ask at most three quick questions, only about things the sources cannot show:

1. "Anything big I missed?" (offline work, helping someone, a hard problem)
2. "What did you learn this week? Any AI tool, prompt, or trick worth sharing?"
3. "Any feedback you got or gave?"

If the user says "skip", build the report without these parts.

## 4. Write the report

Use this shape. Keep each line short. Put a link on each item when there is one.

```markdown
# Weekly report: <Mon DD> – <Mon DD>

## Highlights
<2–3 lines: the most important results of the week, in plain words>

## Done
- <result, not activity> — <links>

## In progress
- <item> — <status, what is left> — <links>

## Blockers and risks
- <what is blocked, by what, and the next step>

## What I learned
- <skill, tool, or lesson> — <one line on how it helped>
- **AI tools:** <tool / prompt / trick> — <real example, and any limits>

## Feedback
- Got: <feedback> → <what I will change>
- Gave: <feedback>

## Next week
- <top 3 goals, most important first>

## Talking points
- **1:1 with manager:** <1–2 points: progress, growth, help needed>
- **Coffee chat with PM:** <one feedback point and one AI-tool tip to share>

## Sources
<which sources were used, which were skipped, and why>
```

Writing tips:

- **Write results, not activity.** "Fixed login crash for Android users (PR #123)" is better than "Worked on login".
- **Use numbers only if a source gives them.**
- **Leave out empty sections.** Never fill them with made-up text.
- **Mark overdue items honestly** in "Blockers and risks".

## 5. After the report

Offer, in one line, to save it as a Markdown file (for example `weekly-reports/YYYY-MM-DD.md`) or to compare it with last week's report if one exists. Do nothing more unless the user asks.
