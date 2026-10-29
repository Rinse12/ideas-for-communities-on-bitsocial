# Rotating Mod

> Every day a random active member becomes the moderator.

**Kind:** governance
**Effort:** S
**Needs:** nothing (mintpass optional)

## How it works

1. At midnight a bot picks a random member from everyone who posted or commented in the last week.
2. It gives them the moderator role through `community edit` and takes it from yesterday's mod.
3. It posts "Today's mod is …", and everything they remove is listed in a public mod log thread.

## The unique part

Moderation as jury duty. Nobody owns the community's culture, and every member eventually sees it from the other side.

Limits that keep it from going wrong:

- the daily mod can remove and approve, but not ban or change settings
- each morning the new mod gets a "review yesterday's removals" thread and can restore anything
- mintpass on eligibility, so nobody farms a hundred accounts to get picked more often

## Builds on

- Bitsocial CLI / RPC for role changes
- mintpass challenge (optional)

## Open questions

- Opt-out for people who don't want the job.
- Weighted lottery by activity, or flat?
