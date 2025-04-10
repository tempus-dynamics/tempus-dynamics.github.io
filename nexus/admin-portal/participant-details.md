---
label: "Participant Details"
route: /nexus/admin-portal/participant-details
order: -4
---
# Participant Details
The participant details page provides a view to edit and access participant profile data. The layout and contents of this page are highly configurable per circle.

Fields must be one of the built-in properties described below or a custom property defined for the circle. The layout can be configured to group properties together with headings for each section, or to order fields individually on the page in a 12-column grid system.

## Common Built-In Properties
A number of built-in properties are predefined and available for use in any circle. Any combination of the below properties may be configured for read-only view or editing in both the admin portal and participant dashboard.

!!!warning
Account status and participant status serve very similar roles in terms of Nexus' automation, but account status is entirely managed and controlled at a system-wide level whereas participant status is set according to your research protocol or other registry needs and may also be manually managed by administrators.
!!!

==- Account Status &nbsp; [!badge Read Only]
`accountStatus`

Account status is set automatically by the Nexus system and cannot be changed. Values for this field include the following:

**Active**
:   The participant has registered and verified their account.

**Unverified**
:   The participant has initiated registration but not verified their email address.

**Invited**
:   The participant has been invited to participate but not yet accepted the invitation.

**Blocked**
:   The participant's account has been blocked and may no longer log in.

==- Participant Status
`participantStatus`

Participant status is indicated by the large colored banner at the top of the participant details page. This field plays a similar role to account status, but is editable by administrators. Values for this field include the following:

**Pending**
:   The participant has registered but not yet consented to participate.

**Consented**
:   The participant has fully consented to participate.

**Aged_Out**
:   The participant previously consented to participate as a child but has not yet reconsented as an adult.

**Ineligible**
:   The participant was deemed ineligible and may no longer participate.

**Withdrawn**
:   The participant voluntarily opted out of participation.

==- First Name
`firstName`

The participant's first name.
==- Middle Name
`middleName`

The participant's middle name.
==- Last Name
`lastName`

The participant's last name.
==- Registration Date &nbsp; [!badge Read Only]
`createdAt`

The date when the participant's account was created.
==- Birth Date
`birthdate`

The participant's date of birth.
==- Age &nbsp; [!badge Calculated Field]

The participant's age, automatically calculated based upon their listed date of birth. This value is only available in the Nexus admin portal and is not returned via the API. The format of the displayed age in the admin portal is configurable:

Years
:   The age in years (rounded down).

    !!!info
    Example: 2.5 years = 2
    !!!

Months
:   The age in months (rounded down).
    
    !!!info
    Example: 2.5 years = 30
    !!!

Years and Months
:   The age in a combination of years and months (rounded down).
    
    !!!info
    Example: 2.5 years = 2 : 6
    !!!

==- Language
`language`

The participant's registered language. When returned from the API, this value will be a two-character language code according to the ISO 639-1 standard.
==- Email Address
`email`

The participant's email address.

!!!warning
When updating an email address, the new address must be verified before the change is finalized.

Email addresses may only be updated for participants that already have an email address. Adding an email address to an account that does not already have one requires using a separate invitation process.
!!!
==- Address
`address`

The participant's street address. The address is subdivided into the following fields:

`address1`
:   The street and house number.

`address2`
:   Optional secondary address information, such as apartment number.

`state`
:   The state or territory. For U.S. addresses, this value may be the state's standard two-letter abbreviation.

`city`
:   The town, city, or village.

`zip`
:   The postal code.

`countryCode`
:   The two-character country code, according to the ISO 3166-1 standard.

==- Phone Numbers
`contactInfo.phones`

The list of the participant's phone numbers.
==- Do Not Contact
`contactInfo.doNotContact`

The do not contact flag, which can be used to disable sending reminders to a participant. Account-related emails (e.g. password reset) and notifications triggered directly by task submission may still be sent.
==-

## Other Registry Properties
Each registry is pre-configured to utilize a customizable set of [identifiers](/nexus/glossary.md#identifier) and properties. Any registry property can optionally be included on the participant details page as an editable or readonly value.

Contact Tempus to request updates to your registry identifiers or properties.