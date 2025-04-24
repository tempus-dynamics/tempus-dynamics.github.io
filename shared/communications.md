---
label: "Communications (BETA)"
icon: mail
order: -6
---
[!badge variant="success" text="BETA - Nexus Only"]

# Tempus Research Communications
The Tempus Research platform uses a robust email framework that enables a multitude of highly configurable notifications and reminders. These messages are comprised of two primary components: communications and email templates.

!!!success
All admin portal users will be able to view communications and email templates, but only designated users will be granted permission to edit. To update permissions for your team, please contact Tempus Dynamics.
!!!

+++ Nexus
To access Nexus communication elements, select **More** > **Communications** or **More** > **Email Templates** in the [Nexus admin portal](/nexus/admin-portal/index.md).
+++

## Filtering
Both the communications and email template tables support several filtering options and controls. The screenshot below has been numbered for reference.

![Communication list filters.](/shared/images/comm-filters.png)

\# | Control | Description
---: | --- | ---
1 | Nexus Circle Filter | This control allows users to filter the table to a single circle. This filter will be hidden if the user does not have access to any circles or has access to only one circle and zero projects.
2 | Synapse Project Filter | This control allows users to filter the table to a single project. This filter will be hidden if the user does not have access to any projects or has access to only one project and zero circles.
3 | Status Filter | The status filter allows users to filter the table to only published or unpublished components (see [Editing & Publishing](#editing--publishing).) By default, both published and unpublished items will be listed.
4 | Archive Filter | The archive filter allows users to filter the table to only active, only archived, or all components. By default, this filter is set to active only so that archived items will not be listed.
5 | New Component Button | This button allows users with editing permission to create a new component. This control will be hidden for users without editing permission. When creating a new communication or email template, users will be prompted to enter several required fields before the new element is created, including: name, language, platform (Nexus or Synapse), and identifier (circle or project).
6 | Refresh Button | This button allows users to refresh the contents of the table.
7 | Apply Button | This button applies any unapplied search settings. Pressing `Enter` on the keyboard will also apply these settings.

In addition to the filters above, users can also search by name, filter by language, and filter by template type (email templates only).

## Components


### Email Templates
The email template interface allows low-level editing of actual email content, which is divided across three template categories: branding, content, and signature. Templates are designed to be reusable and easily interchangeable, such that one branding or signature template can be used for many or even all communications within a registry or research study. Regardless of a template's type, the interface may be used to edit that template via either a Rich Text Editor or an HTML Editor.

Branding Templates
:   A branding template is required for all communications and defines the overall layout of the message. Branding templates should always use the `Branding` substitution template with its special substitution values (`content` and `signature`) to ensure that all communications using that template will function properly. The communication's selected content and signature templates will automatically be filled into the corresponding field when constructing the final message.

Signature Templates
:   A signature template is an optional component intended to allow consistent usage of a farewell message across multiple communications. Signature templates support text substitutions, but using substitutions in a signature template is not recommended due to the variety of different substitution templates that could be used by its parent communications.

Content Templates
:   A content template is the container for a communication's core content. In most cases, a content template will be used for one and only one communication, but it is possible to reuse content templates for multiple communications if desired (and if all communications use the same substitution template).

### Communications
The communication interface allows high-level changes and configuration of an individual email message, including selection of the language, subject line, sender name and address, and the underlying branding, content, and signature email templates.

## Editing & Publishing
When editing communications and email templates, saving changes uses a two-phase process to allow in-progress edits to be saved and tested in a development environment before taking effect in production. In the context of communications, this first phase is referred to as **staging** and the second phase of moving changes to production is referred to as **publishing**. Staged/unpublished changes will be visually identified in the communication and email template tables by a green border around the component's name.

!!!danger
While the communication interface is in its current beta testing phase, the publishing feature is accessible only to Tempus Dynamics employees.
!!!

### HTML Content
Email templates utilize HTML to render message content. For convenience, both a Rich Text Editor and an HTML Editor have been provided to edit email templates, but due to limitations with the Rich Text Editor, more advanced formatting and styling may require using the HTML Editor. Recommended use cases are listed below:

<style>
    .green-icon {
        color: green;
    }
    .red-icon {
        color: red;
    }
</style>

||| Rich Text Editor
:::green-icon
- :icon-check: This is sub-item 2.2
:::
:::red-icon
- :icon-circle-slash: This is sub-item 2.4
:::
||| HTML Editor
:::green-icon
- :icon-check-circle: This is sub-item 2.2
- :icon-circle-slash: This is sub-item 2.4
:::
:::red-icon
- :icon-check-circle: This is sub-item 2.2
- :icon-circle-slash: This is sub-item 2.4
:::
|||

### Substitutions


### Testing
The communications interface includes a **Test** button