---
label: "Appointment History"
route: /nexus/chronos/appointment-history
order: -3
---
# Appointment History
The appointment history page provides a detailed overview of changes made to an appointment over time. The top of the page renders the name of the appointment and the calendar event description. Below that, the appointment history table (see Figure 1 below) displays each change that has been made to the appointment over time. By default, this table is sorted from most recent to least recent changes.

![Figure 1: Appointment history table.](/nexus/images/appointment-history.png)

## Additional Columns
At the top right of the appointment history table, a column chooser control is available, which enables the selection of additional data columns not included in the default table layout. This control can also be used to hide currently visible columns. The Modified column may not be hidden.

## Timezones
The **Start Time** and **End Time** columns display the time of an appointment when converted into your local timezone. The recorded timezone for the participant is shown in the **Timezone** column.  The extra **User Start Time** and **User End Time** columns render the appointment time according to the participant's local timezone.

!!!warning
- Timezones may be up to 26 hours apart, meaning an appointment that takes place for an Interviewer on Monday may take place for the participant on Tuesday.
- 12-hour time formats are only dominant in English-speaking countries (mostly the U.S.). When communicating with international participants, AM/PM designations may cause confusion, so 24-hour time should be used instead.
- Typically, participants will not change timezones, but it is possible for an appointment to be scheduled in one timezone initially and rescheduled in another. If the timezone is changing repeatedly, this likely indicates a technical glitch.
!!!

TEST