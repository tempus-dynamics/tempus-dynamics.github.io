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

{.compact}
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
Editing communications and email templates uses a two-phase process to allow in-progress edits to be saved and tested in a development environment before taking effect in production. In the context of communications, this first phase is referred to as **staging** and the second phase of moving changes to production is referred to as **publishing**. Components with staged/unpublished changes will be visually identified in the communication and email template tables by a green border around the component's name. Staged changes to a template will take immediate effect in the development environment, but changes will not be visible in production emails until they are published.

!!!danger
While the communication interface is in its current beta testing phase, the publishing feature is accessible only to Tempus Dynamics employees.
!!!

### Substitutions
Both the communications and the email template interface support personalization of email messages through the use of substitutions. A substitution can be added to an email template or the communication's subject line, and each is specified by wrapping a pre-defined key or path in curly braces, e.g. `{key}` or `{container.key}`. Clicking the **Substitutions** button at the top of the left panel in the communications interface opens the substitutions table, where current example substitutions can be edited for testing purposes.

!!!warning
Substitutions are always enabled on the communications page but are disabled by default on the email template page. To test substitutions while editing a content template, be sure to enable substitutions at the top right.
!!!

![Substitutions table.](/shared/images/substitutions-table.png)

{.compact}
\# | Control | Description
---: | --- | ---
1 | Copy Control | Click to copy the full substitution value (including braces).
2 | Substitution Key | The unique key or path that defines the substitution.
3 | Value | The current value of the substitution to be used for testing purposes. Click to edit the current value. (Modified values will not be saved.)

#### Substitution Templates
Depending upon the intended usage of a particular communication, different substitution values may be available for use. Substitution templates provide a convenient list of defined substitution values. **Changing a communication's substitution template does not inherently change which substitution values will be available when the communication is sent, only the values that will be available for testing purposes.** The list of substitution templates is provided below, and helpful tooltips are also provided when hovering over each option in the editor. If you have questions about which template should be selected for a given communication please contact Tempus Dynamics for further assistance.

{.compact}
Name | Description
--- | ---
Branding | For Branding email templates only.
Chronos Admin | For scheduling notifications and reminders to admins via the [Chronos scheduling system](/nexus/chronos/index.md).
Chronos Participant | For scheduling notifications and reminders to participants via the [Chronos scheduling system](/nexus/chronos/index.md).
Email Verification | For email verification notifications.
Event Notification | For notifications triggered by task completions.
Event Reminder (Account-Holder) | For task-specific reminder emails configured to send only once even if multiple instances of the same task are present.
Event Reminder (Individual) | For task-specific reminder emails configured to send for each instance of a given task.
File Reminder | For reminders triggered by unseen new files with a designated file tag.
Incentive Email | For incentive notification emails.
Invitation Email | For invitations to join an existing family.
Password Reset | For password reset notifications.
Participant Communication | Default template for individualized notifications and reminders.

#### Custom Substitutions
If no substitutition template is specified or a selected template supports adding custom values, the substitution table will allow adding (and removing) custom substitutions.

![Substitutions table with custom substitutions enabled.](/shared/images/custom-substitutions.png)

{.compact}
\# | Control | Description
---: | --- | ---
1 | Add Custom Substitution | Click to add a new custom substitution value.
2 | Container | The name of a parent field that will contain the custom substitution. (If no substitution template is selected, a container value will not be set.)
3 | Custom Key | The key or path of the custom substitution value.
4 | Delete | Click to remove the custom substitution value.

!!!danger
Custom substitutions require additional configuration outside of the communications system to function as expected. Please contact Tempus Dynamics if you want to configure custom substitutions.
!!!

### HTML Content
Email templates utilize HTML to render message content. For convenience, both a Rich Text Editor and an HTML Editor have been provided to edit email templates, but due to limitations with the Rich Text Editor, more advanced formatting and styling may require using the HTML Editor. The last editor used for a given email template will be saved, and reopening that template will default to using the last saved editor. Supported features of each editor are listed in the table below:


{.compact}
Feature | Rich Text Editor | HTML Editor
--- | :---: | :---:
General text editing | :icon-check: | :icon-check:
Basic formatting (e.g. bold, italics, underline, font color) | :icon-check: | :icon-check:
Simple links & images | :icon-check: | :icon-check:
Copy-paste text with formatting | :icon-check: | :icon-dash:
Advanced styling (e.g. buttons, tables, image styling) | :icon-dash: | :icon-check:

!!!warning HTML Limitations
Using the HTML Editor allows various customizations that are not possible with the Rich Text Editor, but due to security concerns and the limitations of email providers, there are still several major limitations to HTML content:

- Event attributes and script tags are not supported and will be removed from saved templates.
- CSS classes and style tags are not supported. All custom styles must be added in-line via the style attribute.
- HTML content cannot be guaranteed to render in exactly the same way in all email clients or apps. When designing a new message, always assume that fonts and colors may be overridden by a user's email client or device.
!!!

#### Images
The Rich Text Editor includes an **Add Image** button that supports adding a URL and alt parameters, as well as specifying the absolute width and height of an image (in pixels). However, the HTML Editor supports more advanced image styling, including scaling width or height as a percentage of the recipient's screen size. When considering how to include images in an email, keep in mind the following best practices:

- Many or most recipients will view email notifications on mobile devices, so images should be sized appropriately for smaller screens. (Using a style attribute including `max-width: 100%;` will ensure images scale to fit the recipient's screen.)
- Images should never be enlarged beyond their inherent size or resolution.
- The alt attribute should always be included with an image so that screen readers will function appropriately.

!!!info Image Hosting
Images must already be hosted on public web pages in order to be used in email communications. You can host images via your own website or file hosting service, or Tempus Dynamics will provide hosting via a third-party service such as [Cloudinary](https://cloudinary.com/).
!!!

#### Links & Buttons
The Rich Text Editor includes an **Add Link** button that supports adding a simple link and toggling whether to open in a new tab. Although this is sufficient for most email messages, in some scenarios it may be preferable to visually render the link as a button or configure other settings using the HTML Editor. Example use cases are provided below.

==- Disable Click Tracking
Click tracking is automatically enabled by default for all URLs except mail to links. Adding `clicktracking="off"` as the **FIRST** attribute to an `a` tag will disable click tracking for that specific URL. As a best practice, click tracking should be disabled for dynamic links that will be individualized to a specific user.

```html
<a clicktracking="off" href="https://tempusdynamics.com">Link</a>
```
==- URL Substitution
Dynamic links can be configured via the substitution feature so that different links can be conditionally replaced or individualized for specific users or circumstances. For example, the substitution templates for incentive and password reset emails include specific URL substitutions intended for this purpose. Substitutions may also be inserted into the middle of a URL as a route or query parameter.

```html Full Substitution
<a href="{substitution}">Link</a>
```

```html Partial Substitution
<a href="https://tempusdynamics.com/{substitution}">Link</a>
```
==- Custom Styling
Numerous style attributes are supported on links to customize the layout and appearance. In the example below, an outer `div` has been added to center the link, which has been styled to appear as a blue button with white text.

```html Centered Button Link
<div style="text-align: center">
    <a href="https://tempusdynamics.com" style="background-color: #3273DC; border: 1px solid #FFFFFF; border-radius: 5px; color: #FFFFFF !important; display: inline-block; font-size: 16px; line-height: 13px; padding: 13px; text-align: center; text-decoration: none">Link</a>
</div>
```
==- Advanced Configuration Example: Reset Password Button
The example below combines various link configurations to create stylized "Reset Password" button.

```html Button Link with Multiple Configurations
<div style="text-align: center">
    <a clicktracking="off" href="{resetUrl}" style="background-color: #3273DC; border: 1px solid #FFFFFF; border-radius: 5px; color: #FFFFFF !important; display: inline-block; font-size: 16px; line-height: 13px; padding: 13px; text-align: center; text-decoration: none">Reset Password</a>
</div>
```
==-

### Testing
The communications interface includes a **Test** button that allows users with edit permissions to send test copies of that communication to one or more recipients. The current substitution value settings will be applied when sending test emails. The **Preview Source** control at the top left can also be used to toggle between sending a test copy of the Staging or Production version of the communication.