# Interview Runner Business Case

## The Issue
We often need to interview candidates for a particular role but often candidates
are not interviewed by the same interviewer, they are not asked the same questions,
and whether someone is a `Novice`, `Journeyman` or `Master` is subjective to the
experience of the interviewer.
This makes comparing different candidates subjective on who interviewed them and the 
questions they were asked. When only a small number of candidates are required for 
a role the impact of this subjectivity is limited. However, we often need to provide 
a team of staff all with the same skill set. The more roles need filling the less likely
it is that all candidates are interviewed by the same interviewer and the less control 
there is over the quality of the selected applicants.

Additionally, we are often interviewing for similar roles, or roles requiring the same
or similar competencies. Interviewers often find themselves asking the same questions
of multiple candidates over multiple roles. Each time a new job specification is 
identified, effort is required to identify `good` questions to pose to the candidate
which are relevant to the candidates experience and the job specification in question.

Experienced interviewers have a stock of `good` questions and are skilled at directing 
an interview towards questions which expose the candidates ability in respect of the 
competency in question. However, this resource of `good` questions exists only in the
experienced interviewers head and thus is difficult to leverage by other interviewers.

## Issue Scope
This issue applies to any organisation which interviews candidates for a role.
I.e. nearly all organisations experience this issue when interviewing candidates.

## Proposed Solution
Implement a system to define interview questions, with a curated mark scheme linked to
one or more pre-defined competencies. Competencies are a hierarchical, e.g.
* Team Leading / Time management
* Team Leading / Planning
* Software Engineering / AWS / DynamoDB
* Software Engineering / AWS / SQS

Questions can be relevant to any node on any competency hierarchy and potential questions 
to ask for a competency are any questions for that competency or any lower point on the
hierarchy.

The system defines a job specification as a set of competencies and the candidates 
required level for the competency and guides the interviewer to `good` questions based 
on the candidates previous responses (competencies in which they have expressed some 
experience) and the meta data of the recorded questions.

The system presents the curated mark scheme to assist the interviewer in fairly ascribing
candidates response level to the question.

As interviewers pose questions, metadata about the quality and frequency of the question
are recorded to further assist interviewers to find `good` questions.

At the end of the interview, a report is prepared with a 3x3 heat map for each of 
competencies required by the specification with a `thumbs up` if the candidate achieved
the required level for the competency. These reports gives a fair comparison of multiple 
candidates for the same role regardless of who they were interviewed by and what questions
they were asked.

Such a system makes large recruitment drives more efficient with a more consistent outcome
and assists ad-hoc recruitment where a job specification may not exist or interviewing a 
candidate against the competencies identified through their C.V.

## Solution Benefits
* Consistent measurement of a candidates ability against known competencies
* Increased interview quality independent of experience of the interviewer
* Reduced toil identifying suitable interview questions
* The ability to query how a candidate responded to other interviews

## Proposed Solution Scope
The solution could be implemented as private service where the above benefits are only 
realised by the organisation hosting the service.

The solution could be implemented as a SaaS solution where customers are charged for each 
interview given or each question asked.

## Costs

### Development Costs
The will be upfront cost to develop the service. The scale of these costs needs closer
investigation.
Some development cost must be bourne upfront (at risk) to prove the concept [(PoC)](../poc/POC.md) 
Some development cost must be bourne upfront (at risk) to achieve a Minimum Viable Product
[(MVP)](../mvp/MVP.md).
The completion of the MVP realises some (not all) of the solution benefits above.
The MVP will not be SaaS since benefit can be realised without offering a SaaS solution.

With the MVP complete, additional features can be added to further realise the above
Solution Benefits and/or to offer the service as SaaS. The cost of implementing a SaaS
solution needs closer investigation.

### Operational Costs
The solution should be able to be implemented using AWS serverless technology meaning 
the only fixed cost is the data storage overhead, (pennies per month) and the variable 
costs (compute costs) which increase with increased service usage.

### Maintenance Costs
The service is a product used by us (and potentially paying clients via SaaS) and would 
need to be maintained. This will require a product owner and an SRE team (both of these
roles are  likely to be part time). The maintenance cost is minimised through good SRE
practices such as `Observability`, `SLOs` and `Error Budget Burn Rate Alerts`

## Business Benefits
We interview a lot of candidates for a lot of roles. Realising the above benefits will
have an immediate impact on our ability to consistently find and compare candidates for
roles.

Offering the proposed solution as SaaS creates a new revenue stream which should cover
its own costs and have a positive impact on our bottom line.

## Next Steps
The next step is to complete the [PoC](../poc/POC.md) and assess whether the proposed 
solution is capable of delivering some of the above benefits.

If the assessment of the PoC is that the solution is viable and that suitable benefits
could be realised by the [MVP](../mvp/MVP.md) we should then invest in completing the
MVP.

When the MVP is achieved we should start using `Interview Runner` to manage some of 
our own interviewing load, resolve and bugs and add additional features as required.

## Scaling Up
With the MVP operational and delivering benefit, we can reach out to our full time 
employees (based on their recorded competencies in people fluent) and ask that they 
define some questions and mark schemes in their competency areas.

Once we are using `Interview Runner` to realise benefits for our interviewing needs, 
have a suite of good questions for our competency areas, and the service is reliable
and stable we can wrap `Interview Runner` in a SaaS layer and market it as a paid
service to other recruiters and organisations.

## Monitoring Success
There are several break points in developing this service and realising benefits.
These are:
* Proof of Concept
* Minimum Viable Product
* Mature Product
* Saas Product

Each of these breakpoints should have a continuation check to impassionately decide
whether to proceed past the break point. These continuation checks should be formally
defined in this documentation for the break point in question.

A summary of the likely continuation checks are:
### PoC Continuation
* Does the PoC demonstrate that some of the above solution benefits are achievable?
* Does the PoC suggest that the other solution benefits are achievable?
* Does the PoC suggest that sufficient benefit is realisable to continue develop the MVP?

### MVP Continuation
* Does the MVP deliver benefits?
* Does the benefit of the MVP exceed the cost of maintaining the MVP?
* Are there additional benefits which could be realised by further developing the MVP?

### Mature Product Continuation
* Are the benefits of the mature product applicable to other organisations?
* Is there a demand for `Interview Runner` as a SaaS solution?
* Does the demand for a SaaS solution exceed its operational and maintenance cost?

### SaaS Product Continuation
* Are there additional features which may drive more organisations to use`Interview Runner`?
* Does `Interview Runner` generate sufficient revenue to be separated into its own business?