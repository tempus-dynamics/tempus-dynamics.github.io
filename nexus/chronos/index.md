---
label: "Chronos (Legacy)"
exapnded: false
order: -5
---
# Chronos (Legacy)
Chronos is a scheduling service designed to facilitate scheduling of meetings between participants and administrators. Meetings will be added to digital calendar and automatically managed by the chronos@tempusdynamics.com account, which may be linked to an administrator's external calendar.

!!!danger
The Chronos application is considered a legacy product and is no longer under active development. If you are interested in configuring new scheduling services for your Nexus registry, please contact Tempus to discuss alternative solutions.
!!!

## Glossary

The following terminology is used when referring to Chronos data and services.

### Appointment
An appointment is an individual instance of a scheduled meeting between a specific participant and the configured resource.

### Booking
A booking is a meeting template, which includes the following configurations:

- Display name (also used as the calendar event title)
- Description (also used as the calendar event description)
- Minimum time prior to appointment start to allow rescheduling
- Minimum time prior to appointment start to allow cancellation
- Minimum time from now to allow new appointments to be scheduled (e.g. appointments must be made N days in advance)
- Maximum time from now to allow new appointments to be scheduled (e.g. appointments may be made up to N weeks in the future)
- Required buffer time between appointment slots (up to 24 hours)
- Default timeslot duration (up to 24 hours)
- Minimum timeslot duration (at least 30 minutes)
- Maximum timeslot duration (up to 24 hours)
- Change notification emails
- Reminder emails
- Linked resources

### Resource
A resource is a link between a booking and an individual account to allow meeting scheduling. Each booking may be configured to use one or more resources. Each resource sets its own availability, but when scheduling an appointment the combined availabilities of all resources are considered. If two or more resources have overlapping availability, an scheduled appointment will be assigned to one of the resources at random.