## Definitions
### User
|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|_id||true|string||
|active|Says whether the user confirmed the registration. Also becomes inactive upon account deletion request.|true|boolean||
|authentications|A list of available authentication methods (objects) configured for the user.|false|string array||
|createdAt|Time the user has been created.|true|string (date)||
|updatedAt|Time the user has been updated.|true|string (date)||
|deleted|Says whether the user has been deleted. If true - it is scheduled for permanent deletion.|true|boolean||
|email|The user's email address.|true|string||
|languages|The languages this user can speak|true|string array||
|name|The user's name.|true|string||
|phoneNumber|User's contact number.|false|string||
|photoURL|URL of user's avatar.|false|string||
|resetPasswordToken|A unique, random token dedicated for the specific user view to reset the password.|false|string||
|surname|The user's surname.|true|string||
|refferalToken|The token assigned to a user when he will try to generate referal links|false|string||


### LessonTemplate
|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|_id||true|string||
|name|Template name.|true|string||
|groupFlag|Determines whether it is an individual or a group lesson.|true|boolean||
|instructorId|Instructor assigned to generated lessons.|true|string||
|minParticipants|Minimum amount of participants (for group lessons).|false|integer (int32)||
|maxParticipants|Maximum amount of participants (for a group lesson).|false|integer (int32)||
|prices|A list of prices for subsequent participants.|true|number (double) array||
|minAge|Minimum age of the lessons (for group lessons).|false|integer (int32)||
|maxAge|Maximum age of the lessons (for group lessons).|false|integer (int32)||
|specialties|Specialty of the generated lessons|false|Specialty array||
|skillLevels|Required skill level for the generated lessons.|false|string array||
|instructorBonusFlag|Decides whether an instructor will receive bonus for the generated lessons.|false|boolean||
|comment|A brief description of the template.|false|string||


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
|productId|Entity defining the product that has been ordered.|true|EntityID||
|schoolId|ID of the school that does the transaction (if it is not manually booked).|false|string||
|transactionType|Type of the transaction: lesson purchase, refund, referral bonus, etc.|true|string||
|userId|ID of the user for whom the lesson was booked|true|string||
|bookerId|ID of the user of stub user who booked this lesson|false|string||
|royaltyPercent|The percentage of money the school gets for the lesson.|true|number (double)||


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
|timestamp|The time of this message creation|true|string (date)||
|deleted|Says whether the message has been deleted. If true - it is scheduled for permanent deletion.|true|boolean||
|formerInstructorId|The Id of the instructor previously assigned to this lesson.|false|string||
|fromId|Entity type and ID of the person / school which sent this message|true|EntityID||
|important|Whether it is in the 'important' category.|true|boolean||
|lessonId|The id of the lesson that was changed|false|string||
|memberId|ID of the member assigning or unassigning the lesson.|false|string||
|message|The content of the message|true|string||
|oldRole|The previous role of the user who changed|false|string||
|participantId|Person for whom the lesson was booked/unbooked for.|false|string||
|productId|Id of added/removed/changed  lesson / bundle|false|string||
|read|Whether it has already been read.|true|boolean||
|role|The role of the person requesting the lesson|false|string||
|timesOff|A list of periods where the instructor will not be available|false|TimeInterval||
|toId|Entity type and ID of the user/school that is the receiver of this message.|true|EntityID||
|type|Type of message - request, notification etc.|true|string||


### BundleTemplate
|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|_id||true|string||
|name|Name of the generated bundles.|true|string||
|comment|Auto-generated comment for every bundle.|false|string||
|discount|Discount for the generated bundles.|true|Discount||


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
|generatedLessons|A list of IDs of lessons generated by this generator.|true|string array||
|name|Name of the generator.|true|string||
|generatorType|Determines whether it is a lesson or a bundle generator.|true|string||
|generatedBundles|A list of IDs of bundles generated by this generator.|false|string array||
|lessonTemplateId|Template used to create new lessons.|true|LessonTemplate||
|priority|The generator priority (starting from 1, 2, 3, ...), determines the generator precedence in case of overlapping lessons.|true|integer (int32)||
|bundleTemplateId|Template used to generate bundles.|false|BundleTemplate||
|schoolId|ID of the school the generator belongs to.|true|string||
|times|List of time intervals for which the lessons / bundles will be generated.|true|TimeInterval||
|publicFlag|Decides whether the generated lessons and bundles are public.|true|boolean||


### Specialty

An entity representing an instructor specialty.

|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|type|Type of the specialty - ski, snowboard etc.|true|string||
|expertise|Expertises the instr can teach.|true|string||


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
|userId|The corresponding `User`, stored as ID, but will be fetched as an entire embedded object at backend side.|true|User||
|permissions|What the user is allowed to do in this school.|true|string array||
|timesOff|Time intervals during which the user is unavailable|true|TimeInterval array||
|schoolId|The school the employee works at.|true|School||
|specialties|Specialties the user can teach.|false|Specialty array||
|deleted|Says whether the employee was deleted.|true|boolean||


### Bundle

A group of lessons with a discount if a user will decide to purchase all of them.

|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|_id||true|string||
|comment|A creators comment towards the bundle.|false|string||
|deleted|Says whether the bundle has been deleted. If true - it is scheduled for permanent deletion.|true|boolean||
|discount|The discount the user gets for the lessons in this bundle|false|Discount||
|lessons|A list of lessons belonging to this bundle.|true|string array||
|mandatoryBooking|Says whether the lessons of the bundle can be booked without purchasing the whole bundle.|false|boolean||
|name|The name of the bundle.|true|string||
|publicFlag|A flag determining whether the bundle is public or private.|true|boolean||
|private|Whether it's booked by one or multiple persons|false|boolean||
|schoolId|ID of the school at which the bundle's lessons will occur.|true|string||
|generatorId|ID of the generator the bundle comes from (if any).|false|string||


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


### Discount

Object representing fields needed for different types of discounts.

|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|type|Enum representing the discount type - flatPerLesson / flatTotal / percentage|true|string||
|value|Numerical value of the discount|true|number (double)||


### Feedback

Entity representing a feedback (user to instructor, instructor to user or user to school)

|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|_id||true|string||
|fromId|ID and entity type of the sender.|true|EntityID||
|deleted|Whether the feedback has been deleted or not.|true|boolean||
|lessonId|ID of the lesson the feedback refers to.|true|string||
|toId|ID and entity type of the receiver.|true|EntityID||
|message|The content of the feedback|false|string||
|rating|The rating of the feedback|true|number (double)||
|absences|A list of users who didn't show up for the lesson in case it didn't occur after all.|false|string array||
|comment|A note on the lesson in case of special situations (e.g. if it didn't happen for whatever reason).|false|string||


### EntityID

Helper object defining an entity type

|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|entityId|ID of the object selected by `entity` field|true|string||
|entity|Selects an entity type: school, employee, user, lesson, bundle|true|string||


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
|private|Whether it's booked by one or multiple persons|true|boolean||
|bundleId|Id of the bundle containing the lesson|false|string||
|clientSource|Skipodium user, manually booked by school, white label etc|true|string||
|comment|A brief comment about the lesson.|false|string||
|deleted|Says whether the lesson has been deleted. If true - it is scheduled for permanent deletion.|true|boolean||
|timeFrom|Lesson start time|false|string (date)||
|timeTo|Lesson end time|false|string (date)||
|instructorBonusFlag|Bonus the instructor gets for the lesson|false|boolean||
|instructorId|ID of the instructor running the lesson.|true|string||
|level|The skill levels involved in this lesson.|false|string array||
|maxAge|Maximum age for this lesson.|false|integer (int32)||
|maxParticipants|Maximum number of participants.|false|integer (int32)||
|meetingPoint|A meeting point for this lesson.|true|MeetingPoint||
|minAge|Minimum age for this lesson.|false|integer (int32)||
|minParticipants|Minimum number of participants for this lesson.|false|integer (int32)||
|name|Name of the lesson.|true|string||
|participants|List of participants  attending this lesson|true|string array||
|prices|A list of price thresholds, depending on the time of booking|false|number (double) array||
|schoolId|ID of the school at which the lesson was carried out.|true|string||
|specialties|The specialities covered by the lesson|false|Specialty array||
|previousInstructorId|Id of the previous instructor|false|string||
|generatorId|ID of the generator the lesson comes from (if any).|false|string||


### Resort

Object representing a skiing resort.

|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|name|The name of the resort|true|string||
|coords|Resort's location|true|Address||
|pictureURL|Resort picture URL.|false|string||
|schools|A list of schools working in this resort.|true|string array||


### School

Information about a given school

|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|_id||true|string||
|address|School address|true|Address||
|bankDetails|School banking information.|true|BankDetails||
|contacts|A list of phone numbers, emails, or any contact details the school possesses.|false|string array||
|defaultMeetingPoints|A list of established meeting points for instructors and students.|true|MeetingPoint array||
|deleted|Says whether the school has been deleted. If true - it is scheduled for permanent deletion.|true|boolean||
|email|Main email address which can be used to contact the school|true|string||
|logo|An url  with the school logo file|true|string||
|name|The name of the school|true|string||
|openingHours|School working time (internal object with start and end time).|true|string (date)||
|resort|The resort the school belongs to.|true|Resort||
|manuallySetRating|School's rating|false|number (double)||
|enabled|Says whether the school lesson is enabled (e.g. whether its lessons appear for users).|true|boolean||
|royaltyPercent|The percentage of money the school receives for every lesson.|true|number (double)||


### BankDetails

This will be an internal object of an entity of type School.

|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|accountNumber|Bank account number.|true|string||
|currency|Currency the account number is in.|true|string||


