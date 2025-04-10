---
label: "Participant Tasks"
route: /nexus/admin-portal/participant-tasks
order: -5
---
# Participant Tasks
The participant tasks page displays a record of all [events](/nexus/glossary.md#event) assigned to a participant. These events typically are surveys completed by the participant or the participant's guardian, but may also include admin tasks that administrators are expected to complete. Events are sorted from oldest to newest created by default, but can also be sorted by task name, language, status, or updated date. You can click the `Refresh Data` button to pull the latest event data for the participant without reloading the entire page; this can be useful if opening and completing surveys in separate tabs.

![Participant tasks table.](/nexus/images/participant-tasks.png)

## Assign
Start typing in or select an event from the dropdown at the top of the participant tasks page, then click `Assign New Task` to assign an event to a participant. Assignable events are sorted in groups, starting with Admin Surveys, then by language. After assigning a task, your name will appear in the `Created By` column of the tasks table next to the newly created event.

!!!danger
Manually assigning a task bypasses all automation normally associated with that event, including automatic unassignment!
!!!

## Block
Use the Block task dropdown at the bottom of the participant tasks page, or right-click an existing event and select `Edit Task` > `Block`, to block all currently active and future assignments (including automated assignment) of that event for the selected participant. Once blocked, an event may only be unblocked by right-clicking and selecting `Unblock`. Blocked events are not visible on the [participant dashboard](/nexus/participant-portal/participant-dashboard.md).

![Blocked tasks table.](/nexus/images/blocked-tasks.png)

## Task Context Menu
Right-clicking on any row in the tasks table will open up a context menu including several task-specific controls. The available options differ depending on the specific event type and status.

### Access Survey
The `Access Survey` menu option is available for active tasks. This option will open a survey instance, allowing administrators to complete the task on behalf of the participant. This is the primary means of accessing and completing admin tasks.

### Reports
The `Reports` menu option is available for completed tasks. This option will open a sub-menu that contains any report links related to the event. This option will be disabled if no report links are available.

### Edit Task
The edit task sub-menu provides generic controls common to all task types.

#### Remove
The `Remove` control allows you to remove the assignment of any active task.

!!!warning
Removing a task does not disable any automation configured for that event, so the next cycle of criteria evaluation may automatically reassign events if the participant would normally qualify!
!!!

#### Resubmit
The `Resubmit` control allows you to trigger or retrigger the survey submission process for any active task. This control is most commonly used in the scenario that a survey submission is completed on the Inquest platform but does not register as complete in the Nexus platform due to redirect issues or other transient errors. This control can also be used for testing purposes to bypass completion of a survey.

!!!warning
Submitting an event without completing the associated survey may lead to unexpected behavior, especially for registration tasks. Please verify the associated survey instance is complete before selecting this option! 
!!!

#### Block
The `Block` control behaves as described in the [Block](#block) section above. If more than one instance of the same task is assigned, all instances will be blocked. You may initiate the block from any active or completed task, but only active tasks will be blocked.

#### Invalidate
The `Invalidate` control is available for any completed task. Invalidation of an event will cause our automated assignment systems to ignore that event instance in its entirety. Any notifications or other effects triggered by this instance will not be undone, but it may impact future event assignments. Invalidated events will be hidden from the [participant dashboard](/nexus/participant-portal/participant-dashboard.md) but shown with a red highlight on the tasks page.

![Invalidated event row in the admin portal.](/nexus/images/invalidated-task.png)

### Edit Appointment
The edit appointment sub-menu is available on any scheduler-type events. It allows access to a set of scheduler-specific functions.

#### Complete
The `Complete` control is available on any active or pending scheduler event. This control behaves similarly to the [Resubmit](#resubmit) control for tasks but also finalizes the appointment in the Chronos scheduling system.

#### Reschedule
The `Reschedule` control is available for any pending scheduler event. This control will temporarily cancel a scheduled appointment. After selecting this option, an administrator is prompted to enter a reason for the reschedule request. The text entered will be added as a note in the participant notes section and included on a reschedule request notification sent to the participant. After this request has been triggered, the participant can access the scheduler survey again to select a new time for their appointment.

#### Cancel
The `Cancel` control is available for any pending scheduler event. This control will permanently cancel a scheduled appointment. After selecting this option, an administrator is prompted to enter a reason for the cancellation. The text entered will be added as a note in the participant notes section and included on a cancellation notification sent to the participant. After this cancellation has been triggered, the participant will no longer be able to reschedule their appointment.