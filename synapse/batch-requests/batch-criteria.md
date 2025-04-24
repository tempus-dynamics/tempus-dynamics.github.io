---
label: "Batch Criteria"
route: /synapse/batch-request/batch-criteria
order: -3
---
# Batch Criteria

Examples below for more complex batching requirements. Most projects will not need to define custom batch criteria.

## Batch Criteria

### Authorizers and Dependents definition

[Authorizers](https://platforms.tempusresearch.com/synapse/glossary/#authorizer)

[Dependents](https://platforms.tempusresearch.com/synapse/glossary/#dependent)

### Age criteria

Age in years is specified at batch invite. The reason we do this is that after the invite is sent we can not unsend, thus we only invite the age at batch max giving enough time for participants to receive the reminders to participate. This can vary per project but we usually recommend at least 1 month under the maximum study age for the age at batch.

Age in years by authorizer or dependent examples

- Authorizer max age in study of 26 years
    -   If your study needs 2 months time then we would max age at batch use 25.833 years
    -   Criteria: **and authorizer age in years < 25.833**     
- Dependent max age of 14 years
    - Again a 2 month time buffer would use 13.833 years
    - Criteria: **and dependent age in years < 13.833**
- Age ranges uses BETWEEN
    - If your batching is targeting a specific age range for example 9 years to 11 years: BETWEEN 9 and 10.833
    - Again the max age would still need the buffer from invite
    - Criteria: **and dependent age in years BETWEEN 9 and 10.833**
-   Order by
    - You can also order by age
    - This allows you for example to invite within an age range or a max age but by oldest or youngest first
    - This will typically be used for projects with limited eligible participants and the need to invite by the oldest first to reduce the number of participants who age out
    - Example: need to invite dependents up to the max age of the study of 16 years, with order by oldest first
    - Criteria: **and dependent age in years < 15.833 order by dependent age in years desc**
    - Example: youngest first with a requested age range between 2 and 4 years
    - Criteria: **and dependent age in years between 2 and 4 order by dependent age in years asc**

### Custom project properties

Your study may include custom properties for authorizer and/or dependents. This will be setup as part of your study eligibility and used to filter, sort, and prioritize your analysis as well as batching order.

Common custom property examples

- sex
- diagnosis
- zipcode
- distance from clinic
- race
- ethnicity
- language_level

The Tempus Dynamics team will assist you in setting up your custom batch criteria based on these properties.

Examples

- your study may need to focus on getting more female dependents with ASD
    - criteria: and dependent sex = 'female' and dependent diagnosis = 'ASD'
- if you needed to batch by language levels of 1 and 2 or 3 and 4
    - criteria: and dependent language_level in (1, 2)
    - criteria: and dependent language_level in (3, 4)
