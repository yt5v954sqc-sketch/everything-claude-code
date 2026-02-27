# /chronicle - Session Narrative Log

Write a human-readable narrative of the current session — what was worked on, decisions made, problems solved, and outcomes reached.

## Usage

`/chronicle [save|print] [title]`

## What to Chronicle

Capture the session story:

1. **What was the goal?**
   - The user's original request or objective
   - Any clarifications or scope changes made during the session

2. **What was investigated?**
   - Files explored, commands run, errors encountered
   - Dead ends and why they were abandoned

3. **What decisions were made?**
   - Architectural or design choices
   - Trade-offs considered and why one approach was chosen
   - Assumptions made

4. **What was built or changed?**
   - Files created or modified (with brief descriptions)
   - Tools or libraries used
   - Key code patterns introduced

5. **What is the outcome?**
   - Current state: working, partially done, blocked
   - Any remaining open questions or next steps

## Output Format

```markdown
# Chronicle: [title or auto-generated summary]

**Date:** [YYYY-MM-DD]
**Session:** [session ID if available, else omit]

## Goal
[One or two sentences describing what the session set out to accomplish]

## Investigation
[Narrative of what was explored and discovered — written as prose, not bullet dumps]

## Decisions
[Key choices made and the reasoning behind them]

## Changes Made
[What was actually built or modified, with file paths]

## Outcome
[Current state and any open items]
```

## Process

### `print` (default)
Output the chronicle directly to the terminal. Use this for quick review.

### `save`
1. Generate the chronicle
2. Determine filename: `~/.claude/chronicles/YYYY-MM-DD-[slug].md`
   - Slug is a 3-5 word kebab-case summary of the session goal
3. Create the directory if it doesn't exist:
   ```bash
   mkdir -p ~/.claude/chronicles
   ```
4. Write the file and confirm path to user

## Arguments

`$ARGUMENTS`:
- (none) — print chronicle to terminal
- `print` — print chronicle to terminal
- `save` — save chronicle to `~/.claude/chronicles/`
- `save [title]` — save with a custom title overriding the auto-generated slug

## Notes

- Write in plain prose — avoid bullet-point dumps of raw tool calls
- Focus on decisions and reasoning, not a play-by-play of every command
- Be honest about dead ends; they are part of the story
- Keep it concise: aim for something a teammate could read in 2 minutes to understand what happened
- Unlike `/learn`, a chronicle captures the full session narrative rather than a single extractable pattern
