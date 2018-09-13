Event
=======================

Get Events
----------

* `GET /events.json` will return a paginated list of unread events
* `GET /events.json?delivery_state=all` will return a paginated list of all events
* `GET /locations/64/events.json` will return a paginated list of unread events for specified location
* `GET /events.json?user_id=1232` will return a paginated list of unread events created by a specified user
* `GET /events.json?from=2018-09-12T22%3A00%3A00.000Z&until=2018-09-12T22%3A00%3A00.000Z` will return a paginated list of unread events created in a specified time frame
* `GET /events.json?event_type=[application]` will return a paginated list of unread events related to a specific ressource. event_type could be one or more of [location, schedule, shift, application, shift_category, absence, message]

```json
[
  {
    "created_at":"2018-02-03T18:23:58+02:00",
    "updated_at":"2018-02-03T18:23:58+02:00",
    "id":21312,
    "eventable_id":12321,
    "eventable_type":"User",
    "type":"user_created_event",
    "creator_id":12321,
    "description":"<strong class='creator'>Daniel Düsentrieb</strong> created the user <strong class='eventable-type'>Marvin@example.com</strong>",
    "changes":{},
    "location_id":null
  }
]
```
