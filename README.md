# Student finance survey, Utrecht 2024

A 14-item mixed-methods survey I designed, fielded and analysed on my own, published in full: the instrument, the data, the counts, and the three defects that were built into the questionnaire before anyone answered it.

Applied Research 2.4, Master Data-Driven Design, Hogeschool Utrecht. Fielded October 2024. Eleven records, ten usable.

**Read the write-up:** [sepidakz.github.io/student-finance-survey-2024](https://sepidakz.github.io/student-finance-survey-2024/)
**Reproduce the numbers:** [`analysis.ipynb`](analysis.ipynb)

---

## The question

How do the money-literacy limitations students face shape the way they actually handle their finances, and what does that mean for anyone designing a tool for them?

The disagreement in the team was about distribution, not depth. Nobody could say whether students avoid budgeting tools because the tools are hard, because they have no time, or because they see no reason to bother. Those three explanations imply three different products. A handful of interviews would have given richer stories and no way to weigh them, so I ran a survey.

In hindsight the reasoning was right and the execution did not match it. A question about distribution cannot be answered by ten people. I should have either widened the sample or accepted this as a qualitative study and designed it as one.

## Method

Self-administered online survey, roughly three minutes, ordered from stable facts through behaviour to preference, with the two open items last so fatigue would cost the least important data.

| Item | Content | Type |
|---|---|---|
| 1 | Age | Open numeric |
| 2 | Student category | Single select |
| 3 | Source of income | Single select, **defective** |
| 4 | Self-rated understanding of financial concepts | 5-point, **unanchored** |
| 5 | Ever taken a personal finance course | Yes / No |
| 6 | Most challenging concepts | Ranking, **defective** |
| 7 | Currently tracks expenses | Single select |
| 8 | Methods used to manage finances | Multi select |
| 9 | Frequency of saving | 5-point frequency |
| 10 | Most helpful tool features | Multi select |
| 11 | Motivation to use or avoid a tool | Multi select |
| 12 | Frequency of financial stress | 5-point frequency |
| 13 | What would make a tool more engaging | Multi select |
| 14 | One thing you would change | Open text |

**Cleaning.** Respondent 11 opened the form and left after 18 seconds having answered only demographics. Partial records are excluded rather than imputed. Every figure below sits on a base of 10.

**Sample.** Five international students, two EU/EEA, two Dutch, one other. Ages 21 to 39, median 29.5. Recruited in one evening from one network, self-selecting.

## Findings

Counts, not percentages. At a base of 10, a percentage implies a precision the data does not have: 55 percent of this sample is five and a half people.

**Why students use or avoid a financial tool** (item 11, multi select)

| | n |
|---|---|
| It's hard to use | 6 |
| I don't have the time | 3 |
| It helps me reach my financial goals | 2 |
| I use other methods | 1 |
| I don't see the need | 1 |
| It helps me stay organised | 1 |

Usability outranked both time and indifference. "I don't see the need", the explanation the team had been treating as likeliest, was chosen once.

**What would make a tool more engaging** (item 13, multi select)

| | n |
|---|---|
| Personalised financial advice | 7 |
| Visualisations of spending and savings goals | 7 |
| Simple, user-friendly design | 6 |
| Integration with banking apps | 6 |
| Gamification (reward system) | 0 |

Gamification was offered and selected by nobody. It is the finding I trust most, because a zero needs no sample size to be interesting, and it ran against where the concept work was heading.

**Current behaviour.** Six of ten use a banking app, three keep spreadsheets by hand, two track nothing, one uses a purpose-built finance app. Nine of ten have never taken any course on managing money. Seven report financial stress often or always, on a single self-report item with no validated scale.

## What I got wrong

Three defects were built into the questionnaire before a single response came in. I found them while cleaning the data, which is later than I should have. Each is demonstrated in the notebook rather than just described.

**Item 3 offered "Other" twice.** The income question shipped with two separate options both meaning other, one of them free text. Answers scattered into buckets that cannot be recombined, and one respondent typed a compound answer, "part-time job and student loan", that a single-select item had no way to hold. Income is not usable as a variable in this dataset. A second reader on the draft would have caught it in a minute.

**Item 6 was built as a ranking, so it measures nothing.** I wanted to know which financial concepts students find hardest. The item forced every respondent to order all six, so every concept registers for all ten and the counts come out flat. The output looks like data and carries no signal. The right instrument was a pick-your-top-three, or MaxDiff for a genuine preference ordering.

**The 5-point knowledge scale had no anchors.** Item 4 asked for a self-rating from very poor to excellent with no point defined. Four said poor and four said fair, but there is no reason to believe two respondents meant the same thing by fair, and no way to check. A behavioural proxy, such as whether they can name last month's grocery spend, would have been harder to write and worth far more.

**And the sample was whatever answered that day.** One evening, one network, self-selecting, median age 29.5. That is old for a student sample and tells you the recruitment reached my own cohort rather than students in general.

## How I would design it now

- Define the constructs before writing items. Financial confidence, tracking behaviour and tool friction are three different things, and this questionnaire moved between them without saying so.
- Anchor every scale or replace it with a behavioural measure. Frequency items with concrete referents beat unanchored adjectives.
- Use MaxDiff for feature preference. Items 10 and 13 both ask about desirability, and multi select lets a respondent want everything.
- Set the sample against the analysis, not the deadline. Comparing international, EU/EEA and Dutch students needs quotas and a base near 100.
- Pilot with five people and a second reader. Both structural defects above would have surfaced in half an hour.
- Decide the analysis before fielding. Naming the tests in advance is what stops a survey from quietly becoming a thematic exercise after the fact, which is what happened here.

The study did its job as exploratory input: it moved the team off "students don't see the need" and onto usability, and it ruled out reward mechanics early. It was never strong enough to settle the question it was written to answer.

## Repository

```
responses.csv     11 records, anonymous at collection, 14 items plus timestamps
analysis.ipynb    reproduces every figure above, including the defect demonstrations
index.html        the write-up, served via GitHub Pages
```

Requires `pandas`. No response is attributable to an individual: the form collected no names or email addresses.

---

Sepideh Zamani. [sepidehzamani.com](https://sepidehzamani.com)
