# Lens Handoff Protocol

## Goal

Define how Career Pilot explicitly calls an external lens skill and integrates the result back into the main planning flow.

## Controller Rule

- `Career Pilot` is always the controller
- The external lens skill is always an expert input provider
- The external lens skill does not own the final recommendation

## Outbound Brief

When Career Pilot calls a lens skill, it should send a short structured brief containing:

```yaml
lens_brief:
  controller: "career-pilot"
  lens_skill: ""
  question_type: ""      # decision | transition | growth | mixed
  core_question: ""
  user_profile:
    stage: ""
    location: ""
    education_or_role: ""
    years_of_experience: ""
  priorities: []
  constraints: []
  fears: []
  requested_focus:
    - ""
    - ""
```

## Expected Return Format

The lens skill should return a structured lens report, not a final action plan:

```yaml
lens_report:
  lens_name: ""
  top_judgment: ""
  why_this_lens_thinks_so: []
  recommended_direction: []
  warnings: []
  assumptions: []
  confidence: ""         # low | medium | high
```

## Career Pilot Integration Rules

After receiving a lens report, Career Pilot must:

1. Compare the lens judgment with the user's real constraints
2. Check whether the lens is answering the right problem
3. Decide whether to fully adopt, partially adopt, or reject the lens recommendation
4. Explain that decision explicitly in the final answer

For domain-specific career questions, the required sequence is:

1. Career Pilot performs current-state assessment
2. Career Pilot explicitly invokes the domain lens skill
3. The lens skill returns a structured lens report
4. Career Pilot integrates that report into the final recommendation

Career Pilot should not skip step 2 and go directly from current-state assessment to final integration.

## Mandatory User-Facing Disclosure

Before calling a lens skill, Career Pilot should explicitly tell the user:

- which lens skill is being called
- why that lens was chosen
- that the final answer will still be integrated by Career Pilot

## Anti-Patterns

- Do not silently apply a lens without telling the user
- Do not let the lens skill replace Career Pilot's controller role
- Do not forward the lens skill's output as the final answer without integration
- Do not ignore conflicts between lens advice and user constraints
