# Events
## Event Object
An event object contain all of information of a Talent Garden event.

| Filed    |      Type      |  <div style="width:100%">Description</div> |
|----------|---------------|------------|
| `organizer_id` |    integer   |   Identify the creator of the event.|
| `event_name` | string |   Event name |
| `summary` |  string |Event summary. Short summary describing the event and its purpose. |
| `description` |    string   |   Event description. Description can be lengthy and have significant formatting. |
| `start_utc` | time-stamp  | Event start, date and time. |
| `end_utc` |    time-stamp   |  Event end, date and time. |
| `status` | string | The status of event is always live.  |
| `online_event` |  boolean | True = Specifies that the Event is online only.  |
| `format_id` |    integer   |   The Format id represents an Event type, for example seminar, workshop or concert.  |
| `category_id` | integer |    An overarching category that an event falls into (vertical). Examples are “Music”, and “Endurance”. |
| `subcategory_id`| integer| A deeper category to describe the event. |
| `logo_url` | string  | The url of event's logo.  |
| `url` |    string   |   The url of event enable on eventbrite. |
| `locale` | string |  Specifies the language of the event. |
| `listed` | boolean |  True = Specifies that the Event is public. |
## Get All Events

#### HTTP Request
With this request you can get all information about the new talent garden events. <br></br>
`GET https://api.talentgarden.net/v1/events`

```shell
curl "https://api.talentgarden.net/v1/events
```
> The above command returns JSON structured like this:

```json
{
  "data": [
    {
      "id": "126409725893",
      "organizer_id": "2888489877",
      "event_name": "Build your online course",
      "summary": "Come produrre corsi online, dal più semplice al più complesso",
      "description": "Come produrre corsi online, dal più semplice al più complesso",
      "start_utc": "2020-11-10T17:30:00.000Z",
      "end_utc": "2020-11-10T18:30:00.000Z",
      "status": "live",
      "online_event": true,
      "format_id": 2,
      "category_id": 101,
      "subcategory_id": null,
      "url": "https://www.eventbrite.com/e/build-your-online-course-tickets-126409725893",
      "logo_url": "https://img.evbuc.com/https%3A%2F%2Fcdn.evbuc.com%2Fimages%2F115511911%2F63152314247%2F1%2Foriginal.20191009-144842?auto=format%2Ccompress&q=75&sharp=10&s=24cc030ffd6e8830d92d84c36e285c9a",
      "locale": "en_GB",
      "listed": true,
      "created_at": "2020-10-27T02:00:48.705Z",
      "organizer_name": "Talent Garden Isola - Milano"
    },
    {
      "id": "123482438297",
      "organizer_id": "16030478315",
      "event_name": "Introduction to Full Stack Development | Online Info Event",
      "summary": "Do you want to dive into the world of Coding? Are you ready for a career as a Full Stack Developer?",
      "description": "Do you want to dive into the world of Coding? Are you ready for a career as a Full Stack Developer?",
      "start_utc": "2020-10-29T16:00:00.000Z",
      "end_utc": "2020-10-29T17:00:00.000Z",
      "status": "live",
      "online_event": true,
      "format_id": 9,
      "category_id": 101,
      "subcategory_id": 1004,
      "url": "https://www.eventbrite.com/e/introduction-to-full-stack-development-online-info-event-registration-123482438297",
      "logo_url": "https://img.evbuc.com/https%3A%2F%2Fcdn.evbuc.com%2Fimages%2F114522263%2F385833754851%2F1%2Foriginal.20201013-151954?auto=format%2Ccompress&q=75&sharp=10&s=c3a33a5b6b3621d390c37b033590dc65",
      "locale": "en_GB",
      "listed": true,
      "created_at": "2020-10-27T02:00:48.705Z",
      "organizer_name": "Talent Garden Austria"
    }
  ],
  "pagination": {
    "page": 1,
    "per_page": 2,
    "total_elements": 13,
    "total_pages": 7
  }
}
```
#### Query Parameters
You can use this parameter to filter the events or you can sort them.

Parameter | example | Description
--------- | ------- | --------------
`organizer_id` | 1234567890 | Return only events with specified `organizer_id`.|
`format_id` | 1 | Return only events with speecified `format_id`.|
`category_id` | 101 | Return only events with speecified `category_id`.|
`sortby` | organizer_id | Return all events sorted by the fields of object.|



