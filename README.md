# Interview Runner Documentation

## What Is Interview Runner
Interview Runner is a tool to assist interviewers to consistently interview 
candidates against a fixed specification. The specification identifies a set of 
competencies with a target ability `Apprentice`, `Jouneyman` or `Master`.
When an interview is run against a specification the candidate is asked to give 
examples of when they have demonstrated aspects of the competency in question.
As the candidate expresses exposure to detailed aspects of the competency the
tool proposes suitable questions to drill into the details of the candidates 
ability for the competency.

Interview Runner allows questions to be defined, with a curated mark scheme.
The mark scheme details `Novice`, `Skilled`, `Expert` response levels. 
Questions are tagged with an applicable ability `Apprentice`, `Jouneyman` or 
`Master`.

During an interview the questions posed to the candidate are recorded with notes 
on the candidates response including the candidates response level. The 
combination of the questions target ability, `Apprentice`, `Jouneyman` or `Master`
and the candidates response level, `Novice`, `Skilled`, `Expert` gives a heat
map reflecting how well the candidate presents their ability discharging the
competency in question.

Multiple questions can be posed for the same competency which can all be overlayed
on the same heat map.

|  | Novice | Skilled | Expert |
|--|--------|---------|--------|
|Apprentice|        |         | X      |
|Journeyman|        |         | X      |
|Master|        | X       |        |

The heat map above shows 3 candidate responses to questions concerning 1 
competency.

At the end of the interview a report is prepared with a heat map for each
competency in the specification. Comparing this report for each candidate
interviewed against the spec gives a fair comparison of all the candidates
regardless of who interviewed them and what questions were posed.

### Contents
* [Business Case](business_case/BUSINESS_CASE.md)
* [Proof Of Concept](poc/POC.md)
* [User Personas](analysis/user_personas/ALL_PERSONAS.md)
* [Use Cases](analysis/use_cases/ALL_USE_CASES.md)

