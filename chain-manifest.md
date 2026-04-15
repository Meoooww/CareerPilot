# Chain Manifest

## Current Chain

- Status: draft
- Last reviewed: 2026-04-15
- Default mode: runtime

## Runtime Chain

1. Build user profile
2. Route to decision / transition / growth
3. Select general career lens
4. Select domain lens if needed
5. Output structured recommendation

## Maintenance Chain

1. Read current chain state
2. Check update policy
3. Compare external skills / repos
4. Use `bggg-skill-taotie` when synthesis is needed
5. Decide whether to adopt changes
6. Write evolution log

## Integration Protocol

- External lens invocation follows `lens-handoff.md`
- Career Pilot remains the controller
- Lens skills provide structured reports, not final recommendations

## External Skill Dependencies

| Skill | Role | Source | Ref | Last checked | Required |
|------|------|--------|-----|--------------|----------|
| `bggg-skill-taotie` | Maintenance-mode evolver | local skill | local | 2026-04-15 | maintenance only |
| `zhangxuefeng-perspective` | Default China-mainland career lens | local skill | local | 2026-04-15 | runtime conditional |
| `karpathy-perspective` | AI / LLM domain lens | local skill | local | 2026-04-15 | runtime conditional |

## Candidate Lenses

- Zhang Xuefeng: default general career lens for China-mainland users
- Karpathy: AI / LLM / agent engineering domain lens
- Additional lenses: to be added after maintenance reviews
