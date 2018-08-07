Break Timers
=======================

create break_timers to track breaks for your employee

Get break_timers
----------

* `GET /break_timers.json` will return all break_timers
* `GET /locations/64/break_timers.json` will return all break_timers for specified location
* `GET /break_timers.json?from=2016-07-01T00%3A00%3A00%2B02%3A00&until=2016-08-01T00%3A00%3A00%2B02%3A00` will return all break_timers for specified datetime range
* `GET /break_timers.json?user_ids%5B%5D=1` will return all break_timers for specified user id
* `GET /work_timers/60844/break_timers.json` will return all break_timers for specified work_timer_id

```json
[
  {
     "created_at":"2018-02-28T09:40:40+01:00",
     "updated_at":"2018-02-28T09:40:57+01:00",
     "id":24856,
     "user_id":493,
     "updated_by_id":493,
     "created_by_id":493,
     "duration":10,
     "starts_at":"2018-02-28T09:40:40+01:00",
     "work_timer_id":60844,
     "ends_at":"2018-02-28T09:40:50+01:00",
     "device_type":"terminal"
  }
]
```

Get break_timer
----------

* `GET /break_timers/118976.json` will return the specified break_timer.

```json
{
   "created_at":"2018-02-28T09:40:40+01:00",
   "updated_at":"2018-02-28T09:40:57+01:00",
   "id":123,
   "user_id":123,
   "updated_by_id":123,
   "created_by_id":123,
   "duration":10,
   "starts_at":"2018-02-28T09:40:40+01:00",
   "work_timer_id":60844,
   "ends_at":"2018-02-28T09:40:50+01:00",
   "device_type":"terminal"
}
```

Create break_timer
--------------

* `POST /break_timers.json` will create a new break_timer from the parameters passed.

```json
{
  "starts_at": "2015-07-20T08:00:00+02:00",
  "ends_at": "2015-07-20T16:00:00+02:00",
  "work_timer_id":60844,
}
```

This will return `201 Created` with the current JSON representation of the break_timer if the creation was a success.


Update break_timer
--------------

* `PUT /break_timers/3068107.json` will update the break_timer from the parameters passed.

```json
{
  "ends_at": "2015-07-20T17:00:00+02:00",
}
```

Delete break_timer
--------------

* `DELETE /break_timers/3068107.json`

will delete the break_timer specified and return 204 No Content if that was successful. If the user does not have access to delete the break_timer, you'll see 403 Forbidden.


break_timer States
--------------

| State      | Explanation                                                 |
|----------- |-----------------------------------------------------------  |
| running    | break_timer is runnin and does not have a ends_at             |
| stopped    | break_timer has been stopped, a ends_at attribute is provided |


change break_timer States
--------------

if you want to change the `state` of an break_timer, you can use following actions:


| do          | init state      | result state | Explanation                                                 |
|-----------  |---------------- |------------- |-----------------------------------------------------------  |
| start       | `new`           | `running`    | create a break_timer for a user and track the time           |
| stop        | `running`       | `stopped`    | stop a running break_timer |


* `PUT /break_timers/3068107.json` will update the break_timer and change the state.

```json
{
  "id": 123,
  "do": "stop"
}
```


Check-in
--------------

to Start a break for a running work_timer, use the following request:

* `POST /break_timers.json` will create a new break_timer from the parameters passed.

```json
{
  "work_timer_id": 231,
  "do": "start"
}
```

or pass along a specified starts_at time:

```json
{
  "starts_at": "2015-07-20T08:00:00+02:00",
  "work_timer_id": 231,
  "do": "start"
}
```


Check-out
--------------


to stop a break_timer, use the following request:

* `PUT /break_timers.json` will create a new break_timer from the parameters passed.

```json
{
  "work_timer_id": 231,
  "do": "stop"
}
```

or pass along a specified ends_at time:

```json
{
  "ends_at": "2015-07-20T08:00:00+02:00",
  "work_timer_id": 231,
  "do": "start"
}
```

