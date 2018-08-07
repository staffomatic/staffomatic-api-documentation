Work Timers
=======================

Get work_timers
----------

* `GET /work_timers.json` will return all work_timers
* `GET /work_timers.json?from=2016-07-01T00%3A00%3A00%2B02%3A00&until=2016-08-01T00%3A00%3A00%2B02%3A00` will return all work_timers for specified datetime range
* `GET /work_timers.json?user_ids%5B%5D=1` will return all work_timers for specified user id

```json
[
  {
   "created_at":"2018-08-06T13:13:21+02:00",
   "updated_at":"2018-08-06T13:14:57+02:00",
   "id":31231,
   "user_id":1,
   "location_id":null,
   "updated_by_id":1,
   "created_by_id":1,
   "state":"running",
   "duration":0,
   "break_duration":100,
   "net_duration":100,
   "starts_at":"2018-08-06T13:15:00+02:00",
   "ends_at":null,
   "application_starts_at":null,
   "application_ends_at":null,
   "application_intermission":null,
   "work_report_id":30077,
   "application_id":null,
   "device_type":"terminal"
  }
]
```

Get work_timer
----------

* `GET /work_timers/118976.json` will return the specified work_timer.

```json
{
 "created_at":"2018-08-06T13:13:21+02:00",
 "updated_at":"2018-08-06T13:14:57+02:00",
 "id":118976,
 "user_id":1,
 "location_id":null,
 "updated_by_id":1,
 "created_by_id":1,
 "state":"running",
 "duration":0,
 "break_duration":100,
 "net_duration":100,
 "starts_at":"2018-08-06T13:15:00+02:00",
 "ends_at":null,
 "application_starts_at":null,
 "application_ends_at":null,
 "application_intermission":null,
 "work_report_id":30077,
 "application_id":null,
 "device_type":"terminal"
}
```

Create work_timer
--------------

* `POST /work_timers.json` will create a new work_timer from the parameters passed.

```json
{
  "starts_at": "2015-07-20T08:00:00+02:00",
  "ends_at": "2015-07-20T16:00:00+02:00",
  "user_id": 231,
}
```

This will return `201 Created` with the current JSON representation of the work_timer if the creation was a success.


Update work_timer
--------------

* `PUT /work_timers/3068107.json` will update the work_timer from the parameters passed.

```json
{
  "ends_at": "2015-07-20T17:00:00+02:00",
}
```

Delete work_timer
--------------

* `DELETE /work_timers/3068107.json`

will delete the work_timer specified and return 204 No Content if that was successful. If the user does not have access to delete the work_timer, you'll see 403 Forbidden.


work_timer States
--------------

| State      | Explanation                                                 |
|----------- |-----------------------------------------------------------  |
| running    | work_timer is runnin and does not have a ends_at             |
| stopped    | work_timer has been stopped, a ends_at attribute is provided |
| verified   | work_timer has been stopped and verified |


change work_timer States
--------------

if you want to change the `state` of an work_timer, you can use following actions:


| do          | init state      | result state | Explanation                                                 |
|-----------  |---------------- |------------- |-----------------------------------------------------------  |
| start       | `new`           | `running`    | create a work_timer for a user and track the time           |
| stop        | `running`       | `stopped`    | stop a running work_timer |
| verify      | `stopped`       | `verified`   | verify a stopped work_timer |


* `PUT /work_timers/3068107.json` will update the work_timer and change the state.

```json
{
  "id": 123,
  "do": "stop"
}
```


Check-in
--------------

to Check-in a user and start the work_timer, use the following request:

* `POST /work_timers.json` will create a new work_timer from the parameters passed.

```json
{
  "user_id": 231,
  "do": "start"
}
```

or pass along a specified starts_at time:

```json
{
  "starts_at": "2015-07-20T08:00:00+02:00",
  "user_id": 231,
  "do": "start"
}
```


Check-out
--------------


to Check-out a user and stop the work_timer, use the following request:

* `PUT /work_timers.json` will create a new work_timer from the parameters passed.

```json
{
  "timer_id": 231,
  "do": "stop"
}
```

or pass along a specified ends_at time:

```json
{
  "ends_at": "2015-07-20T08:00:00+02:00",
  "user_id": 231,
  "do": "start"
}
```

Breaks
--------------

To create a break for a specific work_timer, see [break_timers](https://github.com/staffomatic/staffomatic-api-documentation/blob/master/ressources/break_timers.md)
