---
label: "Participant Communications"
route: /nexus/admin-portal/participant-communications
order: -7
---
# Participant Communications
The communcations tab details a history of all communications sent to a specific participant account, as well as a history of email addresses used for a specified account. For each email communication that has been sent, the table indicates the date it was sent, identifying information about the template, and key performance metrics including delivery, clicks, and opens. Clicking on each specific row will also expand a detailed preview of the specific message contents and a table of click rates for individual URLs contained in that email.

![Participant communications tab.](/nexus/images/participant-communications.png)

## Email Delivery
The delivered date indicates when an email message was successfully delivered to the target email address. A successful delivery verifies that the email address is valid and capable of receiving messages, but it does not necessarily mean a participant has opened the email.

## Clicks vs Opens
The primary performance indicators to evaluate whether a participant has actually opened an email are clicks and opens. Opens are recorded using a hidden image appended to the email contents, which increments each time the email is opened by the participant. Clicks are recorded each time the participant clicks on any link within the email (excluding mailto links).

!!!warning
Due to the open metric's reliance on loading an image, it may sometimes be blocked by anti-spam features. This may result in scenarios where the open metric has a value of 0 but one or more clicks are recorded. For the most reliable numbers, clicks should be considered in most circumstances.
!!!

## Bounced, Dropped, and Spammed
The bounced, dropped, and spammed dates indicate failure or rejection of an email message:

Bounced
:   The message was rejected by the receiving server. This may indicate the address doesn't exist, the mailbox is full, or there was some other technical reason that the message could not be delivered. Once one message to an email address is flagged as Bounced, future messages may be Dropped.

Dropped
:   The recipient was previously bounced, so the email message was not sent.

Spammed
:   The recipient or their email provider flagged the message as spam.