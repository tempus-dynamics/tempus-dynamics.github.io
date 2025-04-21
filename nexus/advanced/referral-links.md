---
label: "Referral Links"
expanded: false
order: -1
---
# Referral Links
One or more special referral links can be configured utilizing the circle lists feature. Once this setting is enabled and the list has been published to production, these links can be appended to any registration link using the `referral` query parameter and a value equal to the coded value (or configured alternate coded value) of one of the list's available options. The full format of the registration link is:

```
https://<subdomain>.<domain.org>/account/create?referral=<code>
```

!!!
Invalid codes will be ignored and will not block registration.
!!!

## Example Use Case
As an example, suppose you have a custom domain `research.yourdomain.org`. You could configure a list with the following values and referral links to track registrations coming from different sources:

Coded Value | Text Value | Alternate Coded Value | Registration Link
---:|:---|:---|:---
1 | Website | website | `https://research.yourdomain.org/account/create?referral=website`
2 | Google | google | `https://research.yourdomain.org/account/create?referral=google`
3 | Facebook | facebook | `https://research.yourdomain.org/account/create?referral=facebook`

!!!danger
When using alternate coded values, remember:
- Text entered into a URL is NOT case sensitive.
- All configured values must be unique.
- Some characters (especially spaces) must be encoded to be used in a url. As a best practice, use only alphanumeric characters and hyphens (e.g. use `senor-frog` instead of `Señor Frog`).
!!!