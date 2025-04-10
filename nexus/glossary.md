---
label: "Glossary"
route: /nexus/glossary
order: -1
---
# Glossary
Common terms used on the Nexus platform.

## Circle
A circle in Nexus defines a subset of participants that make up a single registry. Each circle has configurable branding, data properties, surveys, and other settings that can be customized to meet virtually any needs. Administrator accounts may have access to one or more circles, with permissions specified separately per circle. Participants are members of one and only one circle, but are not prohibited from using the same email to create accounts in multiple circles.

## Event
An event is a generic representation of a survey or other task, usually targeted at participants. The majority of events represent surveys or admin surveys that participants or administrators (respectively) are expected to complete. Events can be assigned manually via the admin portal, or automatically using the Nexus criteria system.

## Identifier
An identifier is a specialized property used to uniquely identify participants. To maintain data integrity, identifiers should not be modified and must be completely unique. Identifiers may be included as visible fields on the participant details page or as hidden fields, but in either case any identifier may be used to pull participant data via our API.

!!!success
One identifier per circle may be specified as the primary identifier and will be included automatically in certain interfaces like the participants table.
!!!

## Project
A Nexus project is a collection of events that can share criteria and other properties. Projects help to organize events and allow for more efficient automation.