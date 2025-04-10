---
label: "Schedule"
route: /nexus/chronos/schedule
order: -1
---
# Schedule
For projects utilizing Tempus Research's scheduling service Chronos, a calendar of scheduled appointments is available via the "Calendar" link in the account menu at the upper right corner. Filtering options for the schedule interface are details below. You can also access your personal [availability](/nexus/chronos/availability) (if configured) using the "My Availability" button at the upper right. 

!!!
After changing a filter option, you must navigate to a different time window or click the "Refresh" button to update the display. Refreshing/reloading the page will restore everything to the default settings.
!!!

![Schedule interface.](/nexus/images/schedule.png)

## Calendar Selection
If you have your own calendar set up through Chronos, this interface will select your calendar and show only your personal appointments for the week. Otherwise, you will be shown all the appointments for the selected week. You can change this selection using the Calendar selection dropdown at the upper left.

!!!
Clearing all selections or selecting all calendars will both result in a schedule display that includes all appointments.
!!!

## Appointment Status
Only scheduled and rescheduled appointments will be included in the display by default. You can include appointments with other statuses as well by selecting the desired status(es) in the Appointment Status dropdown at the upper right. The available statuses are as follows:
- **Scheduled** - The appointment has been scheduled, and its start time has never been changed.
- **Rescheduled** - The appointment has been scheduled, and its start time has changed one or more times.
- **Reschedule Requested** - The appointment needs to be rescheduled by administrator request. (The timeslot occupied by this appointment is the most recent time for which the appointment was scheduled prior to the reschedule request.)
- **Completed** - The appointment was completed successfully.
- **Cancelled by Admin** - An administrator cancelled the appointment and will not pursue rescheduling. (The timeslot occupied by this appointment is the most recent time for which the appointment was scheduled prior to the cancellation.)

The following status is an optional configuration that is not available to users by default. If you have not requested this functionality, your appointments will not utilize this status.
- **Cancelled by User** - The user cancelled the appointment and will not pursue rescheduling.  (The timeslot occupied by this appointment is the most recent time for which the appointment was scheduled prior to the cancellation.)

!!!warning
At the upper left, a counter of different statuses is provided for your convenience. The numbers listed her include only the statuses that are currently selected in the Appointment status filter. In other words, if the filter does not include completed appointments, the count of completed appointments will always remain 0.
!!!

## Appointment Menu
By right clicking on any appointment shown in the schedule, you will be provided a menu of options, allowing you to take the following actions:
- **Complete** - complete the appointment
- **Reschedule** - trigger a reschedule request
- **Cancel** - cancel the appointment
- **History** - view the [appointment history](/nexus/chronos/appointment-history)
- **Details** - open the participant's details page
- **Tasks** - open the participant's tasks page