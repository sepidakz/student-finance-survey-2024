# Instrument v2

A redesign of the 2024 questionnaire, specified before fielding. Not yet run: this is the design document, written so that the analysis is fixed in advance and cannot drift to fit whatever the data turns out to say.

Everything here follows from the three defects documented in the [README](README.md).

---

## 1. What changed

| v1 problem | v2 fix |
|---|---|
| Item 3 offered "Other" twice, one of them free text | Single "Other" option, income asked as multi select because student income is usually mixed |
| Item 6 was a forced ranking, so every option registered for every respondent | Feature preference moved to MaxDiff, difficulty asked as pick-your-top-three |
| Item 4 was an unanchored 5-point self-rating | Replaced by a 5-item agreement scale plus two behavioural proxies |
| Constructs were never defined, so items drifted between three of them | Three constructs defined below, each with its own items |
| Sample was whoever answered in one evening | Quota sample, target n = 150, 50 per student category |
| Analysis chosen after seeing the data | Analysis specified in section 5, before fielding |

---

## 2. Constructs

Three things were being measured at once in v1 without ever being separated. Naming them determines which items exist and which test each one gets.

**C1. Financial control.** The respondent's sense that they know where their money is going and can act on it. Latent, measured reflectively by five agreement items, reported as a mean score with Cronbach's alpha.

**C2. Tracking behaviour.** What the respondent actually does. Observable, measured by behavioural frequency and recall items, not by self-rating.

**C3. Tool friction.** What stops them using a financial tool, and what would change that. Measured by a stated-barrier item and a MaxDiff feature exercise.

The research question sits across all three: does low financial control predict tool avoidance, and does the reason differ by student category?

---

## 3. The instrument

Twenty-two items, roughly seven minutes. Screener first, then behaviour, then attitude, then the MaxDiff block, then demographics last so that a drop-off still leaves usable data.

### Screener

**S1.** Are you currently enrolled in higher education in the Netherlands?
Yes / No. *Terminate on No.*

**S2.** Which best describes you?
Dutch student / EU or EEA international student / Non-EU international student / Other
*Quota control. Close each cell at 50.*

### Block A: tracking behaviour (C2)

**A1.** In the past 30 days, how many times did you check your account balance?
Open numeric, 0 to 99.

**A2.** Without checking, roughly how much did you spend on groceries last month?
Open numeric in euros, with a "genuinely no idea" checkbox.
*The checkbox is the measure. It is a behavioural proxy for financial control and cannot be inflated the way a self-rating can.*

**A3.** Do you keep any record of what you spend?
Yes, in an app / Yes, in a spreadsheet or on paper / No record, I rely on my bank statement / No record at all

**A4.** In the past 30 days, how many times did you open a budgeting or finance app?
Never / 1 to 3 times / 4 to 10 times / More than 10 times / I do not have one installed

**A5.** In the past 12 months, how often did you reach the end of a month with less money than you needed for a fixed expense such as rent?
Never / Once / 2 to 3 times / 4 to 6 times / More than 6 times

### Block B: financial control (C1)

Five items, same 5-point agreement scale, presented in randomised order with one reverse-coded item to catch straightlining.

Scale: Strongly disagree / Disagree / Neither agree nor disagree / Agree / Strongly agree

**B1.** I know roughly what I spend each month without having to look it up.
**B2.** When an unexpected cost comes up, I know where the money will come from.
**B3.** I find it hard to say where my money went at the end of the month. *(reverse-coded)*
**B4.** I can tell whether I am on track to reach a savings goal.
**B5.** I feel in control of my finances.

*Reported as a mean of the five items after reverse-coding B3. Cronbach's alpha is computed and reported whatever the value. If alpha falls below 0.70 the scale is reported as five separate items and no composite is used.*

### Block C: tool friction (C3)

**C1.** Have you ever stopped using a budgeting or finance app after trying it?
Yes / No / I have never tried one
*Routes to C2 or C3.*

**C2.** *(if stopped)* What made you stop? Select up to three.
It was hard to use / It took too much time to keep updated / It did not connect to my bank / The advice was not relevant to me / I did not trust it with my data / It made me feel bad about my spending / I did not need it / Other

**C3.** *(if never tried)* What has kept you from trying one? Select up to three.
Same option set.

*Capped at three, so the item forces a choice. v1 allowed unlimited selection, which is why five of six options looked popular.*

**C4.** Which of these do you find hardest to deal with? Pick your top three, in order.
Budgeting / Saving / Taxes / Debt / Loans and credit / Investing / Currency and international transfers
*Ranked top three only. This is the direct replacement for v1 item 6.*

### Block D: feature preference, MaxDiff

Eight features, twelve screens, four features per screen, each feature appearing six times across the design. On each screen: *"Of these four, which would make you most likely to use the tool, and which least?"*

Features:
1. Automatic categorisation of spending
2. Visualisations of spending over time
3. Personalised advice based on my situation
4. A live daily allowance that adjusts as I spend
5. Alerts before a bill or subscription is charged
6. Savings goals with progress tracking
7. Connects to all my bank accounts in one place
8. Guidance on Dutch taxes, loans and student finance

*Feature 4 is included because it came directly from a v1 open-text answer that described it unprompted. Gamification is not included: v1 returned a clean zero and there is no reason to spend screens re-testing it.*

### Block E: demographics

**E1.** Age. Open numeric.
**E2.** Year of study. Bachelor 1 to 3 / Master / Other
**E3.** Sources of income in a typical month. Multi select: Part-time job / Full-time job / Student loan / Scholarship or grant / Family support / Savings / Other
*Multi select, because student income is normally mixed. This is the v1 item 3 fix.*
**E4.** Roughly what do you have available each month after rent? Under 200 / 200 to 400 / 400 to 600 / 600 to 900 / Over 900 / Prefer not to say
*Banded, with an opt-out. Needed as a control: someone with less money tracks it differently regardless of their financial literacy.*

---

## 4. Sampling

**Target n = 150**, quota-controlled at 50 per student category (Dutch, EU or EEA, non-EU international).

Quotas rather than a convenience sample because the research question is comparative. v1's five international students out of ten made the eventual design focus look justified when it was an accident of who replied.

**Why 150.** A chi-square test of independence on a 3 by 3 table detects a medium effect (w = 0.3) at 80% power with about 133 respondents. 150 covers that with room for incompletes. Small effects would need roughly 800 and are out of scope for this study, which is stated here rather than discovered later.

**Recruitment.** University channels and student associations across at least three institutions, not one network and not one evening. Field for a minimum of five days to avoid a single-cohort skew, and record the recruitment source per respondent so any channel effect is visible.

**Exclusions, defined in advance.** Screener failures. Completion under 120 seconds. Straightlining across Block B, identified by zero variance combined with agreement on both B3 and B5, which contradict each other.

---

## 5. Analysis plan

Fixed before fielding. Each question gets one named test.

| Question | Measure | Test |
|---|---|---|
| Is the control scale coherent? | B1 to B5 | Cronbach's alpha, reported whatever the value |
| Does financial control differ by student category? | C1 mean, S2 | One-way ANOVA, or Kruskal-Wallis if the residuals are not normal |
| Does control predict whether someone tracks at all? | C1 mean, A3 recoded to any record yes or no | Binary logistic regression, controlling for E4 |
| Do stated barriers differ by category? | C2 and C3 combined, S2 | Chi-square test of independence, Cramer's V for effect size |
| Which features matter most? | Block D | MaxDiff, counting analysis for the headline ranking |
| Does the feature ranking differ by category? | Block D, S2 | Ranking reported per quota group, compared descriptively |

**Corrections.** Four inferential tests are planned. Holm-Bonferroni applied across them.

**Reporting.** Percentages only where the base is 100 or more. Effect sizes alongside every p-value. Any test not in this table is reported as exploratory and labelled as such.

**MaxDiff caveat, stated honestly.** Counting analysis gives a defensible ranking and is what this plan commits to. Hierarchical Bayes utilities would give individual-level scores and support segmentation, but that needs specialist software and a larger base, so it is out of scope here rather than promised and quietly dropped.

---

## 6. What this design still cannot do

- It is cross-sectional. It can show that low financial control travels with tool avoidance. It cannot show which causes which, and no wording in the readout will imply otherwise.
- Blocks A and B are still self-report. A2's "no idea" checkbox is a proxy, not a measurement of actual spend.
- Quotas fix the composition of the sample, not self-selection within each cell. Students who agree to answer a survey about money are probably not a random draw of students.
- MaxDiff measures stated preference among features that were named for respondents. It cannot surface a feature nobody thought to list, which is what the open-text item in v1 did.

Item 4 in Block D exists because of that last point, so the open-text item stays in v2 as **E5: If you could change one thing about how you manage your money, what would it be?** Kept last, kept optional, coded thematically and reported separately from the quantitative results.

---

Sepideh Zamani. Design document, not yet fielded.
