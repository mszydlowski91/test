## Definitions
### User
|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|_id||true|string||
|active|Says whether the user confirmed the registration. Also becomes inactive upon account deletion request.|true|boolean||
|authentications|A list of available authentication methods configured for the user.|false|Authentication array||
|deleted|Says whether the user has been deleted. If true - it is scheduled for permanent deletion.|true|boolean||
|email|The user's email address.|true|string||
|name|The user's name.|true|string||
|phoneNumber|User's contact number.|false|string||
|photoURL|URL of user's avatar.|false|string||
|resetPasswordToken|A unique, random token dedicated for the specific user view to reset the password.|false|string||
|surname|The user's surname.|true|string||
|refferalToken|The token assigned to a user when he will try to generate referal links|false|string||


### Transaction

An entity representing a single transaction made by a user or  a school.

|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|_id||true|string||
|amount|The amount of money to be transferred from the purchaser to the school.|true|number (double)||
|bonus|Amount of bonus money awarded by the school in case of a special transaction or promotion|false|number (double)||
|comment|A brief description of transaction's purpose.|false|string||
|currency|The currency in which the transaction will be done.|true|string||
|date|A date at which the transaction occurs.|true|string (date)||
|productId|ID of lesson or bundle ordered (or null if it's a refund/referral etc)|false|string||
|schoolId|ID of the school that does the transaction (if it is not manually booked).|false|string||
|transactionType|Type of the transaction: lesson purchase, refund, referral bonus, etc.|true|string||
|userId|ID of the user booking the transaction (if booked manually).|false|string||


### Message

A generic Message entity, having all possible fields that could appear in any message type. <br>
Types and type-specific fields: <br>
 - time off request: timesOff, timeOffRepeats<br>
 - lesson request: role, accepted<br>
 - lesson booked/unbooked: lessonId, bookerId, participantId<br>
 - assigned lesson: memberId, assignedInstructorId, lessonId<br>
 - unassigned lesson: memberId, lessonId, formerInstructorId<br>
 - product added/removed/changed: productId, changedFields<br>
 - membership accepted/refused: requestId, memberId<br>
 - membership over/changed: memberId, oldRole<br>

|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|_id||true|string||
|accepted|Whether the request was accepted.|false|boolean||
|assignedInstructorId|The id of the newly assigned instructor.|false|string||
|bookerId|The id of the person (or school) who booked the lesson for you|false|string||
|changedFields|The names of fields that were changed in the given lesson.|false|string array||
|timestamp|READ ONLY
The time of this message creation|true|string (date)||
|deleted|Says whether the message has been deleted. If true - it is scheduled for permanent deletion.|true|boolean||
|formerInstructorId|The Id of the instructor previously assigned to this lesson.|false|string||
|fromId|Id of the person / school which sent this message|true|string||
|important|Whether it is in the 'important' category.|true|boolean||
|lessonId|The id of the lesson that was changed|false|string||
|memberId||false|string||
|message|The content of the message|true|string||
|oldRole|The previous role of the user who changed|false|string||
|participantId|Person for whom the lesson was booked/unbooked for.|false|string||
|productId|Id of added/removed/changed  lesson / bundle|false|string||
|read|Whether it has already been read.|true|boolean||
|role|The role of the person requesting the lesson|false|string||
|timesOff|A list of periods where the instructor will not be available|false|TimeInterval||
|toId|Id of the user/school that is the receiver of this message.|true|string||
|type|Type of message - request, notification etc.|true|string||


### Participant

The participant of a lesson

|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|userId|The id of the user participating in the lesson.|true|string||
|bookingCost|How much the booker paid for the lesson|true|number (double)||
|bookerId|The person who booked the lesson for the user specified by the userID|true|string||
|dateOfBooking|When was the booking performed|true|string (date)||
|_id||true|string||


### MeetingPoint

Default meeting point for a lesson

|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|geo|Coordinates of the meeting point.|true|Geo||
|name|Name of the meeting point.|true|string||


### Generator
|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|_id||true|integer (int64)||
|comment|A brief description of the generator.|false|string||
|deleted|Says whether the generator has been deleted. If true - it is scheduled for permanent deletion.|true|boolean||
|generatedLessons|A list of lessons generated by this generator.|false|string array||
|name|Name of the generator.|true|string||
|type|Determines whether it is a lesson or a bundle generator.|true|string||
|generatedBundles|A list of bundles generated by this generator.|false|string array||


### TimeInterval

An entity representing a pair of times - starting and ending.

|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|endTime||true|string (date)||
|startTime||true|string (date)||


### Employee

School employee

|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|_id||true|string||
|userId|The  id of the user.|true|string||
|schoolID|The id of the school which this user is an employee of|true|string||
|permissions|What the user is allowed to do in this school.|true|string array||
|timesOff|Time intervals during which the user is unavailable|true|TimeInterval array||
|specialties|Specialties the user can teach.|false|string array||
|languages|The languages this employee can speak|true|string array||


### Authentication

An object describing a user's authentication (facebook, google, regular, etc).

|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|password|User password.|false|string||
|token||false|string||
|type|Authentication type.|true|string||


### Bundle

A group of lessons with a discount if a user will decide to purchase all of them.

|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|_id||true|string||
|comment|A creators comment towards the bundle.|false|string||
|deleted|Says whether the bundle has been deleted. If true - it is scheduled for permanent deletion.|true|boolean||
|discount|The discount the user gets for the lessons in this bundle|false|Discount||
|lessons|A list of lessons belonging to this bundle.|true|string array||
|name|The name of the bundle.|true|string||
|publicFlag|A flag determining whether the bundle is public or private.|true|boolean||
|schoolId|ID of the school at which the bundle's lessons will occur.|true|string||


### Address

Internal object of a School entity.

|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|city||false|string||
|country||false|string||
|street||false|string||
|streetNum||false|integer (int32)||
|zipcode||false|string||
|state||false|string||


### EntityType

Helper object defining an entity type

|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|_id||true|string||
|Entity|Selects an entity type: school, employee, user|true|string||
|SchoolType|If the field is not null, the entity is of type School|false|string||


### Feedback

Entity representing a feedback (user to instructor, instructor to user or user to school)

|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|_id||true|string||
|fromWhom|ID of the sender.|true|string||
|lessonId|ID of the lesson the feedback refers to.|true|string||
|schoolId|ID of the school the lesson was carried out at.|true|string||
|toWhom|ID of the receiver.|true|string||
|message|The content of the feedback|false|string||
|rating|The rating of the feedback|true|number (double)||
|relation|Defines what kind of entity sends and receives the feedback|true|string||


### Discount

Object representing fields needed for different types of discounts.

|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|staticAmount|If the discount to a bundle is a static number value|false|number (double)||
|percentageOfFullCost|If the discount to a bundle is a percentage value of the overal cost|false|number (double)||


### Geo

Internal coordinate object used for meeting points.

|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|lat||true|number (double)||
|lng||true|number (double)||


### Lesson
|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|_id||true|string||
|booked|Whether it is booked or not|true|boolean||
|bookingType|Whether it's booked by one or multiple persons|true|string||
|bundleId|Id of the bundle containing the lesson|false|string||
|clientSource|Skipodium user, manually booked by school, white label etc|true|string||
|comment|A brief comment about the lesson.|false|string||
|deleted|Says whether the lesson has been deleted. If true - it is scheduled for permanent deletion.|true|boolean||
|discount|The discount the user gets for this lesson|false|number (double)||
|hourTo|Ending hour of the lesson|false|string (date)||
|instructorBonusFlag|Bonus the instructor gets for the lesson|false|boolean||
|instructorId|ID of the instructor running the lesson.|true|string||
|level|The skill levels involved in this lesson.|false|string||
|maxAge|Maximum age for this lesson.|false|integer (int32)||
|maxParticipants|Maximum number of participants.|false|integer (int32)||
|meetingPoint|A meeting point for this lesson.|true|Geo||
|minAge|Minimum age for this lesson.|false|integer (int32)||
|minParticipants|Minimum number of participants for this lesson.|false|integer (int32)||
|name|Name of the lesson.|true|string||
|participants|List of participants  attending this lesson|true|Participant array||
|prices|A list of price thresholds, depending on the time of booking|false|number (double) array||
|schoolId|ID of the school at which the lesson was carried out.|true|string||
|specialties|The specialities covered by the lesson|false|string||
|previousInstructorId|Id of the previous instructor|false|string||


### School

Information about a given school

|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|_id||true|integer (int64)||
|address|School address|true|Address||
|bankDetails|School banking information.|true|BankDetails||
|contacts|A list of phone numbers, emails, or any contact details the school possesses.|false|string array||
|defaultMeetingPoints|A list of established meeting points for instructors and students.|true|MeetingPoint array||
|deleted|Says whether the school has been deleted. If true - it is scheduled for permanent deletion.|true|boolean||
|email|Main email address which can be used to contact the school|true|string||
|logo|An url  with the school logo file|true|string||
|messages|An inbox containing all messages sent to the school|true|string array||
|name|The name of the school|true|string||
|openingHours|School working time (internal object with start and end time).|true|string (date)||
|resort|A list of all resorts of given school - a minimum of one is required|true|string array||


### BankDetails

This will be an internal object of an entity of type School.

|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|accountNumber|Bank account number.|true|integer (int64)||
|currency|Currency the account number is in.|true|string||
|_id||true|string||


