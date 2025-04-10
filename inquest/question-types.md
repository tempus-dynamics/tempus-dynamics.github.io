---
label: "Question Types"
route: /inquest/question-types
---
# Question Types

## Radio
Radio questions are a type of single-selection multiple choice input based on a predefined list of response options. Each response option typically has a numeric coded value.

## Text
Text inputs allow open entry of user text responses. Responses can also be constrained to specific formats including emails, phone numbers, or other custom regex patterns. Standard text inputs can be rendered as either a single inline input or a text area.

## Numeric
Numeric inputs allow user entry of numeric values. Responses can be constrained to specific ranges of values as needed.

## Date Picker
Date picker inputs allow users to enter date strings or select date values from a calendar widget. The text and coded values for date picker inputs are both string representations of the selected date.

## Time Picker
Time picker inputs allow users to enter a time string or select a time value from a time/clock widget. The text and coded values for time picker inputs are both string representations of the selected time.

## Dropdown
Dropdown inputs function similarly to radio inputs but are visually rendered as a single-selection dropdown list. This input type is strongly recommended for questions with large numbers of predefined responses. This input type also supports advanced features like searchable response options and external response option data sources.

## Multi-select
Multi-select inputs are rendered as collections of individual checkbox inputs. While typically referred to as a single input object, in data terms each individual option is treated as its own input and stored as a separate answer. Selected responses are typically stored with a coded value of 1.

!!!warning Unchecked vs. Unanswered
Because checkboxes are pure binary inputs, it is impossible to distinguish between a negative and non-response. Due to this limitation, any unselected answers for multi-select inputs will be marked as unanswered.
!!!

## Ranking
Ranking questions allow relative rankings of different response options. While typically referred to as a single input object, in data terms each individual option is treated as its own input and stored as a separate answer.