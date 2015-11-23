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
|200|Success|No Content|
|401|You are not allowed to perform this operation.|No Content|


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
|200|Success|No Content|


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
|200|Success|No Content|


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
|200|Success|No Content|


#### Tags

* Default

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
|200|Success|No Content|
|400|The submitted request is malformed.|No Content|
|401|You are not allowed to perform this operation.|No Content|


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
|QueryParameter|specialty|Specialty|false|string||
|QueryParameter|permissions|Permission|false|string||
|QueryParameter|expertise|Expertise|false|string||
|QueryParameter|schoolId|School id|false|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|The submitted request is malformed.|No Content|


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
|FormDataParameter|permissions|A list of employee permissions. JSON array: |true|string||
|FormDataParameter|specialties|A list of employee specialties, JSON array of objects (see examples).|false|string||
|FormDataParameter|timesOff|A list of employee times off, JSON array of objects (see example).|false|string||
|FormDataParameter|schedule|Employee time off schedule, JSON object (see example).|false|string||
|FormDataParameter|salary|Employee salary.|true|string||
|FormDataParameter|comment|Comment about the employee.|false|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|The submitted request is malformed.|No Content|


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
|200|Sucess|Employee|
|400|The submitted request was malformed.|No Content|
|404|The requested resource does not exist.|No Content|


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
|FormDataParameter|permissions|A list of employee permissions. JSON array: |false|string||
|FormDataParameter|specialties|A list of employee specialties, JSON array of objects (see examples).|false|string||
|FormDataParameter|timesOff|A list of employee times off, JSON array of objects (see example).|false|string||
|FormDataParameter|schedule|Employee time off schedule, JSON object (see example).|false|string||
|FormDataParameter|salary|Employee salary.|false|string||
|FormDataParameter|comment|Comment about the employee.|false|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|The submitted request is malformed.|No Content|
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


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
|200|Success|No Content|
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


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


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Sucess|No Content|
|400|The submitted request was malformed.|No Content|
|404|The requested resource does not exist.|No Content|


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
|QueryParameter|date|Month to get the times off for.|true|string (date)||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Sucess|TimeInterval array|
|400|The submitted request was malformed.|No Content|
|404|The requested resource does not exist.|No Content|


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
|200|Success|No Content|
|400|The submitted request is malformed.|No Content|
|401|You are not allowed to perform this operation.|No Content|


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
|FormDataParameter|priority|Generator priority.|true|string||
|FormDataParameter|generatorType|Generator type (lessonGenerator or bundleGenerator).|true|string||
|FormDataParameter|lessonTemplateId|ID of the lesson template used by the generator.|true|string||
|FormDataParameter|schoolId|ID of the school that owns the generator.|true|string||
|FormDataParameter|comment|Comment about the generator.|false|string||
|FormDataParameter|instructorIds|Array of instructor IDs for this generator.|true|string||
|FormDataParameter|schedule|Generator schedule object.|true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|The submitted request is malformed.|No Content|
|401|You are not allowed to perform this operation.|No Content|


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
|200|Success|Generator|
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


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
|PathParameter|generatorId||false|string||
|FormDataParameter|name|Name of the new generator.|false|string||
|FormDataParameter|priority|Generator priority.|false|string||
|FormDataParameter|generatorType|Generator type (lessonGenerator or bundleGenerator).|false|string||
|FormDataParameter|lessonTemplateId|ID of the lesson template used by the generator.|false|string||
|FormDataParameter|schoolId|ID of the school that owns the generator.|false|string||
|FormDataParameter|comment|Comment about the generator.|false|string||
|FormDataParameter|instructorIds|Array of instructor IDs for this generator.|false|string||
|FormDataParameter|schedule|Generator schedule object.|false|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|The submitted request is malformed.|No Content|
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


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
|200|Success|No Content|
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


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
|QueryParameter|timeFrom|Date from which to search.|false|string||
|QueryParameter|timeTo|Date till which to search.|false|string||
|QueryParameter|numParticipants|Target number of participants.|false|string||
|QueryParameter|specialty|Target specialty.|false|string||
|QueryParameter|minPrice|Minimum price. Needs numParticipants & maxPrice|false|string||
|QueryParameter|maxPrice|Maximum price. Needs numParticipants & minPrice|false|string||
|QueryParameter|expertise|Expertises (can be multiple, separate them by a comma).|false|string||
|QueryParameter|age|Target age.|false|string||
|QueryParameter|level||false|string||
|QueryParameter|instructorId|Instructor id|false|string||
|QueryParameter|instructorBonusFlag|Instructor bonus flag|false|boolean||
|QueryParameter|schoolId|School id|false|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|Lesson array|
|400|The submitted request is malformed.|No Content|
|404|No lesson with given matching the provided parameters was found.|No Content|


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
|FormDataParameter|timeFrom|Date from which to search.|true|string||
|FormDataParameter|timeTo|Date till which to search.|true|string||
|FormDataParameter|minParticipants|Min number of participants.|false|string||
|FormDataParameter|maxParticipants|Max number of participants.|false|string||
|FormDataParameter|specialties|Lesson specialties.|false|string||
|FormDataParameter|prices|Lesson prices for consecutive participant numbers.|true|string||
|FormDataParameter|minAge|Min age.|false|string||
|FormDataParameter|maxAge|Max age.|false|string||
|FormDataParameter|instructorId|Instructor id|false|string||
|FormDataParameter|instructorBonusFlag|Instructor bonus flag|true|boolean||
|FormDataParameter|schoolId|School id|true|string||
|FormDataParameter|name|Lesson name.|true|string||
|FormDataParameter|clientSource|user/school/whiteLabel|true|string||
|FormDataParameter|comment|Comment about the lesson.|false|string||
|FormDataParameter|generatorId|ID of the generator that created the lesson.|false|string||
|FormDataParameter|geoName|Name of the meeting point.|false|string||
|FormDataParameter|geoLat|Latitude of the meeting point.|false|string||
|FormDataParameter|geoLng|Longitude of the meeting point.|false|string||
|FormDataParameter|private|Says whether the lesson is private.|false|boolean||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|The submitted request is malformed.|No Content|
|401|You are not allowed to perform this operation.|No Content|


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
|200|Success|Lesson|
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


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
|PathParameter|lessonId|ID of the lesson to work with.|false|string||
|FormDataParameter|timeFrom|Date from which to search.|false|string||
|FormDataParameter|timeTo|Date till which to search.|false|string||
|FormDataParameter|minParticipants|Min number of participants.|false|string||
|FormDataParameter|maxParticipants|Max number of participants.|false|string||
|FormDataParameter|specialties|Lesson specialties.|false|string||
|FormDataParameter|prices|Lesson prices for consecutive participant numbers.|false|string||
|FormDataParameter|minAge|Min age.|false|string||
|FormDataParameter|maxAge|Max age.|false|string||
|FormDataParameter|instructorId|Instructor id|false|string||
|FormDataParameter|instructorBonusFlag|Instructor bonus flag|false|boolean||
|FormDataParameter|schoolId|School id|false|string||
|FormDataParameter|name|Lesson name.|false|string||
|FormDataParameter|clientSource|user/school/whiteLabel|false|string||
|FormDataParameter|comment|Comment about the lesson.|false|string||
|FormDataParameter|generatorId|ID of the generator that created the lesson.|false|string||
|FormDataParameter|meetingPoint|Meeting point JSON.|false|string||
|FormDataParameter|private|Says whether the lesson is private.|false|boolean||
|FormDataParameter|participants|Lesson participants.|false|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|The submitted request is malformed.|No Content|
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


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
|200|Success|No Content|
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


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
|200|Success|User|
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


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
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


#### Tags

* Lessons

### POST /lesson/{lessonId}/purchase
```
POST /lesson/{lessonId}/purchase
```

#### Description

Purchase a new lesson.

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|lessonId||true|string||
|FormDataParameter|guestIds|A list of IDs of users the lesson was bought for (JSON array).|false|string||
|FormDataParameter|number|Credit card number.|true|string||
|FormDataParameter|cvc|Credit card CVC number.|true|string||
|FormDataParameter|exp_month|Expiration month of the credit card.|true|string||
|FormDataParameter|exp_year|Expiration year of the credit card.|true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success.|No Content|
|400|The submitted request is malformed.|No Content|
|401|You are not allowed to perform this operation.|No Content|


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
|FormDataParameter|guestIds|A list of IDs of users the lesson was bought for (JSON array).|true|string||
|FormDataParameter|amount|The amount of money the purchasing person paid.|true|number||
|FormDataParameter|comment|The amount of money the purchasing person paid.|false|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success.|No Content|
|400|The submitted request is malformed.|No Content|
|401|You are not allowed to perform this operation.|No Content|


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
|200|Success|No Content|
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


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
|QueryParameter|resort|Resort|false|string||
|QueryParameter|timeFrom|Date from which to search.|false|string||
|QueryParameter|timeTo|Date till which to search.|false|string||
|QueryParameter|numParticipants|Target number of participants.|false|string||
|QueryParameter|specialty|Target specialty.|false|string||
|QueryParameter|minPrice|Minimum price.|false|string||
|QueryParameter|maxPrice|Maximum price.|false|string||
|QueryParameter|language|Language.|false|string||
|QueryParameter|expertise|Expertises (can be multiple, separate them by a comma).|false|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|The submitted request was malformed.|No Content|
|404|The requested resource does not exist.|No Content|


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
|FormDataParameter|meetingPoint|Meeting point JSON (see example, like in POST /lesson).|true|string||
|FormDataParameter|specialties|Produced lessons' specialties (JSON object array, see POST /lesson example).|false|string||
|FormDataParameter|prices|Produced lessons' prices for consecutive participant numbers (JSON array, see POST /lesson example)|true|string||
|FormDataParameter|schoolId|Produced lessons' school id|true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success.|No Content|
|400|The submitted request is malformed.|No Content|
|401|You are not allowed to perform this operation.|No Content|


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
|400|The submitted request is malformed.|No Content|
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


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
|FormDataParameter|meetingPoint|Meeting point JSON (see example, like in POST /lesson).|false|string||
|FormDataParameter|specialties|Produced lessons' specialties (JSON object array, see POST /lesson example).|false|string||
|FormDataParameter|prices|Produced lessons' prices for consecutive participant numbers (JSON array, see POST /lesson example)|false|string||
|FormDataParameter|schoolId|Produced lessons' school id|false|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success.|No Content|
|400|The submitted request is malformed.|No Content|
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


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
|400|The submitted request is malformed.|No Content|
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


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
|200|Success|No Content|
|401|The user has been deleted or invalid password.|No Content|
|404|No user with a given email found.|No Content|


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
|200|Success|No Content|


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
|200|Success|No Content|
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


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
|200|Success|Message|
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


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
|200|Success|No Content|
|400|The submitted request is malformed.|No Content|
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


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
|200|Success|No Content|
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


#### Tags

* Messages

### POST /school
```
POST /school
```

#### Description

Creates a new school

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|FormDataParameter|user||true|string||
|FormDataParameter|userName||true|string||
|FormDataParameter|userName||true|string||
|FormDataParameter|userName||true|string||
|FormDataParameter|userName||true|string||
|FormDataParameter|userName||true|string||
|FormDataParameter|userName||true|string||
|FormDataParameter|userName||true|string||
|FormDataParameter|userName||true|string||
|FormDataParameter|userName||true|string||
|FormDataParameter|userName||true|string||
|FormDataParameter|userName||true|string||
|FormDataParameter|userName||true|string||
|FormDataParameter|userName||true|string||
|FormDataParameter|userName||true|string||
|FormDataParameter|userName||true|string||
|FormDataParameter|userName||true|string||
|FormDataParameter|userName||true|string||
|FormDataParameter|userName||true|string||
|FormDataParameter|userName||true|string||
|FormDataParameter|userName||true|string||
|FormDataParameter|userName||true|string||
|FormDataParameter|userName||true|string||
|FormDataParameter|userName||true|string||
|FormDataParameter|userName||true|string||
|FormDataParameter|userName||true|string||
|FormDataParameter|userName||true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|The submitted request is malformed.|No Content|
|401|You are not allowed to perform this operation.|No Content|


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
|200|Success|School|
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


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
|BodyParameter|body||true|School||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|The submitted request is malformed.|No Content|
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


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
|200|Success|No Content|
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


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
|200|Success|User array|
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


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


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|User array|
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


#### Tags

* Schools

### GET /school/{schoolId}/clientStats/{clientId}
```
GET /school/{schoolId}/clientStats/{clientId}
```

#### Description

Gets the school stats for a user. Returns a custom JSON.

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|schoolId||true|string||
|PathParameter|clientId||true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success.|No Content|
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


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
|200|Success|Employee array|
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


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
|200|Success|Feedback array|
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


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
|200|Success|Generator array|
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


#### Tags

* Schools

### GET /school/{schoolId}/lessonTemplates
```
GET /school/{schoolId}/lessonTemplates
```

#### Description

Gets all school lesson templates

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|schoolId||true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|LessonTemplate array|
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


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
|200|Success|Message array|
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


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


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|Transaction array|
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


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
|200|Success|No Content|
|401|The user has been deleted or invalid password.|No Content|


#### Tags

* Default

### POST /transaction
```
POST /transaction
```

#### Description

Creates a new transaction

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|BodyParameter|body||true|Transaction||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|The submitted request is malformed.|No Content|
|401|You are not allowed to perform this operation.|No Content|


#### Tags

* Payments

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
|200|Success|Transaction|
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


#### Tags

* Payments

### GET /user
```
GET /user
```

#### Description

Gets users according to parameters (will be paged to avoid huge lists).

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|QueryParameter|startPage|Index of the page to fetch|false|null string array||
|QueryParameter|pageSize|Size of a page|false|null string array||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|User array|
|400|The submitted request is malformed.|No Content|
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


#### Tags

* Users

### POST /user
```
POST /user
```

#### Description

Creates a new user.

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|BodyParameter|body||true|User||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|The submitted request is malformed.|No Content|
|401|You are not allowed to perform this operation.|No Content|


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
|QueryParameter|email|The email of the stub user - This parameter IS mandatory|true|null string array||
|QueryParameter|firstName|The name of the stub user - This parameter is NOT mandatory|false|null string array||
|QueryParameter|lastName|The lastName of the stub user - This parameter is NOT mandatory|false|null string array||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|The submitted request is malformed.|No Content|
|401|You do not have sufficient access to perform this operation|No Content|
|405|Method not allowed.|No Content|


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
|BodyParameter|body||true|User||
|QueryParameter|email||false|null string array||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|The password was reset and a confirmation email is sent.|No Content|
|401|You are not allowed to perform this operation.|No Content|
|404|The email is not in the database.|No Content|


#### Tags

* Users

### GET /user/{token}/newPassword
```
GET /user/{token}/newPassword
```

#### Description

Resets a user's password

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|BodyParameter|body||true|User||
|QueryParameter|email||false|null string array||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|The password was reset and a confirmation email is sent.|No Content|
|401|You are not allowed to perform this operation.|No Content|
|404|The email is not in the database.|No Content|


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
|200|Success|User array|
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


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
|BodyParameter|body||true|User||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|The submitted request is malformed.|No Content|
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


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
|200|Success|No Content|
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


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
|200|Sucess|No Content|
|400|The submitted request was malformed.|No Content|
|404|The requested resource does not exist.|No Content|


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
|200|Success|Feedback array|
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


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
|QueryParameter|amount|Number of feedbacks to fetch.|false|null string array||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|Feedback array|
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


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
|200|Success|Lesson array|
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


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
|200|Success|Message array|
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


#### Tags

* Users

### GET /user/{userId}/stats
```
GET /user/{userId}/stats
```

#### Description

Gets the user stats. Returns a custom JSON.

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|userId||true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success.|No Content|
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


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
|QueryParameter|schoolId||false|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|Transaction array|
|401|You are not allowed to perform this operation.|No Content|
|404|The requested resource does not exist.|No Content|


#### Tags

* Users

