## POST /bundle
```
POST /bundle
```

### Description

Adds a new bundle

### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|BodyParameter|body||false|Bundle||


### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|


### Tags

* Lesson

## GET /bundle/{bundleId}
```
GET /bundle/{bundleId}
```

### Description

Gets a bundle by ID

### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|bundleId||true|integer (int32)||


### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|Bundle|
|404|Error 404|No Content|


### Tags

* Lesson

## PUT /bundle/{bundleId}
```
PUT /bundle/{bundleId}
```

### Description

Modifies an existing bundle

### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|bundleId||true|integer (int32)||
|BodyParameter|body||false|Bundle||


### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|


### Tags

* Lesson

## DELETE /bundle/{bundleId}
```
DELETE /bundle/{bundleId}
```

### Description

Deletes a bundle

### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|bundleId||true|integer (int32)||


### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|404|Error 404|No Content|


### Tags

* Lesson

## DELETE /bundle/{bundleId}/lesson
```
DELETE /bundle/{bundleId}/lesson
```

### Description

Removes a lesson from a bundle

### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|bundleId||true|integer (int32)||


### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|404|Error 404|No Content|


### Tags

* Lesson

## POST /bundle/{bundleId}/lesson
```
POST /bundle/{bundleId}/lesson
```

### Description

Adds a new lesson to the bundle

### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|BodyParameter|body||false|Lesson||
|PathParameter|bundleId||true|integer (int32)||


### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|


### Tags

* Lesson

## POST /feedback
```
POST /feedback
```

### Description

Adds new feedback to db

### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|BodyParameter|body||false|Feedback||


### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|Error 400|No Content|


### Tags

* Messages

## POST /generator
```
POST /generator
```

### Description

Creates a new generator

### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|BodyParameter|body||false|Generator||


### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|Error 400|No Content|


### Tags

* Lesson

## GET /generator/{generatorId}
```
GET /generator/{generatorId}
```

### Description

Gets a generator by ID

### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|generatorId||true|integer (int32)||


### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|


### Tags

* Lesson

## PUT /generator/{generatorId}
```
PUT /generator/{generatorId}
```

### Description

Edits an existing generator

### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|BodyParameter|body||false|Generator||
|PathParameter|generatorId||true|integer (int32)||


### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|Error 400|No Content|
|404|Error 404|No Content|
|405|Error 405|No Content|


### Tags

* Lesson

## DELETE /generator/{generatorId}
```
DELETE /generator/{generatorId}
```

### Description

Deletes a generator

### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|generatorId||true|integer (int32)||


### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|404|Error 404|No Content|


### Tags

* Lesson

## GET /lesson
```
GET /lesson
```

### Description

Gets lessons by parameters

### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|QueryParameter|maxPrice||false|string||
|QueryParameter|bookingType||false|string||
|QueryParameter|schoolId||false|string||
|QueryParameter|instructorId||false|string||
|QueryParameter|speciality||false|string||
|QueryParameter|level||false|string||
|QueryParameter|meetingPoint||false|string||
|QueryParameter|dateFrom||false|string||
|QueryParameter|dateTo||false|string||
|QueryParameter|clientSource|Skipodium user, manually booked by school, white label etc|false|string||
|QueryParameter|booked|Whether it's already booked or not|false|string||
|QueryParameter|generatorId||false|string||
|QueryParameter|bundled||false|string||
|QueryParameter|single||false|string||


### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|Lesson|
|404|Error 404|No Content|


### Tags

* Lesson

## POST /lesson
```
POST /lesson
```

### Description

Creates a new lesson

### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|


### Tags

* Lesson

## GET /lesson/{lessonId}
```
GET /lesson/{lessonId}
```

### Description

Gets a lesson by ID

### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|lessonId|ID of the lesson to work with.|true|integer (int32)||


### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|Lesson|
|404|Error 404|No Content|


### Tags

* Lesson

## PUT /lesson/{lessonId}
```
PUT /lesson/{lessonId}
```

### Description

Modifies an existing lesson

### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|lessonId|ID of the lesson to work with.|true|integer (int32)||
|BodyParameter|body||false|Lesson||


### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|Error 400|No Content|
|404|Error 404|No Content|
|405|Error 405|No Content|


### Tags

* Lesson

## DELETE /lesson/{lessonId}
```
DELETE /lesson/{lessonId}
```

### Description

Deletes a lesson by ID

### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|lessonId|ID of the lesson to work with.|true|integer (int32)||


### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|404|Error 404|No Content|


### Tags

* Lesson

## GET /lesson/{lessonId}/assignment
```
GET /lesson/{lessonId}/assignment
```

### Description

Get the assigned instructor

### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|lessonId||true|integer (int32)||


### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|User array|
|404|Error 404|No Content|


### Tags

* Lesson

## PUT /lesson/{lessonId}/assignment/{instructorId}
```
PUT /lesson/{lessonId}/assignment/{instructorId}
```

### Description

Changes the current lesson instructor

### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|lessonId||true|integer (int32)||
|PathParameter|instructorId||true|integer (int32)||
|BodyParameter|body||false|User||
|QueryParameter|id||false|string||


### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|Error 400|No Content|
|404|Error 404|No Content|


### Tags

* Lesson

## PUT /lesson/{lessonId}/participant/{participantId}
```
PUT /lesson/{lessonId}/participant/{participantId}
```

### Description

Removes or adds a participant to a lesson

### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|lessonId||true|integer (int32)||
|PathParameter|participantId||true|integer (int32)||
|BodyParameter|body||false|Lesson||


### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|Error 400|No Content|
|404|Error 404|No Content|
|405|Error 405|No Content|


### Tags

* Lesson

## POST /login
```
POST /login
```

### Description

Stub login method

### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|401|Error 400|No Content|


### Tags

* Default

## POST /logout
```
POST /logout
```

### Description

Stub logout method

### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|


### Tags

* Default

## GET /message
```
GET /message
```

### Description

Gets messages having specific parameters

### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|404|Error 404|No Content|


### Tags

* Messages

## POST /message
```
POST /message
```

### Description

Adds a new message to db

### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|BodyParameter|body||false|Message||


### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|Error 400|No Content|


### Tags

* Messages

## GET /message/{messageId}
```
GET /message/{messageId}
```

### Description

Gets a message by id

### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|messageId||true|integer (int32)||


### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|Message|
|404|Error 404|No Content|


### Tags

* Messages

## DELETE /message/{messageId}
```
DELETE /message/{messageId}
```

### Description

Deletes a message

### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|messageId||true|integer (int32)||


### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|404|Error 404|No Content|


### Tags

* Messages

## POST /school
```
POST /school
```

### Description

Creates a new school

### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|BodyParameter|body||false|School||


### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|Error 400|No Content|


### Tags

* School

## GET /school/{schoolId}
```
GET /school/{schoolId}
```

### Description

Gets a school by ID

### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|schoolId||true|integer (int32)||


### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|School|
|404|Error 404|No Content|


### Tags

* School

## PUT /school/{schoolId}
```
PUT /school/{schoolId}
```

### Description

Modifies an existing school

### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|schoolId||true|integer (int32)||
|BodyParameter|body||false|School||


### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|Error 400|No Content|
|404|Error 404|No Content|
|405|Error 405|No Content|


### Tags

* School

## POST /transaction
```
POST /transaction
```

### Description

Creates a new transaction

### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|BodyParameter|body||false|Transaction||


### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|Error 400|No Content|


### Tags

* Payments

## GET /transaction/summary
```
GET /transaction/summary
```

### Description

If userId is specifiec, returns JSON: {amount: paidCredit, bonus:savedCredit} 
If schoolId, returns JSON:  {amount: earnedCredit, bonus: credit gave away in promotions}
If both, returns JSON:  {amount: credits earned on a given user by the school, bonus: credit awarder for the user by the school}

### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|QueryParameter|userId||false|string||
|QueryParameter|schoolId||false|string||


### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Outputs a JSON object, representation to be defined.|No Content|
|401|Error 401|No Content|
|403|Error 403|No Content|
|404|Error 404|No Content|


### Tags

* Payments

## GET /transaction/{transactionId}
```
GET /transaction/{transactionId}
```

### Description

Gets a transaction by ID

### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|transactionId||true|integer (int32)||


### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|Transaction|
|404|Error 404|No Content|


### Tags

* Payments

## GET /transactions/{schoolId}
```
GET /transactions/{schoolId}
```

### Description

Gets all transactions for a given school

### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|schoolId||true|integer (int32)||


### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|Transaction array|
|404|Error 404|No Content|


### Tags

* Payments

## GET /user
```
GET /user
```

### Description

Gets users according to parameters (will be paged to avoid huge lists).

### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|QueryParameter|startPage|Index of the page to fetch|false|string||
|QueryParameter|pageSize|Size of a page|false|string||
|QueryParameter|type|User type to fetch|false|string||


### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|User array|
|404|Error 404|No Content|


### Tags

* Users

## POST /user
```
POST /user
```

### Description

Creates a new user.

### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|BodyParameter|body||false|User||


### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|Error 400|No Content|


### Tags

* Users

## POST /user/stub
```
POST /user/stub
```

### Description

Creates a new stub user.

### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|BodyParameter|body||false|User||


### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|


### Tags

* Users

## GET /user/{userId}
```
GET /user/{userId}
```

### Description

Gets a user by ID

### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|userId|ID of the user to work with|true|integer (int64)||


### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|User array|
|400|Error 400|No Content|
|404|Error 404|No Content|


### Tags

* Users

## PUT /user/{userId}
```
PUT /user/{userId}
```

### Description

Updates a selected user

### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|userId|ID of the user to work with|true|integer (int64)||
|BodyParameter|body||false|User||


### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|Error 400|No Content|
|404|Error 404|No Content|
|405|Error 405|No Content|


### Tags

* Users

## DELETE /user/{userId}
```
DELETE /user/{userId}
```

### Description

Deletes a user by ID

### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|userId|ID of the user to work with|true|integer (int64)||


### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200|Success|No Content|
|400|Error 400|No Content|
|404|Error 404|No Content|


### Tags

* Users

## GET /user/{userId}/feedbacks
```
GET /user/{userId}/feedbacks
```

### Description

Gets all user feedbacks

### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|userId||true|integer (int32)||


### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200||Feedback array|


### Tags

* Users

## GET /user/{userId}/messages
```
GET /user/{userId}/messages
```

### Description

Gets all user messages.

### Parameters
|Type|Name|Description|Required|Schema|Default|
|----|----|----|----|----|----|
|PathParameter|userId|ID of the user to get the messages for|true|integer (int32)||


### Responses
|HTTP Code|Description|Schema|
|----|----|----|
|200||Message array|


### Tags

* Users

