# Update Policy

## Goal

Keep Career Pilot current without making every user session unstable or over-researched.

## Default Rule

- Runtime mode does not update the chain by default.
- Maintenance mode is the only place where chain evolution happens.

## Trigger Conditions

Trigger maintenance mode when at least one condition is met:

- User explicitly asks to update the planning chain
- User explicitly asks for new external approaches
- More than 30 days have passed since the last maintenance run
- A key dependency skill appears outdated, unavailable, or significantly changed

## Adoption Criteria

Adopt a new skill or pattern only if it clearly improves at least one of:

- routing accuracy
- lens selection clarity
- career recommendation quality
- maintenance traceability

## Rejection Criteria

Reject a candidate if it mainly adds:

- resume / interview / application execution behavior
- unstable or noisy routing logic
- hidden worldview changes without better explanations
- excessive maintenance complexity

## Maintenance Output

Every maintenance run should end with:

- keep current chain
- adopt partial changes
- adopt major chain change

The decision must be written into `evolution-log.md`.
