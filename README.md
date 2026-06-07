# Participant Template: Beginner Chaos Engineering Exercise

Use this template to plan, observe, and record a beginner-friendly chaos engineering exercise.

This template helps participants capture the steady state, define the hypothesis, prepare the safety checks, document the fault, record observations, collect evidence, and summarize lessons learned from one controlled failure scenario.

## Purpose

This document is a participant-facing template for a simple chaos engineering activity. It is designed to help learners and teams record what normal looks like, what failure is being tested, what they expect to happen, what actually happened, and what should improve after the exercise.

## When to Use This Template

Use this template when:

- running a beginner chaos engineering exercise in a workshop, lab, or staging environment
- guiding QA participants through a resilience-focused observation activity
- documenting one controlled failure scenario and its outcome
- capturing evidence and follow-up actions after the test

## Before You Start

Confirm all of the following before continuing:

- [ ] This exercise is running in a sandbox, lab, or staging environment.
- [ ] Only one failure scenario will be tested.
- [ ] A rollback or undo step is ready.
- [ ] Someone is available to monitor the system.
- [ ] Logs, metrics, screenshots, or observations can be captured.
- [ ] The test is short and time-boxed.

---

## Step 1: Describe the System and Steady State

Before injecting any fault, record what normal behavior looks like. This gives you a baseline for comparison during and after the experiment.

### System Details

- System name:
- Team or owner:
- Environment:
- Main user journey to observe:
- Date and time:
- Participants:

### Steady-State Record

| What to check | Normal behavior |
|---|---|
| Page or service response |  |
| Error rate |  |
| User-visible behavior |  |
| Dependency health |  |
| Logs or dashboard signals |  |
| Expected recovery signal |  |

### Prompt Questions

- What should a normal user see?
- What counts as acceptable behavior?
- What would count as failure for this exercise?
- What tells you the system is healthy before the fault starts?

---

## Step 2: Define the Hypothesis

A useful hypothesis is specific, testable, and measurable. It should state what failure will be introduced and what the system should do if it handles the failure well.

### Choose One Beginner-Safe Fault

Pick one:

- [ ] Kill one process or container.
- [ ] Add network latency.
- [ ] Pause one dependency briefly.
- [ ] Simulate a timeout.
- [ ] Other:

### Hypothesis Sentence Template

Use this sentence:

> If **[failure]** happens to **[component]**, then **[expected behavior]** should happen, and **[important metric or user impact]** should stay within acceptable limits.

### Hypothesis Record

- Failure:
- Target component:
- Expected user experience:
- Expected system behavior:
- Expected recovery behavior:
- Success limit or threshold:

### Example

> If the backend API becomes 2 seconds slower, the application should still show a loading or retry message, avoid a raw error page, and recover once the delay is removed.

---

## Step 3: Prepare the Experiment Safely

Keep the scope small. Beginners should run one short experiment, change one thing only, and keep an undo step ready before the test starts.

### Safety Plan

| Item | Your notes |
|---|---|
| Experiment name |  |
| Fault to inject |  |
| Tool or method |  |
| Start time |  |
| Planned duration |  |
| Rollback step |  |
| Stop condition |  |
| Observer(s) |  |
| Communication method |  |

### Final Safety Check

- [ ] I know exactly what failure I am injecting.
- [ ] I know how to stop it.
- [ ] I know what user flow to test.
- [ ] I know what evidence to capture.
- [ ] I know what result would make this test stop early.

---

## Step 4: Run and Observe

Execute the experiment and observe both the system behavior and the user experience. Focus on whether the system degrades clearly, fails safely, and recovers in an understandable way.

### Experiment Log

| Time | What you did | What you expected | What actually happened |
|---|---|---|---|
|  | Started experiment |  |  |
|  | Injected fault |  |  |
|  | Checked user journey |  |  |
|  | Observed logs/metrics |  |  |
|  | Triggered rollback or stop |  |  |
|  | Confirmed recovery |  |  |

### Observation Prompts

- Did the application stay available?
- Did the user see a clear loading, retry, fallback, or error message?
- Did the system fail gracefully or show a raw failure?
- Were logs, alerts, or visible symptoms captured?
- How long did the system take to recover?
- Did recovery happen automatically or manually?

### Evidence Checklist

- [ ] Screenshot before fault
- [ ] Screenshot during fault
- [ ] Screenshot after recovery
- [ ] Timestamp of fault injection
- [ ] Timestamp of rollback or recovery
- [ ] Error message or UI behavior captured
- [ ] Logs or dashboard notes captured
- [ ] Any unexpected behavior recorded

---

## Step 5: Summarize the Outcome

The goal is not just to inject a fault. The goal is to learn whether the system failed safely, recovered clearly, and gave enough evidence for the team to improve it.

### Results Summary

| Question | Your answer |
|---|---|
| Was the hypothesis confirmed? |  |
| What did the user experience? |  |
| What degraded well? |  |
| What failed badly? |  |
| Were alerts or logs useful? |  |
| Did recovery happen automatically or manually? |  |
| Would this pass as acceptable resilience? |  |

### Lessons Learned

- One thing that worked well:
- One thing that needs improvement:
- One risk discovered during the test:
- One follow-up action for the team:

---

## Post-Experiment Reflection

Copy this into your notes, issue tracker, or README after the activity.

```md
## Post-Experiment Reflection

**Experiment:**
**Environment:**
**Date/Time:**
**Participants:**

### Steady state
- Normal user behavior:
- Normal system signals:
- Success criteria:

### Hypothesis
- Fault injected:
- Expected behavior:
- Expected recovery:

### What happened
- User-visible impact:
- System behavior:
- Logs or alerts seen:
- Recovery time:

### Outcome
- Hypothesis confirmed / partially confirmed / not confirmed:
- Main lesson learned:
- Follow-up fix or improvement:
```

## Quick Reminders

- Start small.
- Test one thing at a time.
- Do not use production as the first environment.
- Always prepare rollback, monitoring, and evidence collection before injecting the fault.
- Focus on learning, not only on pass or fail.
