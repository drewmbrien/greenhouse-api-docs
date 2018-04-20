# Queries
## employee \([Employee](#[Employee](#employee))\)
An Onboarding employee record

Argument | Type | Description
--------- | ----------- | -----------
id | [Int](#int) | 
## employees \([EmployeeConnection](#[EmployeeConnection](#employeeconnection))\)
A collection of Onboarding employee records

Argument | Type | Description
--------- | ----------- | -----------
start_date | [DateFilter](#datefilter) | 
date_of_birth | [DateFilter](#datefilter) | 
with_custom_field_value | [WithCustomFieldValue](#withcustomfieldvalue) | 
## department \([Department](#[Department](#department))\)
A single department

Argument | Type | Description
--------- | ----------- | -----------
id | [Int](#int) | 
## departments \([DepartmentConnection](#[DepartmentConnection](#departmentconnection))\)
All departments

Argument | Type | Description
--------- | ----------- | -----------
## location \([Location](#[Location](#location))\)
A single location

Argument | Type | Description
--------- | ----------- | -----------
id | [Int](#int) | 
## locations \([LocationConnection](#[LocationConnection](#locationconnection))\)
All locations

Argument | Type | Description
--------- | ----------- | -----------
## team \([Team](#[Team](#team))\)
A single team

Argument | Type | Description
--------- | ----------- | -----------
id | [Int](#int) | 
## teams \([TeamConnection](#[TeamConnection](#teamconnection))\)
All teams

Argument | Type | Description
--------- | ----------- | -----------
## teamCategory \([TeamCategory](#[TeamCategory](#teamcategory))\)
A single team category

Argument | Type | Description
--------- | ----------- | -----------
id | [Int](#int) | 
## teamCategories \([TeamCategoryConnection](#[TeamCategoryConnection](#teamcategoryconnection))\)
All team categories

Argument | Type | Description
--------- | ----------- | -----------
## otherCriterion \([OtherCriterion](#[OtherCriterion](#othercriterion))\)
A single other criterion

Argument | Type | Description
--------- | ----------- | -----------
id | [Int](#int) | 
## otherCriteria \([OtherCriterionConnection](#[OtherCriterionConnection](#othercriterionconnection))\)
All other criteria

Argument | Type | Description
--------- | ----------- | -----------
## customField \([CustomField](#[CustomField](#customfield))\)
A custom field

Argument | Type | Description
--------- | ----------- | -----------
permanentFieldId | [ID](#id) | 
## customFields \([CustomFieldConnection](#[CustomFieldConnection](#customfieldconnection))\)
A collection of custom fields

Argument | Type | Description
--------- | ----------- | -----------
permanentFieldIds | [String](#string) | 
fieldTypes | [CustomFieldTypes](#customfieldtypes) | 
## countries \([[Country]](#[Country](#country))\)
The list of countries

Argument | Type | Description
--------- | ----------- | -----------
countryCodes | [String](#string) | 
## contactRelationships \([[String]](#[String](#string))\)
The list of valid options for the 'Contact' custom field type

Argument | Type | Description
--------- | ----------- | -----------
## rateLimit \([RateLimit](#[RateLimit](#ratelimit))\)
Information about your current API quota

Argument | Type | Description
--------- | ----------- | -----------
# Mutations
## updateEmployeeProfile \([Employee](#employee)\)
Update an employee's profile

Argument | Type | Description
--------- | ----------- | -----------
id | [ID](#id) | 
employeeUpdates | [UpdateEmployee](#updateemployee) | 
## addPendingHire \([PendingHire](#pendinghire)\)
Add a Pending Hire to Greenhouse Onboarding

Argument | Type | Description
--------- | ----------- | -----------
addPendingHireInput | [AddPendingHireInput](#addpendinghireinput) | 
# Types
## Country
A country

Field | Type | Description
--------- | ----------- | -----------
name | [String](#string) | 
countryCode | [String](#string) | 
states | [State](#state) | 

## CustomField
Represents a single CustomField record for your company.  CustomFields can be stored and displayed in a variety of    ways.  The types are described via the [CustomFieldTypes](#customfieldtypes) enum.

Field | Type | Description
--------- | ----------- | -----------
createdAt | [DateTime](#datetime) | 
updatedAt | [DateTime](#datetime) | 
name | [String](#string) | The name of this custom field as users would see it inside Greenhouse Onboarding.
permanentFieldId | [String](#string) | A unique identifier for this CustomField.
teamCategory | [TeamCategory](#teamcategory) | 
fieldType | [CustomFieldTypes](#customfieldtypes) | The field type determines how users input and view the data for this field.
customFieldGroup | [CustomFieldGroup](#customfieldgroup) | 
multipleChoiceOptions | [String](#string) | 

## CustomFieldConnection
The connection type for CustomField.

Field | Type | Description
--------- | ----------- | -----------
edges | [CustomFieldEdge](#customfieldedge) | A list of edges.
pageInfo | [PageInfo](#pageinfo) | Information to aid in pagination.

## CustomFieldEdge
An edge in a connection.

Field | Type | Description
--------- | ----------- | -----------
node | [CustomField](#customfield) | The item at the end of the edge.
cursor | [String](#string) | A cursor for use in pagination.

## CustomFieldGroup
A Group of Custom Field

Field | Type | Description
--------- | ----------- | -----------
id | [ID](#id) | 
name | [String](#string) | 

## CustomFieldValue
A Custom Field Value Record

Field | Type | Description
--------- | ----------- | -----------
created_at | [DateTime](#datetime) | 
updated_at | [DateTime](#datetime) | 
value_updated_at | [DateTime](#datetime) | The time of the most recent update to this field.
custom_field | [CustomField](#customfield) | 
value | [Value](#value) | A different type of value will be stored based upon the field type of the [CustomField](#customfield).  Some types    have the data stored as a nested object.  Note that the type is a scalar named [Value](#value).  Even though    it appears to be an object, you are not able to use GraphQL to determine its shape.

## Department
Represents a single department in your company.  Employees may belong to zero or one department. Departments are    used in a variety of ways in Greenhouse Onboarding, including permissions and onboarding plans.

Field | Type | Description
--------- | ----------- | -----------
id | [ID](#id) | 
createdAt | [DateTime](#datetime) | 
updatedAt | [DateTime](#datetime) | 
name | [String](#string) | 
description | [String](#string) | 

## DepartmentConnection
The connection type for Department.

Field | Type | Description
--------- | ----------- | -----------
edges | [DepartmentEdge](#departmentedge) | A list of edges.
pageInfo | [PageInfo](#pageinfo) | Information to aid in pagination.

## DepartmentEdge
An edge in a connection.

Field | Type | Description
--------- | ----------- | -----------
node | [Department](#department) | The item at the end of the edge.
cursor | [String](#string) | A cursor for use in pagination.

## Document
Represents a single document attached to an [Employee](#employee).

Field | Type | Description
--------- | ----------- | -----------
id | [ID](#id) | 
created_at | [DateTime](#datetime) | 
updated_at | [DateTime](#datetime) | 
file | [File](#file) | Contains the file payload.

## Employee
A single Employee that works for your company.

Field | Type | Description
--------- | ----------- | -----------
id | [ID](#id) | 
createdAt | [DateTime](#datetime) | 
updatedAt | [DateTime](#datetime) | 
phoneNumber | [String](#string) | 
about | [String](#string) | A brief description of the employee.  This information is displayed on both the employee's profile and is also    featured prominently in the Welcome Experience for any new hires that report to this employee.
startDate | [Date](#date) | 
dateOfTermination | [Date](#date) | This information is only available on terminated employees
dateOfBirth | [Date](#date) | Note that only administrators can see the birth year for employees
title | [String](#string) | The employee's job title.
department | [Department](#department) | 
location | [Location](#location) | 
email | [String](#string) | The employee's work email.  They need this in order to sign in
personalEmail | [String](#string) | The employee's personal email.
hrManager | [Employee](#employee) | The employee's HR Manager.
manager | [Employee](#employee) | This employee's direct manager.
employmentStatus | [EmploymentStatus](#employmentstatus) | 
workCountryCode | [String](#string) | 
firstName | [String](#string) | 
middleName | [String](#string) | 
lastName | [String](#string) | 
suffix | [String](#string) | 
preferredFirstName | [String](#string) | This is the name that your employee prefers to go by.  If this value is set, Greenhouse Onboarding will display    this name everywhere in the product instead of the employee's legal name.
preferredLastName | [String](#string) | 
profileImage | [File](#file) | A file containing the employee's profile image.  This image is displayed in emails, reports and directory pages.
customFieldValues | [CustomFieldValue](#customfieldvalue) | A list of all other profile information for this employee.  Administrators can configure these fields on the    [Settings > Custom Fields](https://onboarding.greenhouse.io/settings/fields) page.
documents | [Document](#document) | These are documents that came over from Greenhouse Recruiting, were attached directly to the employee    profile, or attached to a task.  This does _not_ include E-Signature requests.
otherCriteria | [OtherCriterion](#othercriterion) | 
signatureRequests | [SignatureRequest](#signaturerequest) | These are E-Signature requests initiated through Greenhouse Onboardinging.  Keep in mind that these requests can    be in a number of different states in their lifecycle and may not always have a signed document available to    download.

## EmployeeConnection
The connection type for Employee.

Field | Type | Description
--------- | ----------- | -----------
edges | [EmployeeEdge](#employeeedge) | A list of edges.
pageInfo | [PageInfo](#pageinfo) | Information to aid in pagination.

## EmployeeEdge
An edge in a connection.

Field | Type | Description
--------- | ----------- | -----------
node | [Employee](#employee) | The item at the end of the edge.
cursor | [String](#string) | A cursor for use in pagination.

## File
A File record

Field | Type | Description
--------- | ----------- | -----------
file_name | [String](#string) | The original name of the file.
file_size | [Int](#int) | The file size, in bytes
file_url | [String](#string) | An expiring URL you can use to download the file.
expires_at | [DateTime](#datetime) | The time when the URL will expire.  After this time, you will need to generate a new URL.

## Location
Represents a single location in your company.  Employees may belong to zero or one location. Locations are    used in a variety of ways in Greenhouse Onboarding, including permissions and onboarding plans.

Field | Type | Description
--------- | ----------- | -----------
id | [ID](#id) | 
createdAt | [DateTime](#datetime) | 
updatedAt | [DateTime](#datetime) | 
name | [String](#string) | 
description | [String](#string) | 

## LocationConnection
The connection type for Location.

Field | Type | Description
--------- | ----------- | -----------
edges | [LocationEdge](#locationedge) | A list of edges.
pageInfo | [PageInfo](#pageinfo) | Information to aid in pagination.

## LocationEdge
An edge in a connection.

Field | Type | Description
--------- | ----------- | -----------
node | [Location](#location) | The item at the end of the edge.
cursor | [String](#string) | A cursor for use in pagination.

## Mutation


Field | Type | Description
--------- | ----------- | -----------
updateEmployeeProfile | [Employee](#employee) | Update an employee's profile
addPendingHire | [PendingHire](#pendinghire) | Add a Pending Hire to Greenhouse Onboarding

## OtherCriterion
A tag that can be used to refine on onboarding plan

Field | Type | Description
--------- | ----------- | -----------
id | [ID](#id) | 
createdAt | [DateTime](#datetime) | 
updatedAt | [DateTime](#datetime) | 
name | [String](#string) | 

## OtherCriterionConnection
The connection type for OtherCriterion.

Field | Type | Description
--------- | ----------- | -----------
edges | [OtherCriterionEdge](#othercriterionedge) | A list of edges.
pageInfo | [PageInfo](#pageinfo) | Information to aid in pagination.

## OtherCriterionEdge
An edge in a connection.

Field | Type | Description
--------- | ----------- | -----------
node | [OtherCriterion](#othercriterion) | The item at the end of the edge.
cursor | [String](#string) | A cursor for use in pagination.

## PageInfo
Information about pagination in a connection.

Field | Type | Description
--------- | ----------- | -----------
hasNextPage | [Boolean](#boolean) | When paginating forwards, are there more items?
hasPreviousPage | [Boolean](#boolean) | When paginating backwards, are there more items?
startCursor | [String](#string) | When paginating backwards, the cursor to continue.
endCursor | [String](#string) | When paginating forwards, the cursor to continue.

## PendingHire
A Pending Hire Record

Field | Type | Description
--------- | ----------- | -----------
id | [ID](#id) | 
createdAt | [DateTime](#datetime) | 
updatedAt | [DateTime](#datetime) | 
firstName | [String](#string) | 
lastName | [String](#string) | 
preferredFirstName | [String](#string) | 
preferredLastName | [String](#string) | 
about | [String](#string) | 
dateOfBirth | [Date](#date) | 
department | [Department](#department) | 
email | [String](#string) | 
employmentStatus | [EmploymentStatus](#employmentstatus) | 
hrManager | [Employee](#employee) | 
location | [Location](#location) | 
manager | [Employee](#employee) | 
personalEmail | [String](#string) | 
phoneNumber | [String](#string) | 
startDate | [Date](#date) | 
title | [String](#string) | 
workCountryCode | [String](#string) | 
customFieldValues | [CustomFieldValue](#customfieldvalue) | 

## RateLimit
Information about your current API quota

Field | Type | Description
--------- | ----------- | -----------
limit | [Int](#int) | Your quota for the given period.
cost | [Int](#int) | The cost of this query. This amount was deducted from your previous quota.
remaining | [Int](#int) | The remaining balance for your quota. Any calls that exceed this value will be throttled.
resetAt | [DateTime](#datetime) | The time when your quota is reset to its maximum value.

## SignatureRequest
An E-Signature Request for assigned to an [Employee](#employee).

Field | Type | Description
--------- | ----------- | -----------
id | [ID](#id) | 
createdAt | [DateTime](#datetime) | 
updatedAt | [DateTime](#datetime) | 
signatureRequestTemplate | [SignatureRequestTemplate](#signaturerequesttemplate) | 
status | [SignatureRequestStatus](#signaturerequeststatus) | 
counterSigner | [Employee](#employee) | The employee responsible for counter-signing this document, if applicable.
file | [File](#file) | This is available only for completed signatures.

## SignatureRequestTemplate
A template used when assigning signature requests.

Field | Type | Description
--------- | ----------- | -----------
createdAt | [DateTime](#datetime) | 
updatedAt | [DateTime](#datetime) | 
name | [String](#string) | The name of the template.  This is the label administrators will see.
publicName | [String](#string) | The public-facing name of the template.  This is the name the new hire will see.    If this is null, new hires will see the name field.
counterSigner | [Employee](#employee) | The default employee responsible for counter-signing documents created from this template, if applicable.    Individual SignatureRequest objects can override the counter signer.

## State
A state

Field | Type | Description
--------- | ----------- | -----------
name | [String](#string) | 
stateCode | [String](#string) | 
country | [Country](#country) | 

## Team
A Team record

Field | Type | Description
--------- | ----------- | -----------
id | [ID](#id) | 
name | [String](#string) | 
description | [String](#string) | 
location | [String](#string) | 
email | [String](#string) | 
teamCategory | [TeamCategory](#teamcategory) | 

## TeamCategory
A Team Category Record

Field | Type | Description
--------- | ----------- | -----------
id | [ID](#id) | 
name | [String](#string) | 

## TeamCategoryConnection
The connection type for TeamCategory.

Field | Type | Description
--------- | ----------- | -----------
edges | [TeamCategoryEdge](#teamcategoryedge) | A list of edges.
pageInfo | [PageInfo](#pageinfo) | Information to aid in pagination.

## TeamCategoryEdge
An edge in a connection.

Field | Type | Description
--------- | ----------- | -----------
node | [TeamCategory](#teamcategory) | The item at the end of the edge.
cursor | [String](#string) | A cursor for use in pagination.

## TeamConnection
The connection type for Team.

Field | Type | Description
--------- | ----------- | -----------
edges | [TeamEdge](#teamedge) | A list of edges.
pageInfo | [PageInfo](#pageinfo) | Information to aid in pagination.

## TeamEdge
An edge in a connection.

Field | Type | Description
--------- | ----------- | -----------
node | [Team](#team) | The item at the end of the edge.
cursor | [String](#string) | A cursor for use in pagination.

# Input Objects
## AddPendingHireInput
Specify the properties of a new PendingHire

Argument | Type | Description
--------- | ----------- | -----------
about | [String](#string) | 
dateOfBirth | [Date](#date) | 
department | [ID](#id) | 
email | [String](#string) | 
employmentStatus | [EmploymentStatus](#employmentstatus) | 
firstName | [String](#string) | 
hrManager | [ID](#id) | 
lastName | [String](#string) | 
location | [ID](#id) | 
manager | [ID](#id) | 
middleName | [String](#string) | 
personalEmail | [String](#string) | 
phoneNumber | [String](#string) | 
preferredFirstName | [String](#string) | 
preferredLastName | [String](#string) | 
startDate | [Date](#date) | 
suffix | [String](#string) | 
title | [String](#string) | 
workCountryCode | [String](#string) | 
customFieldValues | [UpdateCustomFieldValue](#updatecustomfieldvalue) | 

## DateFilter
Specify a range of dates using after (exclusive >), before (exclusive <), or on (exact match)

Argument | Type | Description
--------- | ----------- | -----------
after | [Date](#date) | 
before | [Date](#date) | 
on | [Date](#date) | 

## DateTimeFilter
Specify a range of datetimes using after (exclusive >), before (exclusive <), or on (exact match)

Argument | Type | Description
--------- | ----------- | -----------
after | [DateTime](#datetime) | 
before | [DateTime](#datetime) | 
on | [DateTime](#datetime) | 

## UpdateCustomFieldValue
Used to update an employee's Custom Field Value

Argument | Type | Description
--------- | ----------- | -----------
permanentFieldId | [String](#string) | 
value | [Value](#value) | 

## UpdateEmployee
The input object used to update an [Employee](#employee).

Argument | Type | Description
--------- | ----------- | -----------
about | [String](#string) | 
dateOfBirth | [Date](#date) | 
department | [ID](#id) | 
email | [String](#string) | 
employmentStatus | [EmploymentStatus](#employmentstatus) | 
firstName | [String](#string) | 
hrManager | [ID](#id) | 
lastName | [String](#string) | 
location | [ID](#id) | 
manager | [ID](#id) | 
middleName | [String](#string) | 
personalEmail | [String](#string) | 
phoneNumber | [String](#string) | 
preferredFirstName | [String](#string) | 
preferredLastName | [String](#string) | 
profileImage | [URL](#url) | 
startDate | [Date](#date) | 
suffix | [String](#string) | 
title | [String](#string) | 
workCountryCode | [String](#string) | 
customFieldValues | [UpdateCustomFieldValue](#updatecustomfieldvalue) | 
otherCriteria | [ID](#id) | 

## WithCustomFieldValue
Limit employees to those that contain at least one of the specified CustomFieldValues that have been updated in the    provided time range.

Argument | Type | Description
--------- | ----------- | -----------
permanent_field_ids | [String](#string) | 
updated | [DateTimeFilter](#datetimefilter) | 

# Scalars
## Boolean
Represents `true` or `false` values.

## Date
Representation of a date in YYYY-MM-DD format.

## DateTime
Representation of datetime in RFC3339.

## ID
Represents a unique identifier that is Base64 obfuscated. It is often used to refetch an object or as key for a cache. The ID type appears in a JSON response as a String; however, it is not intended to be human-readable. When expected as an input type, any string (such as `"VXNlci0xMA=="`) or integer (such as `4`) input value will be accepted as an ID.

## Int
Represents non-fractional signed whole numeric values. Int can represent values between -(2^31) and 2^31 - 1.

## String
Represents textual data as UTF-8 character sequences. This type is most often used by GraphQL to represent free-form human-readable text.

## URL
A URL-formatted String

## Value
The actual value of a Custom Field Value. This type is capable of holding both Strings and Integers. Its content will
depend on the fieldType of its corresponding customField.

### text, long_text, confirmable
* Allowed Type(s): String
* Must be less than 3000 chars

### multiple_choice
* Allowed Type(s): String
* Must exactly match one of the customField's options

### multiple_select
* Allowed Type(s): String. Must be a JSON Array encoded string (with escaped quotes) e.g. `"[\"Option A\", \"Option B\"]"`
* Each option must be a String that exactly matches one of the customField's options

### team
* Allowed Type(s): String or Integer
* Value must be valid Team ID
* The Team specified by the ID must have the same teamCategory as the customField

### employee
* Allowed Type(s): String or Integer
* Provided value must be valid Employee ID

### address
* Allowed Type(s): String. Must be a JSON Object encoded string (with escaped quotes) e.g. `"{\"key\": \"value\"}"`
* Provided value must be valid Employee ID
* All values must be Strings
* Must provide `address_line_1`, `city`, `state`, `country`
* `country` must be a valid countryCode.
* `country` must match the `workCountryCode` of the employee
* `state` must be a valid stateCode
* `state` must be a valid stateCode for the provided countryCode.

### contact
* Allowed Type(s): String. Must be a JSON Object encoded string (with escaped quotes) e.g. `"{\"key\": \"value\"}"`
* All values in the JSON Object must be Strings.
* Must provide `first_name`, `last_name`, and `relationship`
* must provide at least one of: `email` or `phone`
* `relationship` must be one of:
  * Child
  * Domestic Partner
  * Domestic Partner Child
  * Friend
  * Grandparent
  * Parent
  * Sibling
  * Spouse
  * Other

### date
* Allowed Type(s): String
* Must formatted as YYYY-MM-DD


# Enums
NOTE: Enums are unquoted in user input but quotes in API output.
## CustomFieldTypes
Possible type values for CustomFieldValues

Value | Description
--------- | ---------
TEXT | Displayed as a single line text field. Stored as a String.
LONG_TEXT | Displayed as a multiline text box. Stored as a String.
MULTIPLE_CHOICE | Displayed as a dropdown.  Stored as a String.
MULTIPLE_SELECT | Displayed as a tag field.  Stored as an Array of Strings.
CONFIRMABLE | Displayed as a text field where the user has to enter the value twice.  Stored as a String.
CONTACT | Displayed as group of inputs.  Stored as JSON.
TEAM | Displayed as a dropdown of teams. Stored as a Team ID.
DATE | Displayed as a datepicker.  Stored as a DateTime
EMPLOYEE | Displayed as a dropdown of employees.  Stored as an Employee ID.
ADDRESS | Displayed as group of inputs.  Stored as JSON.

## EmploymentStatus
Possible employment statuses for an employee

Value | Description
--------- | ---------
FULL_TIME | 
PART_TIME | 
TEMPORARY | 
CONTRACTOR | 
INTERN | 
TERMINATED | 

## SignatureRequestStatus
Possible status values for a Signature Request

Value | Description
--------- | ---------
COMPLETED | Document has been successfully signed and verified.
WAITING_FOR_SIGNATURE | Waiting for the employee to sign the document.
BEING_PROCESSED | Document is being processed by our E-Signature Vendor.
WAITING_FOR_COUNTER_SIGNATURE | Document awaiting counter-signer signature.
CANCELED | Signature request has been terminated.
ERROR | Could not be completed due to an error processing the E-Signature.

