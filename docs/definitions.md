### Address

Internal object of a School entity.

|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|_id||true|integer (int64)||
|city||false|string||
|country||false|string||
|geo||true|Geo||
|street||false|string||
|streetNum||false|integer (int32)||
|zipcode||false|string||


### Authentication
|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|_id||true|integer (int64)||
|emails||true|string array||
|name||false|string||
|ownerId||false|integer (int64)||
|password||true|string||
|token||false|string||
|type||true|string||
|username||false|string||


### BankDetails

This will be an internal object of an entity of type School.

|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|_id||true|integer (int64)||
|accountNumber||true|integer (int64)||
|currency||true|string||


### Bundle
|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|_id||true|integer (int64)||
|comment||false|string||
|deleted|Says whether the bundle has been deleted. If true - it is scheduled for permanent deletion.|true|boolean||
|discount|The discount the user gets for this lesson|true|number (double)||
|generatorId||false|integer (int64)||
|lessons||false|integer (int64) array||
|mandatoryFlag||true|boolean||
|name||true|string||
|publicFlag||true|boolean||
|schoolId||true|integer (int64)||


### Feedback
|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|_id||true|integer (int64)||
|fromWhom||true|integer (int64)||
|lessonId||true|integer (int64)||
|role||false|string||
|schoolId||true|integer (int64)||
|toWhom||true|integer (int64)||


### Generator
|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|_id||true|integer (int64)||
|comment||false|string||
|deleted|Says whether the generator has been deleted. If true - it is scheduled for permanent deletion.|true|boolean||
|generatedLessons||false|integer (int64) array||
|lessonsManaged||false|integer (int64) array||
|name||true|string||
|type||true|string||


### Geo

Internal coordinate object used for meeting points.

|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|_id||true|integer (int64)||
|lat||true|number (double)||
|lng||true|number (double)||


### Lesson
|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|_id||true|integer (int64)||
|booked|Whether it is booked or not|true|boolean||
|bookingType|Whether it's booked by one or multiple persons|true|string||
|bundleId|Id of the bundle containing the lesson|false|string||
|clientSource|Skipodium user, manually booked by school, white label etc|true|string||
|comment||false|string||
|date||false|string (date)||
|deleted|Says whether the lesson has been deleted. If true - it is scheduled for permanent deletion.|true|boolean||
|discount|The discount the user gets for this lesson|false|number (double)||
|generatorId||false|integer (int64)||
|hourFrom||false|string (date)||
|hourTo||false|string (date)||
|instructorBonusFlag|Bonus the instructor gets for the lesson|false|boolean||
|instructorId||false|string||
|level||true|string array||
|maxAge||false|integer (int32)||
|maxParticipants||false|integer (int32)||
|meetingPoint||true|Geo||
|minAge||false|integer (int32)||
|minParticipants||false|integer (int32)||
|name||true|string||
|participants|List of ids of users attending this lesson|true|string array||
|prices||false|number (float) array||
|schoolId||true|integer (int64)||
|specialties||false|string array||


### MeetingPoint

Default meeting point for a lesson

|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|Geo||true|Geo||
|Name||true|string||
|_id||true|integer (int64)||


### Message

A generic Message entity, having all possible fields that could appear in any message type. 
Types and type-specific fields:
 - time off request: timesOff, timeOffRepeats
 - lesson request: role, accepted
 - lesson booked/unbooked: lessonId, bookerId, participantId
 - assigned lesson: memberId, assignedInstructorId, lessonId
 - unassigned lesson: memberId, lessonId, formerInstructorId
 - product added/removed/changed: productId, changedFields
 - product order changed: products, oldProducts
 - membership accepted/refused: requestId, memberId
 - membership over/changed: memberId, oldRole

|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|_id||true|string||
|accepted||true|boolean||
|assignedInstructorId||false|string||
|bookerId||false|string||
|changedFields||false|string array||
|datetime||true|string (date)||
|deleted|Says whether the message has been deleted. If true - it is scheduled for permanent deletion.|true|boolean||
|formerInstructorId||false|string||
|fromId||true|string||
|important|Whether it is in the 'important' category.|true|boolean||
|lessonId||false|string||
|memberId||false|string||
|message||false|string||
|oldProducts||false|string array||
|oldRole||false|string||
|participantId||false|string||
|productId||false|string||
|products||false|string array||
|read|Whether it has already been read.|true|boolean||
|requestId||false|string||
|role||true|string||
|timesOff|A list of periods where the instructor will not be available|true|TimeInterval||
|toId||true|string||
|type|Type of message - request, notification etc.|true|string||


### School

Information about a given school

|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|_id||true|integer (int64)||
|address||true|Address||
|bankDetails||true|BankDetails||
|bundles||false|integer (int64) array||
|contacts|A list of phone numbers, emails, or any contact details the school possesses.|false|string array||
|defaultMeetingPoints||true|MeetingPoint array||
|deleted|Says whether the school has been deleted. If true - it is scheduled for permanent deletion.|true|boolean||
|email||true|string||
|employees||true|string array||
|feedbacks||false|Feedback array||
|generators||false|Generator array||
|lessons||false|integer (int64) array||
|logo||true|string||
|messages||false|Message array||
|name||true|string||
|openingHours|School working time (internal object with start and end time).|true|string (date)||
|resort||true|string array||


### TimeInterval

An entity representing a pair of times - starting and ending.

|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|_id||true|string||
|endTime||true|string (date)||
|startTime||true|string (date)||


### TimeOffRepeats
|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|_id||true|string||
|accepted||true|boolean||
|end||true|string (date)||
|frequency||true|integer (int32)||
|start||true|string (date)||


### Transaction

An entity representing a single transaction made by a user or  a school.

|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|_id||true|integer (int64)||
|amount||true|number (double)||
|bonus|Amount of bonus money awarded in case of a special transaction|false|number (double)||
|comment||false|string||
|currency||true|string||
|date||true|string (date)||
|productId|ID of lesson or bundle ordered (or null if it's a refund/referral etc)|false|string||
|schoolId||true|string||
|transactionType||false|string||
|userId||true|string||


### User
|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|_id||true|integer (int64)||
|active|Says whether the user confirmed the registration. Also becomes inactive upon account deletion request.|true|boolean||
|authentications||false|Authentication array||
|deleted|Says whether the user has been deleted. If true - it is scheduled for permanent deletion.|true|boolean||
|email||true|string||
|feedbacksIn||false|Feedback array||
|feedbacksOut||false|Feedback array||
|languages||false|string array||
|lessons||false|string array||
|name||true|string||
|notifications||false|Message array||
|permissions||false|string array||
|phoneNumber||false|string||
|photoURL||false|string||
|privileges|A list of privileges the user has|true|string array||
|resetPasswordToken||false|string||
|schoolId|ids of schools this user is an instructor of|false|string array||
|schools||false|string array||
|specializations||false|string array||
|timesOff|A list of periods where the instructor is unavailable|false|TimeInterval array||
|userType|Type of the user: regular, instructor, director, manager.|true|string||


