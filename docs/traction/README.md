# Two-week onboarding and outreach test

Baseline: October 4, 2026 (America/New_York). Review: October 18, 2026.

Question: does a concrete, editable example and a focused invitation lead to
independent trials, useful feedback and forks?

## Baseline

[Machine-readable snapshot](baseline-2026-10-04.json): **1 fork, 3 stars and 352
release-asset download events** across the existing releases. The snapshot includes
per-asset IDs and counters for later comparison. Download events include galleries,
manifests and checksums; they are not unique users and may include CI or maintainer
downloads. Visitor and clone data are unavailable through the connected tools and
are recorded as `null`, not zero.

## Changes under test

- Add a prominent route from the README to [Fork and run](../FORK_AND_RUN.md).
- Provide an editable fixture with two expected outcomes.
- Fix the literal newline escapes near the README's browser-demo link.
- Prepare the [tester invitation](../LAUNCH_KIT.md#small-tester-invitation-draft).

The invitation is a draft. No external posts or invitations have been sent as part
of this setup. Distribution requires choosing a relevant community or recipients.
Record the actual posting date and URL below when the invitation is shared.

## Measures

The initial target is **five independent developers trying the example**. This is
a goal, not a forecast. Count confirmed trials only when a person voluntarily
reports a result, issue or contribution. A download alone does not confirm a trial.

At review, record net changes in forks and stars, per-asset download deltas, new
reproducible reports, and external pull requests. Record removed assets or forks
separately rather than treating every count decrease as no activity. For new release
assets, report their counts separately from the baseline cohort.

Commit counts and contribution-graph activity are excluded. Without visitor data,
do not calculate a visitor-to-fork conversion rate. Do not label every new fork as
independent adoption without evidence that its owner tried or adapted the project.

## Outreach log

| Date | Channel and post URL | Message variant | Confirmed responses |
| --- | --- | --- | --- |
| Pending | No external posting yet | Tester invitation | Not measured |

## Decision at review

- No outreach exposure: report that the outreach test has not yet started.
- Visits but no trials, if visitor data becomes available: review the example and setup friction.
- Trials but little feedback: make the request for a counterexample more specific.
- Useful feedback or adaptations: fix reported friction and repeat with one additional failure scenario.

This is an observational before/after check. Small numbers, untracked exposure and
concurrent changes prevent a causal claim about what produced any growth. It does
not test the effect of an artificially inflated fork count.
