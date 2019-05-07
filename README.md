# ![LOGO](logo.png) CallFire **flow**ground Connector

## Description

A generated **flow**ground connector for the CallFire API (version V2).

Generated from: https://api.apis.guru/v2/specs/callfire.com/V2/swagger.json<br/>
Generated at: 2019-05-07T17:39:52+03:00

## API Description

CallFire

## Authorization

Supported authorization schemes:
- Basic Authentication

## Actions

### Find calls

> To search for all calls sent or received by the user. Use "id=0" for the campaignId parameter to query for all calls sent through the POST /calls API. See [call states and results](https://developers.callfire.com/results-responses-errors.html)

*Tags:* `calls`

#### Input Parameters
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.
* `limit` - _optional_ - To set the maximum number of records to return in a paged list response. The default is 100
* `offset` - _optional_ - Offset to the start of a given page. The default is 0. Check [pagination](https://developers.callfire.com/docs.html#pagination) page for more information about pagination in CallFire API.
* `id` - _optional_ - Lists the Call ids to search for. If calls ids are specified then other query parameters can be ignored
* `campaignId` - _optional_ - An id of a campaign, queries for calls included to a particular campaign. Specify null for all campaigns and 0 for default campaign
* `batchId` - _optional_ - An id of a contact batch, queries for calls of a particular contact batch
* `fromNumber` - _optional_ - Phone number in E.164 format (11-digit) that call was from. Example: 12132000384
* `toNumber` - _optional_ - Phone number in E.164 format (11-digit) that call was sent to. Example: 12132000384
* `label` - _optional_ - A label for a specific call
* `states` - _optional_ - Searches for all calls which correspond to statuses listed in a comma separated string. Available values: READY, SELECTED, CALLBACK, FINISHED, DISABLED, DNC, DUP, INVALID, TIMEOUT, PERIOD_LIMIT. See [call states and results](https://developers.callfire.com/results-responses-errors.html)
* `results` - _optional_ - Searches for all calls with statuses listed in a comma separated string. Available values: SENT, RECEIVED, DNT, TOO_BIG, INTERNAL_ERROR, CARRIER_ERROR, CARRIER_TEMP_ERROR, UNDIALED. See [call states and results](https://developers.callfire.com/results-responses-errors.html)
* `inbound` - _optional_ - Filters inbound calls for "true" value and outbound calls for "false" value
* `intervalBegin` - _optional_ - Start of the find time interval, formatted in unix time milliseconds. Example: 1473781817000 for Sat, 05 Jan 1985 14:03:37 GMT
* `intervalEnd` - _optional_ - End of the find time interval, formatted in unix time milliseconds. Example: 1473781817000 for Sat, 05 Jan 1985 14:03:37 GMT

### Send calls

> Use the /calls API to send individual calls quickly. A verified Caller ID and sufficient credits are required to make a call. CallRecipient represents a single recipient identified by phone number or contact id in CallFire system. You can attach user-defined attributes to a Call action via CallRecipient.attributes property, attributes are available in Call action response

*Tags:* `calls`

#### Input Parameters
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.
* `campaignId` - _optional_ - Specifies a campaignId to send calls quickly on a previously created campaign
* `defaultLiveMessage` - _optional_ - Text to be turned into a sound, this text will be played when the phone is answered. Parameter can be overridden for any particular CallRecipient
* `defaultMachineMessage` - _optional_ - Text to be turned into a sound, this text will be played when answering machine is detected. Parameter can be overridden for any particular CallRecipient
* `defaultLiveMessageSoundId` - _optional_ - Id of sound file to play if phone is answered. Parameter can be overridden for any particular CallRecipient
* `defaultMachineMessageSoundId` - _optional_ - An id of a sound file to play if answering machine is detected. Parameter can be overridden for any particular CallRecipient
* `defaultVoice` - _optional_ - The voice set by default for all text-to-speech messages defined in CallRecipient objects or as default *Message properties
    Possible values: MALE1, FEMALE1, FEMALE2, SPANISH1, FRENCHCANADIAN1.
* `strictValidation` - _optional_ - Turns on strict validation for recipients. System will reply with BAD_REQUEST(400) if strictValidation = true and one of numbers didn't pass validation

### Find call broadcasts

> Searches for all voice broadcasts created by user. Can query on label, name, and the current running status of the campaign. Returns a paged list of voice broadcasts

*Tags:* `calls`

#### Input Parameters
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.
* `limit` - _optional_ - To set the maximum number of records to return in a paged list response. The default is 100
* `offset` - _optional_ - Offset to the start of a given page. The default is 0. Check [pagination](https://developers.callfire.com/docs.html#pagination) page for more information about pagination in CallFire API.
* `label` - _optional_ - A label of a voice broadcast
* `name` - _optional_ - A name of voice broadcast
* `running` - _optional_ - Specify whether the campaigns should be running or not
* `scheduled` - _optional_ - Specify whether the campaigns should be scheduled or not
* `intervalBegin` - _optional_ - Start of the find time interval, formatted in unix time milliseconds. Example: 1473781817000 for Sat, 05 Jan 1985 14:03:37 GMT
* `intervalEnd` - _optional_ - End of the find time interval, formatted in unix time milliseconds. Example: 1473781817000 for Sat, 05 Jan 1985 14:03:37 GMT

### Create a call broadcast

> Creates a call broadcast campaign using the Call Broadcast API. Send a CallBroadcast in the message body to add details in a voice broadcast campaign. The campaign can be created without contacts and bare minimum configuration, but contacts will have to be added further on to use the campaign

*Tags:* `calls`

#### Input Parameters
* `start` - _optional_ - Specify whether to immediately start this campaign (not required)
* `strictValidation` - _optional_ - Turns on strict validation for recipients. System will reply with BAD_REQUEST(400) if strictValidation = true and one of numbers didn't pass validation

### Find a specific call broadcast

> Returns a single CallBroadcast instance for a given call broadcast campaign id

*Tags:* `calls`

#### Input Parameters
* `id` - _required_ - An id of a CallBroadcast
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.

### Update a call broadcast

> This operation lets the user modify the configuration of a voice broadcast campaign after call broadcast campaign is created. See CallBroadcast for more information on what can/can't be updated on this API

*Tags:* `calls`

#### Input Parameters
* `id` - _required_ - An id of a voice broadcast
* `strictValidation` - _optional_ - Turns on strict validation for recipients. System will reply with BAD_REQUEST(400) if strictValidation = true and one of numbers didn't pass validation

### Archive voice broadcast

> Archives a voice broadcast (voice broadcast will be hidden in search results)

*Tags:* `calls`

#### Input Parameters
* `id` - _required_ - An id of a voice broadcast to archive

### Find batches in a call broadcast

> This endpoint will enable the user to page through all of the batches for a particular voice broadcast campaign

*Tags:* `calls`

#### Input Parameters
* `id` - _required_ - An id of a call broadcast
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.
* `limit` - _optional_ - To set the maximum number of records to return in a paged list response. The default is 100
* `offset` - _optional_ - Offset to the start of a given page. The default is 0. Check [pagination](https://developers.callfire.com/docs.html#pagination) page for more information about pagination in CallFire API.

### Add batches to a call broadcast

> The 'add batch' API allows user to add additional batches to an already created voice broadcast campaign. The added batch will go through the CallFire validation process, unlike in the recipients version of this API. That is why you can use the scrubDuplicates flag to remove duplicates from your batch. Batches may be added as a contact list id, a list of contact ids, or a list of numbers

*Tags:* `calls`

#### Input Parameters
* `id` - _required_ - An id of a call broadcast
* `strictValidation` - _optional_ - Turns on strict validation for recipients. System will reply with BAD_REQUEST(400) if strictValidation = true and one of numbers didn't pass validation

### Find calls in a call broadcast

> This endpoint will enable the user to page through all calls for a particular call broadcast campaign

*Tags:* `calls`

#### Input Parameters
* `id` - _required_ - An Id of a call broadcast
* `batchId` - _optional_ - An id of a particular batch associated with broadcast
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.
* `limit` - _optional_ - To set the maximum number of records to return in a paged list response. The default is 100
* `offset` - _optional_ - Offset to the start of a given page. The default is 0. Check [pagination](https://developers.callfire.com/docs.html#pagination) page for more information about pagination in CallFire API.

### Add recipients to a call broadcast

> Use this API to add the recipients to an existing voice broadcast. Post a list of Recipient objects to be added to the voice broadcast campaign. These contacts will not go through validation process, and will be acted upon as they are added. Recipients may be added as a list of contact ids, or list of numbers

*Tags:* `calls`

#### Input Parameters
* `id` - _required_ - An id of a call broadcast
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.
* `strictValidation` - _optional_ - Turns on strict validation for recipients. System will reply with BAD_REQUEST(400) if strictValidation = true and one of numbers didn't pass validation

### Start voice broadcast

> Start a voice broadcast

*Tags:* `calls`

#### Input Parameters
* `id` - _required_ - An id of voice broadcast to start

### Get statistics on call broadcast

> Returns broadcast statistics like total number of sent/received actions, total cost, number of remaining outbound actions, error count, etc

*Tags:* `calls`

#### Input Parameters
* `id` - _required_ - An id of a call broadcast
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.
* `begin` - _optional_ - Start of the search time interval, formatted in unix time milliseconds. Example: 1473781817000 for Sat, 05 Jan 1985 14:03:37 GMT
* `end` - _optional_ - End of the search time interval, formatted in unix time milliseconds. Example: 1473781817000 for Sat, 05 Jan 1985 14:03:37 GMT

### Stop voice broadcast

> Stop a voice broadcast

*Tags:* `calls`

#### Input Parameters
* `id` - _required_ - An id of voice broadcast to stop

### Get call recording by id

> Returns metadata of recording of a particular call. Metadata contains a link to a MP3 recording

*Tags:* `calls`

#### Input Parameters
* `id` - _required_ - ~
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.

### Get call recording in mp3 format

> Returns an MP3 recording of particular call, response contains binary data, content type is 'audio/mpeg'

*Tags:* `calls`

#### Input Parameters
* `id` - _required_ - An id of a call

### Find a specific call

> Returns a single Call instance for a given call id.

*Tags:* `calls`

#### Input Parameters
* `id` - _required_ - An id of a call
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.

### Get call recordings for a call

> Returns a list of recordings metadata of particular call. Metadata contains link to a MP3 recording

*Tags:* `calls`

#### Input Parameters
* `id` - _required_ - An id of a call
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.

### Get call recording by name

> Returns recording metadata of particular call. Metadata contains link to a MP3 recording

*Tags:* `calls`

#### Input Parameters
* `id` - _required_ - An id of a call
* `name` - _required_ - A name of a recording
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.

### Get call mp3 recording by name

> Returns a MP3 recording of a particular call, response contains binary data, content type is 'audio/mpeg'

*Tags:* `calls`

#### Input Parameters
* `id` - _required_ - An id of a call
* `name` - _required_ - A name of a recording

### Find a specific batch

> Returns a single Batch instance for a given batch id. This API is useful for determining the state of a validating batch

*Tags:* `campaigns`

#### Input Parameters
* `id` - _required_ - An id of a batch
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.

### Update a batch

> Updates a single Batch instance, currently batch can only be turned "on/off"

*Tags:* `campaigns`

#### Input Parameters
* `id` - _required_ - An id of a batch to update

### Find sounds

> To find all campaign sounds which were created by user. Returns all sounds available to be used in campaigns

*Tags:* `campaigns`

#### Input Parameters
* `limit` - _optional_ - To set the maximum number of records to return in a paged list response. The default is 100
* `offset` - _optional_ - Offset to the start of a given page. The default is 0. Check [pagination](https://developers.callfire.com/docs.html#pagination) page for more information about pagination in CallFire API.
* `filter` - _optional_ - Name of a file to search for
* `includeArchived` - _optional_ - Includes ARCHIVED sounds for "true" value
* `includePending` - _optional_ - Includes UPLOAD/RECORDING sounds for "true" value
* `includeScrubbed` - _optional_ - Includes SCRUBBED sounds for "true" value
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.

### Add sound via call

> Use this API to create a sound via a phone call. Provide the required phone number in the CallCreateSound object inside the request, and user will receive a call shortly after with instructions on how to record a sound over the phone.

*Tags:* `campaigns`

#### Input Parameters
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.

### Add sound via file

> Create a campaign sound file via a supplied .mp3 or .wav file

*Tags:* `campaigns`

#### Input Parameters
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.

### Add sound via text-to-speech

> Use this API to create a sound file via a supplied string of text. Add a text in the TextToSpeech.message field, and pick a voice in the TextToSpeech.voice field. Available voices are: MALE1, FEMALE1, FEMALE2, SPANISH1, FRENCHCANADIAN1

*Tags:* `campaigns`

#### Input Parameters
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.

### Delete a specific sound

> Deletes a single campaign sound instance for a specific campaign sound id, this operation does not delete sound completely, it sets sound status to ARCHIVED which means that sound will no longer appear in 'find' operation results, but still accessible via 'get' operation

*Tags:* `campaigns`

#### Input Parameters
* `id` - _required_ - An id of a campaign sound

### Find a specific sound

> Returns a single CampaignSound instance for a given sound id in campaign. This is a meta data to the sounds. No audio data is returned from this API

*Tags:* `campaigns`

#### Input Parameters
* `id` - _required_ - An id of a sound campaign
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.

### Download a MP3 sound

> Download the MP3 version of a hosted file. This is an audio data endpoint. Returns binary response of the 'audio/mpeg' content type

*Tags:* `campaigns`

#### Input Parameters
* `id` - _required_ - An id of a campaign sound

### Download a WAV sound

> Download the WAV version of the hosted file. This is an audio data endpoint. Returns binary response of the 'audio/mpeg' content type

*Tags:* `campaigns`

#### Input Parameters
* `id` - _required_ - An id of a campaign sound

### Find contacts

> Find user's contacts by id, contact list, or on any property name. Returns a paged list of contacts

*Tags:* `contacts`

#### Input Parameters
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.
* `limit` - _optional_ - To set the maximum number of records to return in a paged list response. The default is 100
* `offset` - _optional_ - Offset to the start of a given page. The default is 0. Check [pagination](https://developers.callfire.com/docs.html#pagination) page for more information about pagination in CallFire API.
* `id` - _optional_ - A list of contact IDs. If the id parameter is included, the other query parameters are ignored.
* `number` - _optional_ - Multiple contact numbers can be specified. If the number parameter is included, the other query parameters are ignored.
* `contactListId` - _optional_ - Filters contacts by a particular contact list
* `propertyName` - _optional_ - Name of a contact property to search by
* `propertyValue` - _optional_ - Value of a contact property to search by

### Create contacts

> Creates contacts in CallFire system. See [contacts validation rules](https://www.callfire.com/help/docs/getting-started/managing-contacts/validating-contacts#section1)

*Tags:* `contacts`

### Find do not contact (dnc) items

> Searches for all Do Not Contact (DNC) objects created by user. These DoNotContact entries only affect calls/texts/campaigns on this account. Returns a paged list of DoNotContact objects

*Tags:* `contacts`

#### Input Parameters
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.
* `limit` - _optional_ - To set the maximum number of records to return in a paged list response. The default is 100
* `offset` - _optional_ - Offset to the start of a given page. The default is 0. Check [pagination](https://developers.callfire.com/docs.html#pagination) page for more information about pagination in CallFire API.
* `prefix` - _optional_ - Prefix (1-10 digits) of phone numbers
* `campaignId` - _optional_ - A campaign id which was used to send a message to a DNC number
* `source` - _optional_ - A DNC source name to search for DNCs
* `call` - _optional_ - Show only Do-Not-Call numbers
* `text` - _optional_ - Show only Do-Not-Text numbers
* `inboundCall` - _optional_ - ~
* `inboundText` - _optional_ - ~
* `number` - _optional_ - ~

### Add do not contact (dnc) numbers

> Add or update a list of Do Not Contact (DNC) contact entries. Can toggle whether the DNCs are enabled for calls/texts.

*Tags:* `contacts`

### Delete do not contact (dnc) numbers contained in source.

> Delete Do Not Contact (DNC) contact entries contained in source.

*Tags:* `contacts`

#### Input Parameters
* `source` - _required_ - Source associated with Do Not Contact (DNC) entry.

### Find universal do not contacts (udnc) associated with toNumber

> Searches for a UniversalDoNotContact object for a given phone number. Shows whether inbound/outbound actions are allowed for a given number

*Tags:* `contacts`

#### Input Parameters
* `toNumber` - _required_ - A required destination phone number in E.164 format (11-digit). Example: 12132000384
* `fromNumber` - _optional_ - An optional destination/source number for DNC, specified in E.164 format (11-digit). Example: 12132000384
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.

### Delete do not contact (dnc) number. If number contains commas treat as list of numbers

> Delete a Do Not Contact (DNC) contact entry.

*Tags:* `contacts`

#### Input Parameters
* `number` - _required_ - Number associated with Do Not Contact (DNC) entry.

### Get do not contact (dnc)

> Get Do Not Contact (DNC) object create by user. This DoNotContact entry only affects calls/texts/campaigns on this account.

*Tags:* `contacts`

#### Input Parameters
* `number` - _required_ - Number associated with Do Not Contact (DNC) entry.

### Update an individual do not contact (dnc) number

> Update a Do Not Contact (DNC) contact entry. Can toggle whether the DNC is enabled for calls/texts.

*Tags:* `contacts`

#### Input Parameters
* `number` - _required_ - ~

### Find contact lists

> Searches for all contact lists which are available for the current user. Returns a paged list of contact lists

*Tags:* `contacts`

#### Input Parameters
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.
* `limit` - _optional_ - To set the maximum number of records to return in a paged list response. The default is 100
* `offset` - _optional_ - Offset to the start of a given page. The default is 0. Check [pagination](https://developers.callfire.com/docs.html#pagination) page for more information about pagination in CallFire API.
* `name` - _optional_ - A name or a partial name of a contact list

### Create contact lists

> Creates a contact list for use with campaigns using 1 of 3 inputs. A List of Contact objects, a list of String E.164 numbers, or a list of CallFire contactIds can be used as the data source for the created contact list. After contact list is added into the CallFire system, contact lists goes through seven system safeguards that check the accuracy and consistency of the data. For example, our system checks that contact number is formatted correctly, is valid, is not duplicated in another contact list, or is not added on a specific DNC list. You can configure to keep/merge or remove contacts which do not complies these rules. If contacts were not added to a contact list after the validation, this means the data needs to be properly formatted and corrected before calling this API

*Tags:* `contacts`

### Create contact list from file

> Creates a contact list to be used with campaigns through uploading a .csv file. Returns the id of created list

*Tags:* `contacts`

### Delete a contact list

> Deletes a contact list, included contacts will not be deleted.

*Tags:* `contacts`

#### Input Parameters
* `id` - _required_ - An id of the contact list to be deleted

### Find a specific contact list

> Returns a single ContactList instance for a given contact list id

*Tags:* `contacts`

#### Input Parameters
* `id` - _required_ - An id of a contact list to return
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.

### Update a contact list

> Updates contact list instance.

*Tags:* `contacts`

#### Input Parameters
* `id` - _required_ - An id of contact list to update

### Delete contacts from a contact list

> Deletes contacts from a contact list. List the contact ids in request to delete multiple contacts with one request.

*Tags:* `contacts`

#### Input Parameters
* `id` - _required_ - A id of a contact list
* `contactId` - _optional_ - An id of a contact entity in the CallFire system

### Find contacts in a contact list

> Searches for all entries in a contact list with specified id. Returns a paged list of contact entries

*Tags:* `contacts`

#### Input Parameters
* `id` - _required_ - An id of a contact list
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.
* `limit` - _optional_ - To set the maximum number of records to return in a paged list response. The default is 100
* `offset` - _optional_ - Offset to the start of a given page. The default is 0. Check [pagination](https://developers.callfire.com/docs.html#pagination) page for more information about pagination in CallFire API.

### Add contacts to a contact list

> Adds contacts to a contact list. Available contact sources are: list of the contact entities, list of ids of existing contacts in user's account, list of phone numbers in E.164 format (11-digits)

*Tags:* `contacts`

#### Input Parameters
* `id` - _required_ - An id of a contact list

### Delete a contact from a contact list

> Deletes a single contact from a contact list

*Tags:* `contacts`

#### Input Parameters
* `id` - _required_ - An id of a contact list
* `contactId` - _required_ - An id of a contact

### Delete a contact

> Deletes a contact instance from account

*Tags:* `contacts`

#### Input Parameters
* `id` - _required_ - An Id of a contact

### Find a specific contact

> Returns a Contact instance for a given contact id. Deleted contacts can be still retrieved but will be marked as deleted. Deleted contacts will not be shown in search request.

*Tags:* `contacts`

#### Input Parameters
* `id` - _required_ - An id of a contact
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.

### Update a contact

> Updates a single contact instance with id specified. See [contact validation rules](https://www.callfire.com/help/docs/getting-started/managing-contacts/validating-contacts#section1)

*Tags:* `contacts`

#### Input Parameters
* `id` - _required_ - An id of a contact

### Find a contact's history

> Searches for all texts and calls attributed to a contact. Returns a list of calls and texts a contact has been involved with

*Tags:* `contacts`

#### Input Parameters
* `id` - _required_ - An Id of a contact
* `limit` - _optional_ - To set the maximum number of records to return in a paged list response. The default is 100
* `offset` - _optional_ - Offset to the start of a given page. The default is 0. Check [pagination](https://developers.callfire.com/docs.html#pagination) page for more information about pagination in CallFire API.
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.

### Find keywords

> Searches for all keywords available for purchase on the CallFire platform. If a keyword appears in the response, it is available for purchase. List the 'keywords' in a query parameter to search for multiple keywords (at least one keyword should be sent in request). Keyword should only consist of uppercase and lowercase letters and numbers. Number of characters must be greater than 2, but less than 65.

*Tags:* `keywords`

#### Input Parameters
* `keywords` - _optional_ - A keyword to search for

### Find keyword leases

> Searches for all keywords owned by user. A keyword lease is the ownership information involving a keyword

*Tags:* `keywords`

#### Input Parameters
* `limit` - _optional_ - To set the maximum number of records to return in a paged list response. The default is 100
* `offset` - _optional_ - Offset to the start of a given page. The default is 0. Check [pagination](https://developers.callfire.com/docs.html#pagination) page for more information about pagination in CallFire API.
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.

### Find a specific lease

> Searches for all keywords owned by user

*Tags:* `keywords`

#### Input Parameters
* `keyword` - _required_ - Keyword text that a lease is desired for
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.

### Update a lease

> Updates a keyword lease. Turns the autoRenew on/off. Configure double opt in feature. Add/remove contact list from keyword.

*Tags:* `keywords`

#### Input Parameters
* `keyword` - _required_ - To update a keyword lease

### Check for a specific keyword

> Searches for the specific keyword to purchase on the CallFire platform. Returns 'true' if keyword is available. Keyword should only consist of uppercase and lowercase letters and numbers. Number of characters must be greater than 2, but less than 65.

*Tags:* `keywords`

#### Input Parameters
* `keyword` - _required_ - To specify a keyword to search for. Example: SUN, MOON

### Find account details

> Searches for the user account details. Details include name, email, and basic account permissions. For authentication use api credentials.

*Tags:* `me`

### Find api credentials

> Searches for all credentials generated by user. Returns a paged list of the API credentials. Only ACCOUNT_HOLDER can invoke this API. For authentication use account credentials.

*Tags:* `me`

#### Input Parameters
* `name` - _optional_ - Filter by name
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.
* `limit` - _optional_ - To set the maximum number of records to return in a paged list response. The default is 100
* `offset` - _optional_ - Offset to the start of a given page. The default is 0. Check [pagination](https://developers.callfire.com/docs.html#pagination) page for more information about pagination in CallFire API.

### Create api credentials

> Creates an API credentials for the CallFire API. This endpoint requires full CallFire account credentials to be used, authenticated using Basic Authentication. At the moment user provides only the name for the credentials. The generated credentials can be used to access any CallFire APIs. For authentication use account credentials.

*Tags:* `me`

### Delete api credentials

> Deletes a specified API credential. Currently, removes the ability to access the API. Only ACCOUNT_HOLDER can invoke this API. For authentication use account credentials.

*Tags:* `me`

#### Input Parameters
* `id` - _required_ - An id of an API credential

### Find a specific api credential

> Returns an API credential instance for a given api credential id. Only ACCOUNT_HOLDER can invoke this API. For authentication use account credentials.

*Tags:* `me`

#### Input Parameters
* `id` - _required_ - An id of an API credential
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.

### Disable specified API credentials

> Disables a specified API credential. Currently, removes the ability to access the API. Only ACCOUNT_HOLDER can invoke this API. For authentication use account credentials.

*Tags:* `me`

#### Input Parameters
* `id` - _required_ - An id of an API credential

### Enable specified API credentials

> Enables a specified API credential. Currently, adds the ability to access the API. Only ACCOUNT_HOLDER can invoke this API. For authentication use account credentials.

*Tags:* `me`

#### Input Parameters
* `id` - _required_ - An id of an API credential

### Find credit usage

> Find credit usage for the user. Returns credits usage for time period specified or if unspecified then total for all time. For authentication use api credentials.

*Tags:* `me`

#### Input Parameters
* `intervalBegin` - _optional_ - Beginning of usage period formatted in unix time milliseconds. Example: 1473781817000
* `intervalEnd` - _optional_ - End of usage period formatted in unix time milliseconds. Example: 1473781817000

### Find plan usage

> Searches for the data of a billing plan usage for the user. Returns the data of a billing plan usage for the current month. For authentication use api credentials.

*Tags:* `me`

### Find caller ids

> Returns a list of verified caller ids. If the number is not shown in the list, then it is not verified. In this case sending of a verification code is required. For authentication use api credentials.

*Tags:* `me`

### Create a caller id

> Generates and sends a verification code to the phone number provided in the path. The verification code is delivered via a phone call. This code needs to be submitted to the verify caller id API endpoint to complete verification. For authentication use api credentials.

*Tags:* `me`

#### Input Parameters
* `callerid` - _required_ - A phone number in E.164 format (11-digit) which needs to be verified. Example: 12132000384

### Verify a caller id

> With the verification code received from the Create caller id endpoint, a call to this endpoint is required to finish verification. For authentication use api credentials.

*Tags:* `me`

#### Input Parameters
* `callerid` - _required_ - A phone number in E.164 format (11-digit) which needs to be verified. Example: 12132000384

### Find media

> Find media files created by user

*Tags:* `media`

#### Input Parameters
* `limit` - _optional_ - To set the maximum number of records to return in a paged list response. The default is 100
* `offset` - _optional_ - Offset to the start of a given page. The default is 0. Check [pagination](https://developers.callfire.com/docs.html#pagination) page for more information about pagination in CallFire API.
* `filter` - _optional_ - Name of a file to search for
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.

### Create media

> Uploads media file to account, acceptable media formats: bmp, gif, jpg, m4a, mp3, mp4, png, wav

*Tags:* `media`

### Download media by extension

> Download a media file. Available types of files: bmp, gif, jpg, m4a, mp3, mp4, png, wav. Content type in response depends on 'extension' parameter, e.g. image/jpeg, image/png, audio/mp3, etc

*Tags:* `media`

#### Input Parameters
* `key` - _required_ - A hash-key of a media resource
* `extension` - _required_ - Media file type, available types: bmp, gif, jpg, m4a, mp3, mp4, png, wav

### Get a specific media

> Get media resource by id

*Tags:* `media`

#### Input Parameters
* `id` - _required_ - An id of a media resource
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.

### Download media by extension

> Download a media file. Available types of files: bmp, gif, jpg, m4a, mp3, mp4, png, wav. Content type in response depends on 'extension' parameter, e.g. image/jpeg, image/png, audio/mp3, etc

*Tags:* `media`

#### Input Parameters
* `id` - _required_ - An id of a media resource
* `extension` - _required_ - Media file type. Available types: bmp, gif, jpg, m4a, mp3, mp4, png, wav

### Download a MP3 media

> Download a MP3 media, endpoint returns application/binary content-type

*Tags:* `media`

#### Input Parameters
* `id` - _required_ - An id of a media resource

### Find leases

> Searches for all numbers leased by account user. This API is useful for finding all numbers currently owned by the user. Returns a paged list of number leases.

*Tags:* `numbers`

#### Input Parameters
* `limit` - _optional_ - To set the maximum number of records to return in a paged list response. The default is 100
* `offset` - _optional_ - Offset to the start of a given page. The default is 0. Check [pagination](https://developers.callfire.com/docs.html#pagination) page for more information about pagination in CallFire API.
* `prefix` - _optional_ - A 4-7 digit prefix
* `city` - _optional_ - A city name
* `state` - _optional_ - A two-letter state code. Example: CA, IL, etc.
* `zipcode` - _optional_ - A five-digit Zipcode
* `labelName` - _optional_ - A label name
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.

### Find lease configs

> Searches for all number lease configs for the user. Returns a paged list of NumberConfig

*Tags:* `numbers`

#### Input Parameters
* `limit` - _optional_ - To set the maximum number of records to return in a paged list response. The default is 100
* `offset` - _optional_ - Offset to the start of a given page. The default is 0. Check [pagination](https://developers.callfire.com/docs.html#pagination) page for more information about pagination in CallFire API.
* `prefix` - _optional_ - A 4-7 digit prefix
* `city` - _optional_ - A city name
* `state` - _optional_ - A two-letter state code. Example: CA, IL, etc.
* `zipcode` - _optional_ - A five-digit Zipcode
* `labelName` - _optional_ - A label name
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.

### Find a specific lease config

> Returns a single NumberConfig instance for a given number lease

*Tags:* `numbers`

#### Input Parameters
* `number` - _required_ - A phone number in E.164 format (11-digit). Example: 12132000384
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.

### Update a lease config

> Updates a phone number lease configuration. Use this API endpoint to add an Inbound IVR or Call Tracking feature to a CallFire phone number. Call tracking configuration allows you to track the incoming calls, to analyze and to respond customers using sms or voice replies. For more information see [call tracking page](https://www.callfire.com/products/call-tracking)

*Tags:* `numbers`

#### Input Parameters
* `number` - _required_ - A phone number in E.164 format (11-digit) which needs to be verified. Example: 12132000384

### Find a specific lease

> Returns a single NumberLease instance for a given number

*Tags:* `numbers`

#### Input Parameters
* `number` - _required_ - A phone number in E.164 format (11-digit). Example: 12132000384
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.

### Update a lease

> Updates a number lease instance. Ability to turn on/off autoRenew and toggle call/text features for a particular number

*Tags:* `numbers`

#### Input Parameters
* `number` - _required_ - A phone number in E.164 format (11-digit). Example: 12132000384

### Find local numbers

> Searches for numbers available for purchase in CallFire local numbers catalog . At least one additional parameter is required. User may filter local numbers by their region information. If all numbers with desirable zip code is already busy search will return available numbers with nearest zip code.

*Tags:* `numbers`

#### Input Parameters
* `limit` - _optional_ - To set the maximum number of records to return in a paged list response. The default is 100
* `prefix` - _optional_ - A 4-7 digit prefix
* `city` - _optional_ - A city name
* `state` - _optional_ - A two-letter state code. Example: CA, IL, etc.
* `zipcode` - _optional_ - A five-digit Zipcode
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.

### Find number regions

> Searches for region information. Use this API to obtain detailed region information that can be used to query for more specific phone numbers than a general query.

*Tags:* `numbers`

#### Input Parameters
* `limit` - _optional_ - To set the maximum number of records to return in a paged list response. The default is 100
* `offset` - _optional_ - Offset to the start of a given page. The default is 0. Check [pagination](https://developers.callfire.com/docs.html#pagination) page for more information about pagination in CallFire API.
* `prefix` - _optional_ - A 4-7 digit prefix
* `city` - _optional_ - A city name
* `state` - _optional_ - A two-letter state code. Example: CA, IL, etc.
* `zipcode` - _optional_ - A five-digit Zipcode
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.

### Find tollfree numbers

> Searches for the toll free numbers which are available for purchase in the CallFire catalog

*Tags:* `numbers`

#### Input Parameters
* `pattern` - _optional_ - Filter toll free numbers by prefix, pattern must be 3 char long and should end with '*'. Examples: 8**, 85*, 87* (but 855 will fail because pattern must end with '*').
* `limit` - _optional_ - To set the maximum number of records to return in a paged list response. The default is 100
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.

### Purchase keywords

> Purchase keywords. Send a list of available keywords into this API to purchase them using CallFire credits. Make sure the account has enough credits before trying to purchase the keywords. Keyword should only consist of uppercase and lowercase letters and numbers. Number of characters must be greater than 2, but less than 65.

*Tags:* `orders`

### Purchase numbers

> Purchase numbers. There are many ways to purchase a number. Set either 'tollFreeCount' or 'localCount' along with some querying fields to purchase numbers by bulk query. Set the list of numbers to purchase by list. Available numbers will be purchased using CallFire credits owned by the user. Make sure the account has enough credits before trying to purchase

*Tags:* `orders`

### Find a specific order

> Returns a single NumberOrder instance for a given order id. Order contains information about purchased keywords, local, toll-free numbers

*Tags:* `orders`

#### Input Parameters
* `id` - _required_ - An id of an order
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.

### Find texts

> Searches for texts sent or received by user. Use "campaignId=0" parameter to query for all texts sent through the POST /texts API. See [call states and results](https://developers.callfire.com/results-responses-errors.html)

*Tags:* `texts`

#### Input Parameters
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.
* `limit` - _optional_ - To set the maximum number of records to return in a paged list response. The default is 100
* `offset` - _optional_ - Offset to the start of a given page. The default is 0. Check [pagination](https://developers.callfire.com/docs.html#pagination) page for more information about pagination in CallFire API.
* `id` - _optional_ - List of Text ids to search for, if ids specified other query params ignored
* `campaignId` - _optional_ - An id of a campaign, queries for texts inside a particular campaign. Specify null to list texts of all campaigns or 0 for a default campaign
* `batchId` - _optional_ - An Id of a contact batch, queries for texts which are used in the particular contact batch
* `fromNumber` - _optional_ - A phone number in E.164 format (11-digit). Example: 12132000384, 67076
* `toNumber` - _optional_ - A phone number in E.164 format (11-digit). Example: 12132000384, 67076
* `label` - _optional_ - A label of a text message
* `states` - _optional_ - Expected text statuses in comma separated string, available values: READY, SELECTED, CALLBACK, FINISHED, DISABLED, DNC, DUP, INVALID, TIMEOUT, PERIOD_LIMIT. See [call states and results](https://developers.callfire.com/results-responses-errors.html)
* `results` - _optional_ - Expected text results in comma separated string, available values: SENT, RECEIVED, DNT, TOO_BIG, INTERNAL_ERROR, CARRIER_ERROR, CARRIER_TEMP_ERROR, UNDIALED. See [call states and results](https://developers.callfire.com/results-responses-errors.html)
* `inbound` - _optional_ - Specify true for inbound or false for outbounds. Do not specify this parameter if you need to get both inbound and outbound texts listed in response
* `intervalBegin` - _optional_ - Start of the find time interval, formatted in unix time milliseconds. Example: 1473781817000
* `intervalEnd` - _optional_ - End of the find time interval, formatted in unix time milliseconds. Example: 1473781817000

### Send texts

> Use the /texts API to send individual texts quickly. By default all texts are going out from CallFire's dedicated short code 67076

*Tags:* `texts`

#### Input Parameters
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.
* `campaignId` - _optional_ - Specifies a campaignId to send texts through a previously created campaign
* `defaultMessage` - _optional_ - Text message can be overridden by TextRecipient.message field. If multiple recipients have the same text message to a different recipients it is better to specify a single default message and do not duplicate it in each recipient.
* `strictValidation` - _optional_ - Turns on strict validation for recipients

### Find auto replies

> Find all text autoreplies created by user. Returns a paged list of TextAutoReply

*Tags:* `texts`

#### Input Parameters
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.
* `limit` - _optional_ - To set the maximum number of records to return in a paged list response. The default is 100
* `offset` - _optional_ - Offset to the start of a given page. The default is 0. Check [pagination](https://developers.callfire.com/docs.html#pagination) page for more information about pagination in CallFire API.
* `number` - _optional_ - Phone number in E.164 format (11-digit) which contains a TextAutoReply. Example: 12132000384. If number is empty then operator returns all autoreplies configured for the user's account

### Create an auto reply

> CallFire gives you possibility to set up auto reply messages for your numbers and keywords. You can set a general auto reply for anyone who texts your number, keyword, and/or include a text to match, so that the auto reply would be sent only to those who text the matched text

*Tags:* `texts`

### Delete an auto reply

> Deletes a text auto reply and removes the configuration. Can not delete a TextAutoReply which is currently active for a campaign

*Tags:* `texts`

#### Input Parameters
* `id` - _required_ - An id of a text auto reply

### Find a specific auto reply

> Returns a single TextAutoReply instance for a given text auto reply id

*Tags:* `texts`

#### Input Parameters
* `id` - _required_ - An id of a text auto reply
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.

### Find text broadcasts

> Searches for all text broadcasts created by user. Can query on label, name, and the current running status of the campaign. Returns a paged list of text broadcasts

*Tags:* `texts`

#### Input Parameters
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.
* `limit` - _optional_ - To set the maximum number of records to return in a paged list response. The default is 100
* `offset` - _optional_ - Offset to the start of a given page. The default is 0. Check [pagination](https://developers.callfire.com/docs.html#pagination) page for more information about pagination in CallFire API.
* `label` - _optional_ - A label of a text broadcast
* `name` - _optional_ - A name of text broadcast
* `running` - _optional_ - Returns broadcasts only in running state.
* `scheduled` - _optional_ - Specify whether the campaigns should be scheduled or not
* `intervalBegin` - _optional_ - Start of the find time interval, formatted in unix time milliseconds. Example: 1473781817000 for Sat, 05 Jan 1985 14:03:37 GMT
* `intervalEnd` - _optional_ - End of the find time interval, formatted in unix time milliseconds. Example: 1473781817000 for Sat, 05 Jan 1985 14:03:37 GMT

### Create a text broadcast

> Creates a text broadcast campaign using the Text Broadcast API. Send a TextBroadcast object in the message body to detail a text broadcast campaign. A campaign can be created without contacts and with bare minimum configuration, but contacts have to be added further on to use the campaign. It supports scheduling, retry logic, pattern-based messages.

*Tags:* `texts`

#### Input Parameters
* `start` - _optional_ - If true then starts the campaign immediately (not required).
* `strictValidation` - _optional_ - Turns on strict validation for recipients. System will reply with BAD_REQUEST(400) if strictValidation = true and one of numbers didn't pass validation

### Find a specific text broadcast

> Returns a single TextBroadcast instance for a given text broadcast id

*Tags:* `texts`

#### Input Parameters
* `id` - _required_ - An id of a text broadcast
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.

### Update a text broadcast

> Allows modifying the configuration of existing text broadcast campaign. See TextBroadcast for more information on what can/can't be updated on this API

*Tags:* `texts`

#### Input Parameters
* `id` - _required_ - An id of a text broadcast
* `strictValidation` - _optional_ - Turns on strict validation for recipients. System will reply with BAD_REQUEST(400) if strictValidation = true and one of numbers didn't pass validation

### Archive text broadcast

> Archives a text broadcast (and hides it in the search results)

*Tags:* `texts`

#### Input Parameters
* `id` - _required_ - An id of a text broadcast to archive

### Find batches in a text broadcast

> This endpoint will enable the user to page through all of the batches for a particular text broadcast campaign

*Tags:* `texts`

#### Input Parameters
* `id` - _required_ - An id of a text broadcast
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.
* `limit` - _optional_ - To set the maximum number of records to return in a paged list response. The default is 100
* `offset` - _optional_ - Offset to the start of a given page. The default is 0. Check [pagination](https://developers.callfire.com/docs.html#pagination) page for more information about pagination in CallFire API.

### Add batches to a text broadcast

> Allows adding an extra batches to an already created text broadcast campaign. The batches which being  added pass the CallFire validation process (unlike in the recipients version of this API). That is why using of a scrubDuplicates flag remove duplicates from your batch. Batches may be added as a contact list id, a list of contact ids, or a list of numbers

*Tags:* `texts`

#### Input Parameters
* `id` - _required_ - An id of a text broadcast
* `strictValidation` - _optional_ - Turns on strict validation for recipients. System will reply with BAD_REQUEST(400) if strictValidation = true and one of numbers didn't pass validation

### Add recipients to a text broadcast

> Use this API to add recipients to a text broadcast which is already created. Post a list of Recipient objects to be immediately added to the text broadcast campaign. These contacts will not go through validation process, and will be acted upon as they are added. Recipients may be added as a list of contact ids, or list of numbers

*Tags:* `texts`

#### Input Parameters
* `id` - _required_ - An id of a text broadcast
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.
* `strictValidation` - _optional_ - Turns on strict validation for recipients. System will reply with BAD_REQUEST(400) if strictValidation = true and one of numbers didn't pass validation

### Start text broadcast

> Starts a text broadcast

*Tags:* `texts`

#### Input Parameters
* `id` - _required_ - An id of a text broadcast to start

### Get statistics on text broadcast

> Returns the broadcast statistics. Example: total number of the sent/received actions, total cost, number of remaining outbound actions, error count, etc

*Tags:* `texts`

#### Input Parameters
* `id` - _required_ - An id of a text broadcast
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.
* `begin` - _optional_ - Start of a search find time interval, formatted in unix time milliseconds. Example: 1473781817000 for Sat, 05 Jan 1985 14:03:37 GMT
* `end` - _optional_ - End of a search time interval, formatted in unix time milliseconds. Example: 1473781817000 for Sat, 05 Jan 1985 14:03:37 GMT

### Stop text broadcast

> Stops a text broadcast

*Tags:* `texts`

#### Input Parameters
* `id` - _required_ - An Id of a text broadcast. To stop the broadcast

### Find texts in a text broadcast

> This endpoint will enable the user to page through all of the texts for a particular text broadcast campaign

*Tags:* `texts`

#### Input Parameters
* `id` - _required_ - An id of a text broadcast
* `batchId` - _optional_ - ~
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.
* `limit` - _optional_ - To set the maximum number of records to return in a paged list response. The default is 100
* `offset` - _optional_ - Offset to the start of a given page. The default is 0. Check [pagination](https://developers.callfire.com/docs.html#pagination) page for more information about pagination in CallFire API.

### Find a specific text

> Returns a single Text instance for a given text id

*Tags:* `texts`

#### Input Parameters
* `id` - _required_ - An id of a text
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.

### Find webhooks

> Searches all webhooks available for a current user. Searches by name, resource, event, callback URL, or whether they are enabled. Returns a paged list of Webhooks

*Tags:* `webhooks`

#### Input Parameters
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.
* `limit` - _optional_ - To set the maximum number of records to return in a paged list response. The default is 100
* `offset` - _optional_ - Offset to the start of a given page. The default is 0. Check [pagination](https://developers.callfire.com/docs.html#pagination) page for more information about pagination in CallFire API.
* `name` - _optional_ - A name of a webhook
* `resource` - _optional_ - A name of a resource, available values: 'CccCampaign', 'CallBroadcast', 'TextBroadcast',  'OutboundCall', 'OutboundText', 'InboundCall', 'InboundText', 'ContactList'
* `event` - _optional_ - A name of event, available values: 'started', 'stopped', 'finished'
* `callback` - _optional_ - A callback URL
* `enabled` - _optional_ - Specifies whether webhook is enabled

### Create a webhook

> Create a Webhook for notification in the CallFire system. Use the webhooks API to receive notifications of important CallFire events. Select the resource to listen to, and then choose the resource events to receive notifications on. When an event triggers, a POST will be made to the callback URL with a payload of notification information. Available resources and their events include 'CccCampaign': ['started', 'stopped', 'finished'], 'CallBroadcast': ['started', 'stopped', 'finished'], 'TextBroadcast': ['started', 'stopped', 'finished'], 'OutboundCall': ['finished'], 'InboundCall': ['finished'], 'OutboundText': ['finished'], 'InboundText': ['finished'], 'ContactList': ['validationFinished', 'validationFailed']. Webhooks support secret token which is used as signing key to HmacSHA1 hash of json payload which is returned in 'X-CallFire-Signature' header. This header can be used to verify callback POST is coming from CallFire. See [security guide](https://developers.callfire.com/security-guide.html)

*Tags:* `webhooks`

### Find webhook resources

> Searches for webhook resources. Available resources include 'CccCampaign': ['started', 'stopped', 'finished'], 'CallBroadcast': ['started', 'stopped', 'finished'], 'TextBroadcast': ['started', 'stopped', 'finished'], 'OutboundCall': ['finished'], 'InboundCall': ['finished'], 'OutboundText': ['finished'], 'InboundText': ['finished'], 'ContactList': ['validationFinished', 'validationFailed']

*Tags:* `webhooks`

#### Input Parameters
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.

### Find specific webhook resource

> Returns information about supported events for a given webhook resource

*Tags:* `webhooks`

#### Input Parameters
* `resource` - _required_ - A name of a webhook resource. Available resources include 'CccCampaign': ['started', 'stopped', 'finished'], 'CallBroadcast': ['started', 'stopped', 'finished'], 'TextBroadcast': ['started', 'stopped', 'finished'], 'OutboundCall': ['finished'], 'InboundCall': ['finished'], 'OutboundText': ['finished'], 'InboundText': ['finished'], 'ContactList': ['validationFinished', 'validationFailed']
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.

### Delete a webhook

> Deletes a webhook instance. Will be removed permanently

*Tags:* `webhooks`

#### Input Parameters
* `id` - _required_ - An Id of a webhook

### Find a specific webhook

> Returns a single Webhook instance for a given webhook id

*Tags:* `webhooks`

#### Input Parameters
* `id` - _required_ - An id of a webhook
* `fields` - _optional_ - Limit fields received in response. E.g. fields: id, name or fields items (id, name), see more at [partial response](https://developers.callfire.com/docs.html#partial-response) page.

### Update a webhook

> Updates the information in existing webhook

*Tags:* `webhooks`

#### Input Parameters
* `id` - _required_ - An id of a webhook

## License

**flow**ground :- Telekom iPaaS / callfire-com-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
