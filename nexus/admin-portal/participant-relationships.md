---
label: "Participant Relationships"
route: /nexus/admin-portal/participant-relationships
order: -9
---
# Participant Relationships
Each circle is comprised of numerous individual participants with various potential family structures. To accommodate virtually any form of family in a uniform way, a set of pre-defined relationships can be configured for each circle using the data points below.

## Pre-Defined Relationships
Each pre-defined relationship within a circle effectively represents half of the data required to represent the relationship between two participants. Only by combining these values together can one singular relationship be defined between two individuals. This relationship is said to be between Person 1 and Person 2, and includes fields labeled as Description 1, Role 1, Description 2, and Role 2.

==- Description
The specific name of a particular relationship, which will be displayed in the admin portal sidebar.
==- Role
A generic role that a particular relationship represents. This value can be used for generalizing more specific descriptions, such as combining `father` and `mother` descriptions under one `parent` role.
==- Linked Relationships
In most circumstances, one or more linked relationships may be defined for validation purposes (e.g. `parent` & `child`). A relationship may also be linked with itself (e.g. `sibling` & `sibling`). When a relationship is edited via the admin portal, it will not be considered valid unless Description 1 is a linked relationship to Description 2 and vice versa, or both are ["Other" relationships](/nexus/admin-portal/participant-relationships.md#other-relationships).
==- Position
For validation purposes, each description may be configured such that it will only be permitted in a specific position (i.e. as Description 1 or Description 2). This can be used to strictly limit parents to the first position and children to the second position.
==-

## Connection
In addition to the relationship roles and descriptions, each relationship must specify a connection that encompasses both of its halves (e.g. biological). If a connection is not specified, a value of `Other` will be used by default.

## Authority
The authority field dictates whether Person 1 has authority for Person 2, therefore the ordering of Person 1 and Person 2 in a relationship may have a semantic difference when considering authority. Relationships are thus generally considered to be directional, such that Person 2 is always equal or subordinate to Person 1. The possible authority designations include:

NONE
:   Person 1 has no authority for Person 2. Person 2's name will still be visible on the dashboard, but their data will not be viewable or editable by Person 1.

ALL
:   Person 1 has full authority for Person 2. Person 2 will be able to edit Person 1's data and complete surveys on behalf of Person 1.


!!!danger
Duplicate relationships are not permitted between Nexus participants, including reversed relationships. Therefore mutual authority (in which Person 1 and Person 2 both have authority for one another) is not currently possible. 
!!!

## "Other" Relationships
In addition to pre-defined relationships, free-form "Other" relationships may also be used. When editing relationships in the admin portal, any text may be entered into the Description 1 or Description 2 fields to specify an "Other" relationship. When doing so, the connection and role fields will automatically be changed to a value of `Other`.

## Editing Relationships
The Connection, Description, and Authority fields are all available for editing in the admin portal. By default the Connection and Authority fields are hidden, but they may be selected in the column chooser window (top right button).

![Relationships table.](/nexus/images/relationships-table.png)

### General Editing
To edit any of these fields, simply click on the corresponding cell, then enter a new value or select a pre-defined value from the provided dropdown menu. The table will smartly update any related fields where possible to minimize data entry errors. Modified fields will be highlighted green if changes are pending, or red if an invalid value is entered. To save these changes, click the save button at the top right.

### Swapping Relationships
In rare circumstances, relationship data may be incorrectly entered due to user error such that the individual entered as Person 1 should have been Person 2, and vice versa. To handle these cases, a Swap button has also been provided in the relationships table that will automatically swap the positions of Person 1 and Person 2. No other fields will be updated as part of the swap.