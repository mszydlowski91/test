## Definitions
### Identified
|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|id||false|integer (int64)||


### User
|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|id||false|integer (int64)||
|username||false|string||
|firstName||false|string||
|lastName||false|string||
|email||false|string||
|password||false|string||
|phone||false|string||
|userStatus|User Status|false|integer (int32)||


### Category
|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|id||false|integer (int64)||
|name||false|string||


### Pet

Test description

|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|id||false|integer (int64)||
|category||false|Category||
|name||true|string||
|photoUrls||true|string array||
|tags||false|Tag array||
|status|pet status in the store|false|string||


### Tag
|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|id||false|integer (int64)||
|name||false|string||


### Order
|Name|Description|Required|Schema|Default|
|----|----|----|----|----|
|id||false|integer (int64)||
|petId||false|integer (int64)||
|quantity||false|integer (int32)||
|shipDate||false|string (date-time)||
|status|Order Status|false|string||
|complete||false|boolean||


