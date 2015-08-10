## Paths
### POST /bundle
```
POST /bundle
```

#### Description

Adds a new bundle

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|BodyParameter|body||false|Bundle||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|Invalid data provided.|No Content|
|401|Permission not granted.|No Content|


#### Tags

* Bundles

### GET /bundle/{bundleId}
```
GET /bundle/{bundleId}
```

#### Description

Gets a bundle by ID

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|bundleId||true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|Bundle|
|401|Permission not granted.|No Content|
|404|The element with the given ID does not exist.|No Content|


#### Tags

* Bundles

### PUT /bundle/{bundleId}
```
PUT /bundle/{bundleId}
```

#### Description

Modifies an existing bundle

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|bundleId||true|string||
|BodyParameter|body||false|Bundle||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|The submitted request is malformed.|No Content|
|401|Permission not granted.|No Content|
|404|The element with the given ID does not exist.|No Content|


#### Tags

* Bundles

### DELETE /bundle/{bundleId}
```
DELETE /bundle/{bundleId}
```

#### Description

Deletes a bundle

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|bundleId||true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|401|Permission not granted.|No Content|
|404|The element with the given ID does not exist.|No Content|


#### Tags

* Bundles

### PUT /bundle/{bundleId}/addLesson
```
PUT /bundle/{bundleId}/addLesson
```

#### Description

Adds a lesson to the bundle

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|bundleId||true|string||
|BodyParameter|body||false|Lesson||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|The submitted request is malformed.|No Content|
|401|Permission not granted.|No Content|
|404|The requested resource does not exist.|No Content|


#### Tags

* Bundles

### PUT /bundle/{bundleId}/deleteLesson
```
PUT /bundle/{bundleId}/deleteLesson
```

#### Description

Removes a lesson from bundle.

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|BodyParameter|body||false|Lesson||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|The submitted request is malformed.|No Content|
|401|Permission not granted.|No Content|
|404|The requested resource does not exist.|No Content|


#### Tags

* Bundles

### GET /bundle/{bundleId}/lessons
```
GET /bundle/{bundleId}/lessons
```

#### Description

Gets all lessons of a bundle

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|bundleId||true|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|Lesson array|
|401|Permission not granted.|No Content|
|404|The requested resource does not exist.|No Content|


#### Tags

* Bundles

### GET /feedback
```
GET /feedback
```

#### Description

Get a feedback by parameters

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|QueryParameter|schoolId||false|null string array||
|QueryParameter|lessonId||false|null string array||
|QueryParameter|senderUserId||false|null string array||
|QueryParameter|receiverUserId||false|null string array||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|Feedback array|
|400|The submitted request is malformed.|No Content|
|401|Permission not granted.|No Content|
|404|The element with the given ID does not exist.|No Content|


#### Tags

* Messages

### POST /feedback
```
POST /feedback
```

#### Description

Adds new feedback to db

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|BodyParameter|body||false|Feedback||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|The submitted request is malformed.|No Content|
|401|Permission not granted.|No Content|


#### Tags

* Messages

### POST /generator
```
POST /generator
```

#### Description

Creates a new generator

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|BodyParameter|body||false|Generator||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|The submitted request is malformed.|No Content|
|401|Permission not granted.|No Content|


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
|401|Permission not granted.|No Content|
|404|The element with the given ID does not exist.|No Content|


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
|BodyParameter|body||false|Generator||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|Error 400|No Content|
|401|Permission not granted.|No Content|
|404|Error 404|No Content|


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
|401|Permission not granted.|No Content|
|404|The element with the given ID does not exist.|No Content|


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
|QueryParameter|maxPrice||false|null string array||
|QueryParameter|bookingType||false|null string array||
|QueryParameter|schoolId||false|null string array||
|QueryParameter|instructorId||false|null string array||
|QueryParameter|speciality||false|null string array||
|QueryParameter|level||false|null string array||
|QueryParameter|meetingPoint||false|null string array||
|QueryParameter|dateFrom||false|null string array||
|QueryParameter|dateTo||false|null string array||
|QueryParameter|clientSource|Skipodium user, manually booked by school, white label etc|false|null string array||
|QueryParameter|booked|Whether it's already booked or not|false|null string array||
|QueryParameter|generatorId||false|null string array||
|QueryParameter|bundled||false|null string array||
|QueryParameter|single||false|null string array||
|QueryParameter|criteria|Other additional sorting criteria|false|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|Lesson array|
|400|The submitted request is malformed.|No Content|
|401|Permission not granted.|No Content|
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
|BodyParameter|body||false|Lesson||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|The submitted request is malformed.|No Content|
|401|Permission not granted.|No Content|


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
|401|You do not have permission to perform this operation|No Content|
|404|No lesson with the specified id was found|No Content|


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
|BodyParameter|body||false|Lesson||
|QueryParameter|id|The id of the lesson to be modified - this parameter IS mandatory.|false|null string array||
|QueryParameter|bookingType|What kind of booking type should this lesson have.|false|null string array||
|QueryParameter|bundleId|The id of the bundle this lesson should be part of. Empty  for removing from a bundle.|false|null string array||
|QueryParameter|comment|Modify the comment of a lesson|false|null string array||
|QueryParameter|discount|Modify the discount applicable for this lesson (if present must be >= 0)|false|null string array||
|QueryParameter|generatorId|The id of the generator owning this lesson, if a lesson is edited without specifying this parameter than it will be set to null.|false|null string array||
|QueryParameter|hourFrom|Starting hour of this lesson, must be less than hourTo|false|null string array||
|QueryParameter|hourTo|Ending hour of this lesson, must be more than hourFrom|false|null string array||
|QueryParameter|instructorBonusFlag|Does this lesson provide a bonus for the instructor|false|null string array||
|QueryParameter|instructorId|The id of the new instructor (null for unassigned). If you only wish to modify the instructor assignment use /lesson{lessonId}/assignment|false|null string array||
|QueryParameter|level|Modifies the level of this lesson.|false|null string array||
|QueryParameter|maxAge|The max age for participants|false|null string array||
|QueryParameter|maxParticipants|The maximum amount of participants|false|null string array||
|QueryParameter|meetingPoint|The meeting point of this lesson|false|null string array||
|QueryParameter|minAge|Minimal age for this lesson|false|null string array||
|QueryParameter|minParticipants|Minimal number of participants for the lesson to take place|false|null string array||
|QueryParameter|name|The name of the lesson|false|null string array||
|QueryParameter|participants|list of id's of users participating in this lesson. If this is the only value you would like to modify please use /lesson{lessonId}/participant/|false|null string array||
|QueryParameter|prices|Modifies the prices array for this lesson|false|null string array||
|QueryParameter|specialties|Modifies the speciality available in this lesson|false|null string array||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|The submitted request is malformed.|No Content|
|401|Permission not granted.|No Content|
|404|The element with the given ID does not exist.|No Content|


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
|401|Permission not granted.|No Content|
|404|The element with the given ID does not exist.|No Content|


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
|401|Permission not granted.|No Content|
|404|The element with the given ID does not exist.|No Content|


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
|BodyParameter|body||false|Lesson||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|The instructor has been changed.|No Content|
|400|The submitted request is malformed.|No Content|
|401|Permission not granted.|No Content|
|404|The element with the given ID does not exist.|No Content|


#### Tags

* Lessons

### PUT /lesson/{lessonId}/participant
```
PUT /lesson/{lessonId}/participant
```

#### Description

Remove or add a participant to a lesson

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|lessonId||true|string||
|BodyParameter|body||false|Lesson||
|QueryParameter|participants|A list id containing all of the participants, in order to remove a participant submit a list without his id (just other participants), if you would like to add a participant submit a list containing his id (and all other participants)|false|null string array||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|The submitted request is malformed.|No Content|
|401|Permission not granted.|No Content|
|404|The element with the given ID does not exist.|No Content|


#### Tags

* Lessons

### PUT /lesson/{lessonId}/participant/{participantId}
```
PUT /lesson/{lessonId}/participant/{participantId}
```

#### Description

Modifies a lesson participant

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|participantId||true|string||
|PathParameter|lessonId||true|string||
|BodyParameter|body||false|User||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|The participant has been modified.|No Content|
|400|The submitted request is malformed.|No Content|
|401|Permission not granted.|No Content|
|404|The element with the given ID does not exist.|No Content|


#### Tags

* Lessons

### POST /login
```
POST /login
```

#### Description

Login

#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|Wrong combination of email/password.|No Content|
|401|The user has been deleted or is inactive.|No Content|
|404|No user with a given email found.|No Content|


#### Tags

* Default

### POST /logout
```
POST /logout
```

#### Description

Logout

#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|


#### Tags

* Default

### GET /message
```
GET /message
```

#### Description

Gets messages having specific parameters

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|QueryParameter|toId|Get recieved messages of user - THIS IS A TEST METHOD|false|null string array||
|QueryParameter|startDate|fetch messages from date range|false|null string array||
|QueryParameter|type|fetch messages of given type|false|null string array||
|QueryParameter|unread|fetch only messages that are unread|false|null string array||
|QueryParameter|fromId|Fetch all messages sent from given person/school|false|null string array||
|QueryParameter|endDate|Fetch messages up to given date|false|null string array||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|Message array|
|400|The submitted request is malformed.|No Content|
|401|You do not have sufficient access to perform this operation|No Content|
|404|There is no data identifiable by the given parameters.|No Content|


#### Tags

* Messages

### POST /message
```
POST /message
```

#### Description

Adds a new message to db

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|BodyParameter|body||false|Message||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|The submitted request is malformed.|No Content|
|401|Permission not granted.|No Content|
|403|Invalid data provided.|No Content|


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
|401|Permission not granted.|No Content|
|404|The element with the given ID does not exist.|No Content|


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
|401|Permission not granted.|No Content|
|404|The element with the given ID does not exist.|No Content|


#### Tags

* Messages

### GET /resetPassword
```
GET /resetPassword
```

#### Description

Resets a user's password

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|BodyParameter|body||false|User||
|QueryParameter|email||false|null string array||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|The password was reset and a confirmation email is sent.|No Content|
|401|Permission not granted.|No Content|
|404|The email is not in the database.|No Content|


#### Tags

* Default

### POST /school
```
POST /school
```

#### Description

Creates a new school

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|BodyParameter|body||false|School||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|The submitted request is malformed.|No Content|
|401|Permission not granted.|No Content|


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
|401|Permission not granted.|No Content|
|404|The element with the given ID does not exist.|No Content|


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
|BodyParameter|body||false|School||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|The submitted request is malformed.|No Content|
|401|Permission not granted.|No Content|
|404|The element with the given ID does not exist.|No Content|


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
|401|Permission not granted.|No Content|
|404|The requested resource does not exist.|No Content|


#### Tags

* Schools

### GET /school/{schoolId}/transactions
```
GET /school/{schoolId}/transactions
```

#### Description

Gets all transactions for a given school

#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|Transaction array|
|401|Permission not granted.|No Content|
|404|The requested resource does not exist.|No Content|


#### Tags

* Schools

### POST /transaction
```
POST /transaction
```

#### Description

Creates a new transaction

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|BodyParameter|body||false|Transaction||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|The submitted request is malformed.|No Content|
|401|Permission not granted.|No Content|


#### Tags

* Payments

### GET /transaction/summary
```
GET /transaction/summary
```

#### Description

If userId is specifiec, returns JSON: {amount: paidCredit, bonus:savedCredit} 
If schoolId, returns JSON:  {amount: earnedCredit, bonus: credit gave away in promotions}
If both, returns JSON:  {amount: credits earned on a given user by the school, bonus: credit awarder for the user by the school}

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|QueryParameter|userId||false|null string array||
|QueryParameter|schoolId||false|null string array||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Outputs a JSON object, representation to be defined.|No Content|
|400|The submitted request is malformed.|No Content|
|401|Permission not granted.|No Content|
|404|The element with the given ID does not exist.|No Content|


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
|401|Permission not granted.|No Content|
|404|The element with the given ID does not exist.|No Content|


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
|QueryParameter|type|User type to fetch|false|null string array||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|User array|
|400|The submitted request is malformed.|No Content|
|401|Permission not granted.|No Content|
|404|The element with the given ID does not exist.|No Content|


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
|BodyParameter|body||false|User||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|The submitted request is malformed.|No Content|
|401|Permission not granted.|No Content|


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
|BodyParameter|body||false|User||
|QueryParameter|email|The email of the stub user - This parameter IS mandatory|false|null string array||
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
|401|Permission not granted.|No Content|
|404|The element with the given ID does not exist.|No Content|


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
|BodyParameter|body||false|User||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|The submitted request is malformed.|No Content|
|401|Permission not granted.|No Content|
|404|The element with the given ID does not exist.|No Content|


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
|400|The submitted request is malformed.|No Content|
|401|Permission not granted.|No Content|
|404|The element with the given ID does not exist.|No Content|


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
|200||Feedback array|
|401|Permission not granted.|No Content|
|404|The element with the given ID does not exist.|No Content|


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
|200||Message array|
|401|Permission not granted.|No Content|
|404|The element with the given ID does not exist.|No Content|


#### Tags

* Users

