---
label: "Participant Search"
route: /nexus/admin-portal/participant-search
order: -3
---
# Participant Search
The Nexus admin portal provides two components for searching for individual participants: the participants table and the advanced search query builder.

## Participants Table
The participants table provides access to a quick listing of all current participants in the registry with several convenient searchable and sortable fields. Double clicking on any row in the participants table will open the [participant's details](/nexus/admin-portal/participant-details.md). Available search fields include:
- Search all - checks for string matches in any field
- Participant Identifier(s)
- Participant Status
- Email
- First Name
- Last Name
- Language

![Participants table.](/nexus/images/participants-table.png)

### Column Sorting
Click on any column name to toggle sorting by that field. To sort by mutliple fields, hold Shift and click on each column in turn.

## Advanced Search
You can access advanced search functionality by clicking on the advanced search button at the top right corner above the participants table. The advanced search view includes access to a query builder widget, custom column selection, and data export features. The query builder supports filtering the participants table with greater granularity and precision through totally customizable queries. Complex queries can be built ad-hoc or saved to the system for future use.

!!!
Saved queries are stored per registry and will be made available to any other administrators of the registry.
!!!

### Parameters
The basic unit of each query is a parameter. A parameter is comprised of a data field (pre-configured for each registry), an operator (determined by the data type), and zero or more target values. Each parameter is evaluated as a boolean or true/false statement, which determines whether to include or exclude each participant in the query's results.

### Groups
Parameters can also be evaluated in blocks, called groups. Each query will at minimum contain one group of parameters that are evaluated as a whole. Each group also allows the designation of a conditional: `AND` or `OR`. A group with an `AND` conditional evaluates to true if all of its component elements evaluate to true, or false if any of its component elements evaluate to false. A group with an `OR` conditional evaluates to true if any of its component elements evaluate to true, or false if all of its component elements are false. The optional `NOT` parameter also allows for the inversion of any group's evaluation, meaning that any `NOT` group will evaluate to true if it normally would return false and vice versa.

!!!warning
Groups can be nested inside of other groups as deeply as necessary to create infinitely complex and detailed queries. However, the complexity of each query is directly proportional to the time needed to execute it.
!!!

![Advanced search grouping.](/nexus/images/advanced-search.png)

!!!
In the image above, the specified query is configured to filter the participants table down to all participants who are consented or between the age of 6 and 18. Both age parameter groups in this example evaluate a similar age interval in different ways. In many cases, it is possible to build functionally equivalent parameter groups with different individual parameters.
!!!

### Subqueries
Some queryable data included in the query builder, such as Task data, is accessed through a complex system of subqueries that requires additional care to group related parameters together. In general, when querying against any data that is not included on the participant details page, it is important to properly group queries to isolate distinct components. Grouping will automatically be applied beginning from the highest level for which a relevant parameter exists.

For example, to create a query to determine if a participant completed two distinct tasks, each task component should be isolated within its own parameter group so that the query will create distinct subqueries for each task group. Any task rules that are applied across task groups will result in a combined subquery that applies the parameters of both groups together.

![Task criteria variations](/nexus/images/subqueries.png)

!!!warning
In the above image, the first group of parameters represents an invalid query, while the other two groups represent an equivalent and valid representation of the same query. Group 1 will be executed as a query requesting "assigned tasks that are both Task A and Task B," which will always evaluate to false. Group 2 and Group 3 will instead be executed as individual subqueries of "assigned tasks that are Task A" and "assigned tasks that are Task B" respectively.
!!!