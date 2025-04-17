---
label: "Batch Criteria"
route: /synapse/batch-request/batch-criteria
order: -3
---
# Batch Criteria

Examples below for more complex batching requirements. Most projects will not need to define custom batch criteria.

## Batch Criteria

### Authorizers and Dependents definition

Authorizers - these are typically parents, but not limited to just parents. They are anyone who is authorized to submit information for your study. An authorizer can also be an information provider, ie an outside reporter who is providing information like a grandparent or friend or teacher.

Dependents - these are typically children in the family but can be anyone for whom an authorizer is supplying information about said dependent(s).

### Age criteria

Age in years is specified at batch invite. The reason we do this is that after the invite is sent we can not unsend, thus we only invite the age at batch max giving enough time for participants to receive the reminders to participate. This can vary per project but we usually recommend at least 1 month under the maximum study age for the age at batch.

Age in years by authorizer or dependent examples

- authorizer max age in study of 26 years
    -   if your study needs 2 months time then we would max age at batch use 25.833 years
    -   criteria: **and authorizer age in years < 25.833**     
- dependent max age of 14 years
    - again a 2 month time buffer would use 13.833 years
    - criteria: **and dependent age in years < 13.833**
- age ranges uses BETWEEN
    - if your batching is targeting a specific age range for example 9 years to 11 years: BETWEEN 9 and 10.833
    - again the max age would still need the buffer from invite
    - criteria: **and dependent age in years BETWEEN 9 and 10.833**
-   order by
    - you can also order by age
    - this allows you for example to invite within an age range or a max age but by oldest or youngest first
    - this will typically be used for projects with limited eligible participants and the need to invite by the oldest first to reduce the number of participants who age out
    - example: need to invite dependents up to the max age of the study of 16 years, with order by oldest first
    - criteria: **and dependent age in years < 15.833 order by dependent age in years desc**
    - example: youngest first with a requested age range between 2 and 4 years
    - criteria: **and dependent age in years between 2 and 4 order by dependent age in years asc**
