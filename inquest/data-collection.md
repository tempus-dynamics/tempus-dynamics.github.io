---
label: "Data Collection"
route: /inquest/data-collection
---
# Data Collection

All data collected through the Inquest3 platform is stored in a unified answer format primarily consisting of an `alias`, `codedValue`, and `textValue`, with additional metadata properties of `isUnseen`, `isUnanswered`, and other configuration options. The collected answers for a particular survey when returned from the Tempus API are formatted as a JSON object, with each individual answer represented by a key-value pair of the alias and answer object.

```json
{
    "alias": {
        "inputAlias": "alias",
        "textValue": "A",
        "codedValue": 1,
        "isUnseen": false,
        "isUnanswered": false,
        "codeBooksValue": null,
        "isDeidentified": false,
        "deidentifiedText": null,
        "data": {}
    }
}
```

Field | Type | Description
--- | --- | ---
inputAlias | string | This value is the same as the `alias`'s key within the answers object.
textValue | string | The text value of the selected/entered response option (if any).
codedValue | string or number | The coded value of the selected/entered response option. This may be a numeric or string value. If unseen or unanswered, this value will be null or an empty string.
isUnseen | boolean | A value indicating whether the input was hidden due to survey-based logic.
isUnanswered | boolean | A value indicating that the input was rendered but no answer was provided.
codeBooksValue | string or number | An aggregate value used by the Insight platform to streamline data display. This field typically has a value equivalent to the `codedValue` or one of the following string values: `Answered`, `Unanswered`, `Unseen`
isDeidentified | boolean | A value indicating that the input has been deidentified. This field is only used for questions that support open text responses.
deidentifedText | string | This value corresponds to the deidentified version of any text response provided. This field is only used for questions that support open text responses.
data | object | Additional data used by the Inquest platform for certain complex components.