# UK AML Enforcement Dataset

**A year of UK anti-money-laundering enforcement, with the control failure recorded against each case
rather than the headline penalty.**

Compiled by [Thomas Geater](https://thetypologyfiles.com). First published 4 September 2026.

## Why this exists

Public discussion of AML enforcement is dominated by a small number of very large fines. Those cases
are well covered. The several hundred small penalties issued in the same period are not covered
anywhere I could find, and they describe a completely different failure.

This dataset puts both in one place, and records **what actually went wrong** in each case rather
than only what it cost.

## The finding

**The distribution is bimodal and the middle is close to empty.**

At one end, a handful of institutions fined tens of millions for controls that existed, were
documented, were staffed, and did not work. At the other, several hundred small firms fined a few
thousand pounds each for having no controls, because they were never inside the supervisory system
at all.

**In the six months to September 2025, HMRC issued 369 penalties totalling £1,881,237. 332 of them —
just under 90% — were for trading without AML registration.** Not for weak risk assessment. Not for
inadequate monitoring. For operating a regulated business without being registered for supervision.

A second pattern sits underneath the first. Nationwide's findings were ineffective customer risk
assessment and ineffective CDD refresh. Two of the Bank of Lithuania's four 2026 measures turn on
customer identification and customer risk assessment. Two of the Gambling Commission's four recurring
findings concern customer interaction and affordability. **Enforcement is concentrating at the front
of the process — on whether the firm understood who it was dealing with — rather than on whether it
watched the money afterwards.**

## Files

| File | Contents |
|---|---|
| `data/enforcement_actions.csv` | Individual enforcement actions, one row per case, with the primary control failure and the stage of the customer lifecycle it sits at |
| `data/hmrc_penalties_2025h1.csv` | HMRC penalties for the six months to September 2025, broken down by supervised sector |
| `data/hmrc_headline_figures.csv` | HMRC headline figures for the same period |
| `data/gambling_commission_activity.csv` | Gambling Commission enforcement and compliance activity volumes |

## Method

1. **Sources are the supervisors' own publications only.** FCA Final Notices and press releases, the
   HMRC enforcement publication of 9 February 2026, Gambling Commission enforcement action reports,
   and Bank of Lithuania enforcement notices.
2. **The control failure is taken from the regulator's own stated finding**, not inferred from the
   penalty size or the sector.
3. **`failure_stage` is the one interpretive field.** It maps the stated finding onto the stage of
   the customer lifecycle where it sits, so that onboarding failures can be separated from monitoring
   failures. Where a published summary does not itemise the failure, the field says so rather than
   guessing.
4. **Unknown values are left blank.** Where a source did not state a publication date or a
   breakdown, nothing is inserted.

## Limitations, stated plainly

- **This is one compiler's reading of published notices, not an official register.** Anyone relying
  on it for a regulatory purpose should go to the primary sources, which are cited above.
- **It is not exhaustive.** It covers the actions that were published and that I found. Absence from
  this dataset is not evidence that no action was taken.
- **Currencies are not converted.** GBP and EUR appear as published.
- **The Lithuanian comparison is deliberately small** — four measures, included because they point
  the same way as the UK findings, not because four cases establish a trend.
- **`failure_stage` is a judgement.** It is the only field in the dataset that is.

## Licence

Data: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Use it, change it, build on it.
Attribution to Thomas Geater / The Typology Files.

## Citing

> Geater, T. (2026). *UK AML Enforcement Dataset*. https://thetypologyfiles.com

## Contributions

Corrections are welcome, particularly missing actions and any case where you think the recorded
control failure does not match the regulator's own wording. Open an issue with the source.
