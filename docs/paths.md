## Paths
### POST /auth/facebook
```
POST /auth/facebook
```

#### Description

Facebook login method.

#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|


#### Tags

* Default

### POST /auth/google
```
POST /auth/google
```

#### Description

Google login method.

#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|


#### Tags

* Default

### POST /auth/twitter
```
POST /auth/twitter
```

#### Description

Twitterlogin method.

#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|


#### Tags

* Default

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
|QueryParameter|lessonId|ID of the lesson to add|false|string||


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
|PathParameter|bundleId||true|string||
|BodyParameter|body||false|Lesson||
|QueryParameter|lessonId|ID of the lesson to remove|false|string||


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

### POST /bundle/{bundleId}/purchase
```
POST /bundle/{bundleId}/purchase
```

#### Description

Purchase a new bundle.

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|bundleId||true|string||
|QueryParameter|guestIds|A list of IDs of users for which the bundle is purchased.|false|null string array||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success.|No Content|
|400|The submitted request is malformed.|No Content|
|401|Permission not granted.|No Content|


#### Tags

* Lessons

### POST /contact
```
POST /contact
```

#### Description

Sends a message to Skipodium support

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|QueryParameter|from|Email address of the sender.|false|string||
|QueryParameter|topic|Message topic.|false|string||
|QueryParameter|message|Message content.|false|string||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|Invalid data provided.|No Content|
|401|Permission not granted.|No Content|


#### Tags

* Default

### POST /employee
```
POST /employee
```

#### Description

Adds a new employee

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|BodyParameter|body||false|Employee||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|The submitted request is malformed.|No Content|
|401|Permission not granted.|No Content|


#### Tags

* Users

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

* Users

### PUT /employee/{employeeId}
```
PUT /employee/{employeeId}
```

#### Description

Modifies an existing employee

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|employeeId||true|string||
|BodyParameter|body||false|Employee||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|The submitted request is malformed.|No Content|
|401|Permission not granted.|No Content|
|404|The requested resource does not exist.|No Content|


#### Tags

* Users

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
|401|Permission not granted.|No Content|
|404|The requested resource does not exist.|No Content|


#### Tags

* Users

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
|QueryParameter|isBundle|Determines whether the generator will be a bundle generator.|false|string||


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

### PUT /generator/{generatorId}/bundleTemplate
```
PUT /generator/{generatorId}/bundleTemplate
```

#### Description

Modifies the bundle template of the generator

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|generatorId||true|string||
|BodyParameter|body||false|BundleTemplate||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|The submitted request is malformed.|No Content|
|401|Permission not granted.|No Content|
|404|The requested resource does not exist.|No Content|


#### Consumes

* application/json

#### Tags

* Generators

### PUT /generator/{generatorId}/lessonTemplate
```
PUT /generator/{generatorId}/lessonTemplate
```

#### Description

Modifies the bundle template of the generator

#### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|generatorId||true|string||
|BodyParameter|body||false|LessonTemplate||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|The submitted request is malformed.|No Content|
|401|Permission not granted.|No Content|
|404|The requested resource does not exist.|No Content|


#### Consumes

* application/json

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
|QueryParameter|age||false|null string array||
|QueryParameter|numParticipants||false|null string array||
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
|QueryParameter|startPage|Starting index of the whole list to fetch|false|string||
|QueryParameter|endPage|Ending index of the whole list to fetch|false|string||


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

### GET /lesson/search
```
GET /lesson/search
```

#### Description

Gets a list of instructors having lessons with specific parameters

#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|Employee array|
|401|Permission not granted.|No Content|
|404|The requested resource does not exist.|No Content|


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


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|The instructor has been changed.|No Content|
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
|401|Permission not granted.|No Content|
|404|The element with the given ID does not exist.|No Content|


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
|QueryParameter|id|A list of IDs of users the lesson was bought for.|false|null string array||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|The instructor has been changed.|No Content|
|400|The submitted request is malformed.|No Content|
|401|Permission not granted.|No Content|


#### Tags

* Lessons

### POST /login
```
POST /login
```

#### Description

Login method

#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|401|The user has been deleted or invalid password.|No Content|
|404|No user with a given email found.|No Content|


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
|401|Permission not granted.|No Content|
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
|401|Permission not granted.|No Content|
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
|401|Permission not granted.|No Content|
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
|401|Permission not granted.|No Content|
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


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|Transaction array|
|401|Permission not granted.|No Content|
|404|The requested resource does not exist.|No Content|


#### Tags

* Schools

### POST /signup
```
POST /signup
```

#### Description

Signup method

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
|BodyParameter|body||false|Transaction||


#### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|The submitted request is malformed.|No Content|
|401|Permission not granted.|No Content|


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
|200|Success|Feedback array|
|401|Permission not granted.|No Content|
|404|The element with the given ID does not exist.|No Content|


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
|401|Permission not granted.|No Content|
|404|The element with the given ID does not exist.|No Content|


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
|200|Success|Message array|
|401|Permission not granted.|No Content|
|404|The element with the given ID does not exist.|No Content|


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
|401|Permission not granted.|No Content|
|404|The requested resource does not exist.|No Content|


#### Tags

* Users

