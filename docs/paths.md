## Paths
### GET /
```
GET /
```

#### Description

Home address. Returns current session data.

#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|No Content|
|401|Unauthorized|No Content|


#### Produces

* application/json

#### Tags

* Default

### GET /auth/facebook
```
GET /auth/facebook
```

#### Description

Facebook login method.

#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|No Content|


#### Tags

* Default

### GET /auth/google
```
GET /auth/google
```

#### Description

Google login method.

#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|No Content|


#### Tags

* Default

### GET /auth/twitter
```
GET /auth/twitter
```

#### Description

Twitterlogin method.

#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|No Content|


#### Tags

* Default

### GET /clientToken
```
GET /clientToken
```

#### Description

Gets the Braintree client token

#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|No Content|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Payments

### POST /contact
```
POST /contact
```

#### Description

Sends a message to Skipodium support

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|FormDataParameter|email|Email address of the sender.|true|string||
|FormDataParameter|newsletter|Newsletter flag.|true|boolean||
|FormDataParameter|subject|Message topic.|true|string||
|FormDataParameter|message|Message content.|true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|No Content|
|400|Bad Request|No Content|


#### Consumes

* application/x-www-form-urlencoded

#### Tags

* Default

### GET /employee
```
GET /employee
```

#### Description

Gets employees by params

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|QueryParameter|language|Language|false|string||
|QueryParameter|specialtyType|Specialty - see MOCKUP API|false|string||
|QueryParameter|expertise|Expertise - see MOCKUP API|false|string||
|QueryParameter|level|Level - see MOCKUP API|false|string||
|QueryParameter|permissions|Permission - see MOCKUP API|false|string||
|QueryParameter|schoolId|School id|false|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|No Content|
|400|Bad Request|No Content|


#### Tags

* Employees

### POST /employee
```
POST /employee
```

#### Description

Adds a new employee

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|FormDataParameter|name|Name of the employee user (if created from scratch with user).|false|string||
|FormDataParameter|surname|Surame of the employee user (if created from scratch with user).|false|string||
|FormDataParameter|email|Email of the employee user (if created from scratch with user).|false|string||
|FormDataParameter|userId|ID of the user the employee will be assigned to (if created for an existing user).|false|string||
|FormDataParameter|schoolId|ID of the school of the new employee.|true|string||
|FormDataParameter|permissions|JSON array - see MOCKUP API|true|string||
|FormDataParameter|salary|Employee salary.|true|string||
|FormDataParameter|comment|Comment about the employee.|false|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|No Content|
|400|Bad Request|No Content|
|403|Forbidden|No Content|


#### Consumes

* application/x-www-form-urlencoded

#### Tags

* Employees

### GET /employee/{employeeId}
```
GET /employee/{employeeId}
```

#### Description

Gets an employee by ID

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|employeeId||true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|No Content|
|404|Not Found|No Content|


#### Tags

* Employees

### PUT /employee/{employeeId}
```
PUT /employee/{employeeId}
```

#### Description

Modifies an existing employee.

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|employeeId||true|string||
|FormDataParameter|permissions|A list of employee permissions. JSON array - see MOCKUP API.|false|string||
|FormDataParameter|specialties|A list of specialties, JSON array of objects - see MOCKUP API.|false|string||
|FormDataParameter|timesOff|A list of employee times off, JSON array of objects - see MOCKUP API.|false|string||
|FormDataParameter|schedule|Employee time off schedule, JSON object - see MOCKUP API.|false|string||
|FormDataParameter|salary|Employee salary.|false|string||
|FormDataParameter|comment|Comment about the employee.|false|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|No Content|
|400|Bad Request|No Content|
|401|Unauthorized|No Content|
|403|Forbidden|No Content|
|404|Not Found|No Content|


#### Consumes

* application/x-www-form-urlencoded

#### Tags

* Employees

### DELETE /employee/{employeeId}
```
DELETE /employee/{employeeId}
```

#### Description

Schedules an employee for deletion.

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|employeeId||true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|No Content|
|401|Unauthorized|No Content|
|403|Forbidden|No Content|
|404|Not Found|No Content|


#### Tags

* Employees

### PUT /employee/{employeeId}/employment/{accept}
```
PUT /employee/{employeeId}/employment/{accept}
```

#### Description

Manages accept employment request.

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|employeeId||true|string||
|PathParameter|accept||true|boolean||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Employees

### GET /employee/{employeeId}/stats
```
GET /employee/{employeeId}/stats
```

#### Description

Gets the stats of the employee. Returns a custom JSON.

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|employeeId||true|string||
|QueryParameter|timeFrom|Date from which to search: 2015-11-11T16:11:32.714Z|false|string||
|QueryParameter|timeTo|Date till which to search: 2016-11-11T16:11:32.714Z|false|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|Bad Request|No Content|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Employees

### PUT /employee/{employeeId}/timeOff
```
PUT /employee/{employeeId}/timeOff
```

#### Description

Adds timeOffs for the employee.

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|employeeId||true|string||
|FormDataParameter|startDate|Start date of the generated time offs, format: YYYY-MM-DD|true|string||
|FormDataParameter|endDate|End date of the generated time offs, format: YYYY-MM-DD|true|string||
|FormDataParameter|startTime|Start time of the generated time offs, format: HH:MM:SS|true|string||
|FormDataParameter|endTime|End time of the generated time offs, format: HH:MM:SS|true|string||
|FormDataParameter|repeatMode|Repeat pattern enum - weekly, daily, or weekday.|true|string||
|FormDataParameter|repeatEvery|If weekly or daily mode - says that it repeats every N days/weeks.|false|string||
|FormDataParameter|repeatOn|Selects weekdays to repeat on - weekly mode only (JSON array of weekday indexes)|false|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|Bad Request|No Content|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Employees

### GET /employee/{employeeId}/times
```
GET /employee/{employeeId}/times
```

#### Description

Gets the times off of the employee.

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|employeeId||true|string||
|QueryParameter|timeFrom|Lower time bound: 2015-11-11T16:11:32.714Z|false|string||
|QueryParameter|timeTo|Upper time bound: 2016-11-11T16:11:32.714Z|false|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|TimeInterval array|
|400|Bad Request|No Content|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Employees

### POST /feedback
```
POST /feedback
```

#### Description

Creates a new feedback

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|FormDataParameter|fromEntity||true|string||
|FormDataParameter|fromId||true|string||
|FormDataParameter|toEntity||true|string||
|FormDataParameter|toId||true|string||
|FormDataParameter|rating||true|string||
|FormDataParameter|lessonId||true|string||
|FormDataParameter|schoolId||true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|No Content|
|400|Bad Request|No Content|
|401|Unauthorized|No Content|


#### Tags

* Feedbacks

### POST /generator
```
POST /generator
```

#### Description

Creates a new generator

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|FormDataParameter|name|Name of the new generator.|true|string||
|FormDataParameter|priority|Generator priority (number).|true|string||
|FormDataParameter|generatorType|Generator type (lessonGenerator or bundleGenerator).|true|string||
|FormDataParameter|lessonTemplateId|ID of the lesson template used by the generator.|true|string||
|FormDataParameter|schoolId|ID of the school that owns the generator.|true|string||
|FormDataParameter|comment|Comment about the generator.|false|string||
|FormDataParameter|instructorIds|Array of instructor IDs for this generator - see MOCKUP - API.|true|string||
|FormDataParameter|schedules|Generator schedules - see MOCKUP - API.|true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|No Content|
|400|Bad Request|No Content|
|401|Unauthorized|No Content|
|403|Forbidden|No Content|


#### Tags

* Generators

### GET /generator/{generatorId}
```
GET /generator/{generatorId}
```

#### Description

Gets a generator by ID

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|generatorId||true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|Generator|
|401|Unauthorized|No Content|
|403|Forbidden|No Content|
|404|Not Found|No Content|


#### Tags

* Generators

### PUT /generator/{generatorId}
```
PUT /generator/{generatorId}
```

#### Description

Edits an existing generator

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|generatorId||true|string||
|FormDataParameter|name|Name of the new generator.|false|string||
|FormDataParameter|priority|Generator priority.|false|string||
|FormDataParameter|generatorType|Generator type (lessonGenerator or bundleGenerator).|false|string||
|FormDataParameter|lessonTemplateId|ID of the lesson template used by the generator.|false|string||
|FormDataParameter|schoolId|ID of the school that owns the generator.|false|string||
|FormDataParameter|comment|Comment about the generator.|false|string||
|FormDataParameter|instructorIds|Array of instructor IDs for this generator- see MOCKUP - API.|false|string||
|FormDataParameter|schedules|Generator schedules - see MOCKUP - API.|false|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|No Content|
|400|Bad Request|No Content|
|401|Unauthorized|No Content|
|403|Forbidden|No Content|
|404|Not Found|No Content|


#### Tags

* Generators

### DELETE /generator/{generatorId}
```
DELETE /generator/{generatorId}
```

#### Description

Deletes a generator

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|generatorId||true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|No Content|
|401|Unauthorized|No Content|
|403|Forbidden|No Content|
|404|Not Found|No Content|


#### Tags

* Generators

### GET /lesson
```
GET /lesson
```

#### Description

Gets lessons by parameters

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|QueryParameter|timeFrom|Date from which to search: 2015-11-11T16:11:32.714Z.|false|string||
|QueryParameter|timeTo|Date till which to search: 2015-11-11T16:11:32.714Z.|false|string||
|QueryParameter|numParticipants|Target number of participants.|false|string||
|QueryParameter|specialty|Target specialty - see MOCKUP - API.|false|string||
|QueryParameter|expertise|Expertise - see MOCKUP - API.|false|string||
|QueryParameter|level|Level - see MOCKUP - API.|false|string||
|QueryParameter|minPrice|Minimum price.|false|string||
|QueryParameter|maxPrice|Maximum price.|false|string||
|QueryParameter|age|Target age.|false|string||
|QueryParameter|instructorId|Instructor id|false|string||
|QueryParameter|instructorBonusFlag|Instructor bonus flag|false|boolean||
|QueryParameter|schoolId|School id|false|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|Lesson array|
|400|Bad Request|No Content|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Lessons

### POST /lesson
```
POST /lesson
```

#### Description

Creates a new lesson

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|FormDataParameter|timeFrom|Lesson start time: 2015-11-11T16:11:32.714Z|true|string||
|FormDataParameter|timeTo|Lesson end time: 2015-11-11T16:11:32.714Z.|true|string||
|FormDataParameter|minParticipants|Min number of participants.|false|string||
|FormDataParameter|maxParticipants|Max number of participants.|false|string||
|FormDataParameter|specialties|Lesson specialties - see MOCKUP - API.|false|string||
|FormDataParameter|prices|Lesson prices for consecutive participant numbers: [10, 100]|true|string||
|FormDataParameter|minAge|Min age.|false|string||
|FormDataParameter|maxAge|Max age.|false|string||
|FormDataParameter|instructorId|Instructor id|false|string||
|FormDataParameter|instructorBonusFlag|Instructor bonus flag|true|boolean||
|FormDataParameter|schoolId|School id|true|string||
|FormDataParameter|name|Lesson name.|true|string||
|FormDataParameter|clientSource|user/school/whiteLabel|true|string||
|FormDataParameter|comment|Comment about the lesson.|false|string||
|FormDataParameter|generatorId|ID of the generator that created the lesson.|false|string||
|FormDataParameter|geoName|Name of the meeting point.|true|string||
|FormDataParameter|geoLat|Latitude of the meeting point.|true|string||
|FormDataParameter|geoLng|Longitude of the meeting point.|true|string||
|FormDataParameter|private|Says whether the lesson is private.|false|boolean||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|No Content|
|400|Bad Request|No Content|
|401|Unauthorized|No Content|
|403|Forbidden|No Content|


#### Tags

* Lessons

### GET /lesson/{lessonId}
```
GET /lesson/{lessonId}
```

#### Description

Gets a lesson by ID

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|lessonId|ID of the lesson to work with.|true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|Lesson|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Lessons

### PUT /lesson/{lessonId}
```
PUT /lesson/{lessonId}
```

#### Description

Modifies an existing lesson

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|lessonId|ID of the lesson to work with.|true|string||
|FormDataParameter|timeFrom|New time from: 2015-11-11T16:11:32.714Z|false|string||
|FormDataParameter|timeTo|New time to: 2015-11-11T16:11:32.714Z|false|string||
|FormDataParameter|minParticipants|Min number of participants.|false|string||
|FormDataParameter|maxParticipants|Max number of participants.|false|string||
|FormDataParameter|specialties|Lesson specialties - see MOCKUP - API.|false|string||
|FormDataParameter|prices|Lesson prices for consecutive participant numbers - see MOCKUP-API.|false|string||
|FormDataParameter|minAge|Min age.|false|string||
|FormDataParameter|maxAge|Max age.|false|string||
|FormDataParameter|instructorId|Instructor id|false|string||
|FormDataParameter|instructorBonusFlag|Instructor bonus flag|false|boolean||
|FormDataParameter|schoolId|School id|false|string||
|FormDataParameter|name|Lesson name.|false|string||
|FormDataParameter|clientSource|user/school/whiteLabel|false|string||
|FormDataParameter|comment|Comment about the lesson.|false|string||
|FormDataParameter|generatorId|ID of the generator that created the lesson.|false|string||
|FormDataParameter|meetingPoint|Meeting point JSON - see MOCKUP-API.|false|string||
|FormDataParameter|private|Says whether the lesson is private.|false|boolean||
|FormDataParameter|participants|Lesson participant IDs - see MOCKUP-API.|false|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|No Content|
|400|Bad Request|No Content|
|401|Unauthorized|No Content|
|403|Forbidden|No Content|
|404|Not Found|No Content|


#### Tags

* Lessons

### DELETE /lesson/{lessonId}
```
DELETE /lesson/{lessonId}
```

#### Description

Deletes a lesson by ID

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|lessonId|ID of the lesson to work with.|true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|No Content|
|401|Unauthorized|No Content|
|403|Forbidden|No Content|
|404|Not Found|No Content|


#### Tags

* Lessons

### GET /lesson/{lessonId}/assignment
```
GET /lesson/{lessonId}/assignment
```

#### Description

Get the assigned instructor

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|lessonId||true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|User|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Lessons

### PUT /lesson/{lessonId}/assignment/{instructorId}
```
PUT /lesson/{lessonId}/assignment/{instructorId}
```

#### Description

Change the instructor assigned to the lesson

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|instructorId||true|string||
|PathParameter|lessonId||true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|The instructor has been changed.|No Content|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Lessons

### POST /lesson/{lessonId}/purchaseManual
```
POST /lesson/{lessonId}/purchaseManual
```

#### Description

Manually purchase a new lesson by a school manager or instructor.

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|lessonId||true|string||
|FormDataParameter|clientId|A list of IDs of users the lesson was bought for (JSON array).|true|string||
|FormDataParameter|amount|The amount of money the purchasing person paid.|true|number||
|FormDataParameter|paymentMethod|The selected payment method (bankTransfer,creditCard, debitCard or cash).|false|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success.|No Content|
|400|Bad Request|No Content|
|401|Unauthorized|No Content|


#### Tags

* Lessons

### PUT /lesson/{lessonId}/unbook/{userId}
```
PUT /lesson/{lessonId}/unbook/{userId}
```

#### Description

Unbooks a specific lesson for a user.

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|lessonId||true|string||
|PathParameter|userId||true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|No Content|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Lessons

### PUT /lesson/{lessonId}/unbookManual/{userId}
```
PUT /lesson/{lessonId}/unbookManual/{userId}
```

#### Description

Unbooks a manually booked lesson for a user.

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|lessonId||true|string||
|PathParameter|userId||true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|No Content|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Lessons

### GET /lessonInstructors
```
GET /lessonInstructors
```

#### Description

Returns a list of entries: {imageUrl, firstName, surname, lowestPrice, specialties}

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|QueryParameter|resortId|ID of the resort to look in|false|string||
|QueryParameter|timeFrom|Date from which to search: 2015-11-11T16:11:32.714Z|false|string||
|QueryParameter|timeTo|Date till which to search: 2016-11-11T16:11:32.714Z|false|string||
|QueryParameter|numParticipants|Target number of participants.|false|string||
|QueryParameter|specialtyType|Target specialty, see MOCKUP - API|false|string||
|QueryParameter|expertises|Expertises, see MOCKUP - API|false|string||
|QueryParameter|level|Level, see MOCKUP - API|false|string||
|QueryParameter|minPrice|Minimum price.|false|string||
|QueryParameter|maxPrice|Maximum price.|false|string||
|QueryParameter|language|Language.|false|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|No Content|
|400|Bad Request|No Content|


#### Tags

* Lessons

### POST /lessonTemplate
```
POST /lessonTemplate
```

#### Description

Add a new lesson template.

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|FormDataParameter|comment|Comment about the lesson template.|false|string||
|FormDataParameter|instructorBonusFlag|Says whether produced lessons will have an instructor bonus.|true|boolean||
|FormDataParameter|maxAge|Maximum age for the produced lessons.|false|string||
|FormDataParameter|minAge|Minimum age for the produced lessons.|false|string||
|FormDataParameter|minParticipants|Minimum participant count for the produced lessons.|false|string||
|FormDataParameter|maxParticipants|Maximum participant count for the produced lessons.|false|string||
|FormDataParameter|name|Name of the lesson template.|true|string||
|FormDataParameter|lessonName|Name of the lessons produced.|true|string||
|FormDataParameter|meetingPoint|Meeting point JSON (see MOCKUP-API).|true|string||
|FormDataParameter|specialties|Produced lessons' specialties (JSON object array, see MOCKUP-API).|false|string||
|FormDataParameter|prices|Produced lessons' prices for consecutive participant numbers: [10, 100]|true|string||
|FormDataParameter|schoolId|Produced lessons' school id|true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success.|No Content|
|400|Bad Request|No Content|
|401|Unauthorized|No Content|


#### Tags

* Lessons

### GET /lessonTemplate/{lessonTemplateId}
```
GET /lessonTemplate/{lessonTemplateId}
```

#### Description

Get a lesson template by ID.

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|lessonTemplateId||true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success.|No Content|
|400|Bad Request|No Content|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Lessons

### PUT /lessonTemplate/{lessonTemplateId}
```
PUT /lessonTemplate/{lessonTemplateId}
```

#### Description

Modify a lesson template by ID.

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|lessonTemplateId||true|string||
|FormDataParameter|comment|Comment about the lesson template.|false|string||
|FormDataParameter|instructorBonusFlag|Says whether produced lessons will have an instructor bonus.|false|boolean||
|FormDataParameter|maxAge|Maximum age for the produced lessons.|false|string||
|FormDataParameter|minAge|Minimum age for the produced lessons.|false|string||
|FormDataParameter|minParticipants|Minimum participant count for the produced lessons.|false|string||
|FormDataParameter|maxParticipants|Maximum participant count for the produced lessons.|false|string||
|FormDataParameter|name|Name of the lesson template.|false|string||
|FormDataParameter|lessonName|Name of the lessons produced.|false|string||
|FormDataParameter|meetingPoint|Meeting point JSON (see MOCKUP-API).|false|string||
|FormDataParameter|specialties|Produced lessons' specialties (see MOCKUP-API).|false|string||
|FormDataParameter|prices|Produced lessons' prices for consecutive participant numbers: [10, 100]|false|string||
|FormDataParameter|schoolId|Produced lessons' school id|false|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success.|No Content|
|400|Bad Request|No Content|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Lessons

### DELETE /lessonTemplate/{lessonTemplateId}
```
DELETE /lessonTemplate/{lessonTemplateId}
```

#### Description

Delete a lesson template by ID.

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|lessonTemplateId||true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success.|No Content|
|400|Bad Request|No Content|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Lessons

### POST /login
```
POST /login
```

#### Description

Login method

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|FormDataParameter|email||true|string||
|FormDataParameter|password||true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|No Content|
|401|Unauthorized|No Content|


#### Consumes

* application/x-www-form-urlencoded

#### Tags

* Default

### GET /logout
```
GET /logout
```

#### Description

Logout

#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|No Content|
|401|Unauthorized|No Content|


#### Tags

* Default

### POST /message
```
POST /message
```

#### Description

Send a message

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|FormDataParameter|fromEntity||true|string||
|FormDataParameter|fromId||true|string||
|FormDataParameter|toEntity||true|string||
|FormDataParameter|toId||true|string||
|FormDataParameter|message||true|string||
|FormDataParameter|important||true|boolean||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|No Content|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Messages

### GET /message/{messageId}
```
GET /message/{messageId}
```

#### Description

Gets a message by id

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|messageId||true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|Message|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Messages

### DELETE /message/{messageId}
```
DELETE /message/{messageId}
```

#### Description

Deletes a message

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|messageId||true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|No Content|
|400|Bad Request|No Content|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Messages

### PUT /message/{messageId}/markAsRead
```
PUT /message/{messageId}/markAsRead
```

#### Description

Marks the message as read

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|messageId||true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|No Content|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Messages

### POST /purchase
```
POST /purchase
```

#### Description

Purchase a new lesson.

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|FormDataParameter|lessons|A list of lessons to buy with their respective participants.|true|string||
|FormDataParameter|participants|A list of participants with their respective lesson IDs.|true|string||
|FormDataParameter|paymentNonce|Braintree payment method nonce received from the Braintree server.|false|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success.|No Content|
|400|Bad Request|No Content|
|401|Unauthorized|No Content|


#### Tags

* Lessons

### GET /resort
```
GET /resort
```

#### Description

Gets resorts by params.

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|QueryParameter|name|Resort name.|false|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|Resort array|
|401|Unauthorized|No Content|


#### Tags

* Resorts

### POST /resort
```
POST /resort
```

#### Description

Adds a new resort.

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|FormDataParameter|name|Resort name - must be unique|true|string||
|FormDataParameter|photoURL||false|string||
|FormDataParameter|lat||false|number||
|FormDataParameter|lng||false|number||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|Resort array|
|401|Unauthorized|No Content|


#### Tags

* Resorts

### GET /resort/{id}
```
GET /resort/{id}
```

#### Description

Gets resort by id.

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|id||true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|Resort|


#### Tags

* Resorts

### PUT /resort/{id}
```
PUT /resort/{id}
```

#### Description

Modifies resort by id.

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|id||true|string||
|FormDataParameter|name||false|string||
|FormDataParameter|photoURL||false|string||
|FormDataParameter|lat||false|number||
|FormDataParameter|lng||false|number||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|No Content|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Resorts

### POST /school
```
POST /school
```

#### Description

Creates a new school

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|FormDataParameter|email||true|string||
|FormDataParameter|name||true|string||
|FormDataParameter|siteUrl||false|string||
|FormDataParameter|country||false|string||
|FormDataParameter|resort|Resort name|false|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|No Content|
|400|Bad Request|No Content|
|401|Unauthorized|No Content|


#### Tags

* Schools

### GET /school/{schoolId}
```
GET /school/{schoolId}
```

#### Description

Gets a school by ID

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|schoolId||true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|School|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Schools

### PUT /school/{schoolId}
```
PUT /school/{schoolId}
```

#### Description

Modifies an existing school

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|schoolId||true|string||
|FormDataParameter|addressCity||false|string||
|FormDataParameter|addressCountry||false|string||
|FormDataParameter|addressStreet||false|string||
|FormDataParameter|addressStreetNum||false|string||
|FormDataParameter|addressZipCode||false|string||
|FormDataParameter|addressState||false|string||
|FormDataParameter|email||false|string||
|FormDataParameter|logo|This tool does not support uploading files.|false|string||
|FormDataParameter|name||false|string||
|FormDataParameter|royaltyPercent||false|string||
|FormDataParameter|resortId||false|string||
|FormDataParameter|openingHours|See MOCKUP-API|false|string||
|FormDataParameter|defaultMeetingPoints|See MOCKUP-API|false|string||
|FormDataParameter|contactsFacebook||false|string||
|FormDataParameter|contactsTwitter||false|string||
|FormDataParameter|contactsGoogleplus||false|string||
|FormDataParameter|contactsPhone||false|string||
|FormDataParameter|contactsMail||false|string||
|FormDataParameter|contactsSiteUrl||false|string||
|FormDataParameter|manuallySetRating||false|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|No Content|
|400|Bad Request|No Content|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Schools

### PUT /school/{schoolId}/accept/{accept}
```
PUT /school/{schoolId}/accept/{accept}
```

#### Description

Sends an activation request to skipodium, can only be sent by a school director, upon success an email will be sent to skipodium managment to manually activate the school

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|schoolId||true|string||
|PathParameter|accept||true|boolean||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|No Content|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Schools

### PUT /school/{schoolId}/activate
```
PUT /school/{schoolId}/activate
```

#### Description

Sends an activation request to skipodium, can only be sent by a school director, upon success an email will be sent to skipodium managment to manually activate the school

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|schoolId||true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|No Content|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Schools

### GET /school/{schoolId}/bookedClients
```
GET /school/{schoolId}/bookedClients
```

#### Description

Gets a list of school clients

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|schoolId||true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|User array|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Schools

### GET /school/{schoolId}/clientList
```
GET /school/{schoolId}/clientList
```

#### Description

Gets the list of all school clients.

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|schoolId||true|string||
|QueryParameter|lessonId|ID of the lesson to fetch the clients for|false|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|User array|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Schools

### GET /school/{schoolId}/clientStats/{clientId}
```
GET /school/{schoolId}/clientStats/{clientId}
```

#### Description

Gets the stats for a user at school. Returns a custom JSON.

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|schoolId||true|string||
|PathParameter|clientId||true|string||
|QueryParameter|timeFrom|Date from which to search. Format: 2015-11-01T10:30:00.000Z|false|string||
|QueryParameter|timeTo|Date till which to search. Format: 2015-11-01T10:30:00.000Z|false|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success.|No Content|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Schools

### GET /school/{schoolId}/employees
```
GET /school/{schoolId}/employees
```

#### Description

Gets all school employees

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|schoolId||true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|Employee array|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Schools

### GET /school/{schoolId}/feedbacks
```
GET /school/{schoolId}/feedbacks
```

#### Description

Gets all school feedbacks

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|schoolId||true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|Feedback array|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Schools

### GET /school/{schoolId}/generators
```
GET /school/{schoolId}/generators
```

#### Description

Gets all generators of a school

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|schoolId||true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|Generator array|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Schools

### GET /school/{schoolId}/messages
```
GET /school/{schoolId}/messages
```

#### Description

Gets all school messages

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|schoolId||true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|Message array|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Schools

### GET /school/{schoolId}/transactions
```
GET /school/{schoolId}/transactions
```

#### Description

Gets all transactions for a given school, for a given user ID

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|schoolId||true|string||
|QueryParameter|userId||false|string||
|QueryParameter|lessonId||false|string||
|QueryParameter|timeFrom|Format: 2015-11-01T10:30:00.000Z|false|string||
|QueryParameter|timeTo|Format: 2015-11-01T10:30:00.000Z|false|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|Transaction array|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Schools

### POST /signup
```
POST /signup
```

#### Description

Signup method

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|FormDataParameter|email||true|string||
|FormDataParameter|password||true|string||
|FormDataParameter|name||true|string||
|FormDataParameter|surname||true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|No Content|
|400|Bad Request|No Content|
|401|Unauthorized|No Content|


#### Tags

* Default

### GET /transaction/{transactionId}
```
GET /transaction/{transactionId}
```

#### Description

Gets a transaction by ID

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|transactionId||true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|Transaction|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Payments

### GET /user
```
GET /user
```

#### Description

Gets users according to parameters.

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|QueryParameter|name||false|string||
|QueryParameter|surname||false|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|User array|
|400|Bad Request|No Content|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Users

### POST /user/stub
```
POST /user/stub
```

#### Description

Creates a new stub user.

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|FormDataParameter|email|The email of the stub user|true|string||
|FormDataParameter|name|The name of the stub user|true|string||
|FormDataParameter|surname|The lastName of the stub user|true|string||
|FormDataParameter|schoolId|The ID of the school creating the stub user|true|string||
|FormDataParameter|birthDate|E.g. 1991-04-04T10:00:00.000Z|false|string||
|FormDataParameter|address|The address of the stub user|false|string||
|FormDataParameter|nationality|The nationality of the stub user|false|string||
|FormDataParameter|vatCode|The VAT ID of the stub user|false|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|No Content|
|400|Bad Request|No Content|
|401|Unauthorized|No Content|


#### Tags

* Users

### GET /user/{email}/resetPassword
```
GET /user/{email}/resetPassword
```

#### Description

Resets a user's password

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|email||true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|The password was reset and a confirmation email is sent.|No Content|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Users

### POST /user/{token}/newPassword
```
POST /user/{token}/newPassword
```

#### Description

Resets a user's password

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|token||true|string||
|FormDataParameter|newpassword||true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|The password was reset and a confirmation email is sent.|No Content|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Users

### PUT /user/{token}/verify
```
PUT /user/{token}/verify
```

#### Description

Verifies user using the provided token

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|token||true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|User verified|No Content|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Users

### GET /user/{userId}
```
GET /user/{userId}
```

#### Description

Gets a user by ID

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|userId|ID of the user to work with|true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|User array|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Users

### PUT /user/{userId}
```
PUT /user/{userId}
```

#### Description

Updates a selected user

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|userId|ID of the user to work with|true|string||
|FormDataParameter|name||false|string||
|FormDataParameter|email||false|string||
|FormDataParameter|surname||false|string||
|FormDataParameter|phoneNumber||false|string||
|FormDataParameter|languages|See MOCKUP-API|false|string||
|FormDataParameter|photoURL||false|string||
|FormDataParameter|birthDate|E.g: 1991-04-04T10:00:00.000Z|false|string||
|FormDataParameter|address||false|string||
|FormDataParameter|nationality||false|string||
|FormDataParameter|vatCode||false|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|No Content|
|400|Bad Request|No Content|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Users

### DELETE /user/{userId}
```
DELETE /user/{userId}
```

#### Description

Deletes a user by ID

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|userId|ID of the user to work with|true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|No Content|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Users

### GET /user/{userId}/employment
```
GET /user/{userId}/employment
```

#### Description

Gets all user employments. Returns an array of pairs {employee, school}.

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|userId||true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|Bad Request|No Content|
|404|Not Found|No Content|


#### Tags

* Users

### GET /user/{userId}/feedbacks
```
GET /user/{userId}/feedbacks
```

#### Description

Gets all user feedbacks

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|userId||true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|Feedback array|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Users

### GET /user/{userId}/feedbacks/random
```
GET /user/{userId}/feedbacks/random
```

#### Description

Gets a number of random user feedbacks

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|userId||true|string||
|QueryParameter|count|Number of feedbacks to fetch.|false|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|Feedback array|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Users

### GET /user/{userId}/lessons
```
GET /user/{userId}/lessons
```

#### Description

Gets all user lessons

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|userId||true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|Lesson array|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Users

### GET /user/{userId}/messages
```
GET /user/{userId}/messages
```

#### Description

Gets all user messages.

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|userId|ID of the user to get the messages for|true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|Message array|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Users

### GET /user/{userId}/stats/{schoolId}
```
GET /user/{userId}/stats/{schoolId}
```

#### Description

Gets the user stats. Returns a custom JSON.

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|userId||true|string||
|PathParameter|schoolId||true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success.|No Content|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Users

### GET /user/{userId}/transactions
```
GET /user/{userId}/transactions
```

#### Description

Gets all user transactions, for a given school

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|userId||true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|OK|Transaction array|
|401|Unauthorized|No Content|
|404|Not Found|No Content|


#### Tags

* Users

