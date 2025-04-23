---
label: "Data Retrieval"
route: /inquest/data-retrieval
---
# Data Retrieval

## API
Data collected via the Inquest3 platform can always be pulled in its raw format via the Tempus Research API given a particular Survey ID. Contact Tempus Dynamics or see the API documentation for further details: https://docs.tempusresearch.com/

## Synapse Data Distribution

For projects run through the Synapse engine, Tempus provides a service of data distribution via spreadsheet files generated on a per-project and per-survey basis. In this format, each answer in the raw survey response data is flattened to the single, most relevant value: typically the coded value or the status of the answer.

### Answer Statuses
In addition to specific responses, each survey question also records its status. During data distribution, these statuses may be customized per-project as specific codes such as `-1`, `-999`, `[Unanswered]`, `[Unseen]`, etc. The specific statuses and their meanings are detailed below.

#### Dropoff
An answer has a status of Dropoff if the user did not progress far enough through a survey to encounter the question. For example, if a user only progresses to page 2 of a survey, all answers to questions on page 3 and beyond will be returned with a status of Dropoff.

!!!
When pulling responses from the API, a particular alias can be considered to have a status of Dropoff if it is not included the Answers object.
!!!

#### Unseen
An answer has a status of Unseen if custom logic within the survey prevented the question from being rendered. For example, if question B is only rendered when the response to question A is Yes/1 then for users who responded No/0 to question A, answers to question B will be returned with a status of Unseen.

#### Unanswered
An answer has a status of Unanswered if the question was rendered but the user did not provide a response.

!!!warning
In some scenarios, it is not possible to distinguish between a negative and non-response. In such cases, the Unanswered status is used as the default answer value. See [Question Types](/inquest/question-types.md) for more details.
!!!

### Other Customizations
Other customizations of data distribution are available upon request. Requirements for data distribution files should be fully detailed and documented before the launch of a project to ensure that the request can be fulfilled.