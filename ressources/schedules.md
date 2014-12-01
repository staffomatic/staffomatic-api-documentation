Schedules
=======================

Get schedules
----------

* `GET /locations/64/schedules.json` will return all schedules

```json
[
  {
    "created_at": "2012-03-13T12:20:13+01:00",
    "updated_at": "2013-07-16T00:56:16+02:00",
    "id": 1699,
    "creator_id": 493,
    "schedule_id": 118,
    "state": "draft",
    "template": null,
    "bop": "2012-02-20",
    "eop": "2012-02-26",
    "deadline": "2012-02-16T00:00:00+01:00",
    "coverage_percentage": 0,
    "schedule_changes_count": 0,
    "first_day_of_week": 1,
    "slot_minutes": 30,
    "min_time": 0,
    "max_time": 24,
    "default_view": "agendaWeek",
    "default_event_minutes": 240,
    "show_event_header": false,
    "applications_visible": true,
    "assignments_visible": false,
    "swap_shifts": true,
    "notes_visible": false,
    "allow_self_assign": false
  }
]
```

Get schedule
----------

* `GET /locations/64/schedules/1699.json` will return the specified schedule.

```json
{
  "created_at": "2012-03-13T12:20:13+01:00",
  "updated_at": "2013-07-16T00:56:16+02:00",
  "id": 1699,
  "creator_id": 493,
  "schedule_id": 118,
  "state": "draft",
  "template": null,
  "bop": "2012-02-20",
  "eop": "2012-02-26",
  "deadline": "2012-02-16T00:00:00+01:00",
  "coverage_percentage": 0,
  "schedule_changes_count": 0,
  "first_day_of_week": 1,
  "slot_minutes": 30,
  "min_time": 0,
  "max_time": 24,
  "default_view": "agendaWeek",
  "default_event_minutes": 240,
  "show_event_header": false,
  "applications_visible": true,
  "assignments_visible": false,
  "swap_shifts": true,
  "notes_visible": false,
  "allow_self_assign": false
}
```

Create schedule
--------------

* `POST /locations/64/schedules.json` will create a new schedule from the parameters passed.

```json
{
  "bop": "2012-02-20",
  "deadline": "2012-02-16",
  "first_day_of_week": 1,
  "slot_minutes": 30,
  "min_time": 0,
  "max_time": 24,
  "default_event_minutes": 240,
  "show_event_header": false,
  "applications_visible": true,
  "assignments_visible": false,
  "swap_shifts": true,
  "notes_visible": false,
  "allow_self_assign": false
}
```

This will return `201 Created` with the current JSON representation of the schedule if the creation was a success.


Update schedule
--------------

* `PUT /locations/64/schedules/83959.json` will update the schedule from the parameters passed.

```json
{
  "deadline": "2012-02-16",
  "first_day_of_week": 1,
  "slot_minutes": 30,
  "min_time": 0,
  "max_time": 24,
  "default_event_minutes": 240,
  "show_event_header": false,
  "applications_visible": true,
  "assignments_visible": false,
  "swap_shifts": true,
  "notes_visible": false,
  "allow_self_assign": false
}
```

**Note:** You cannot change the `bop` of a schedule after creation.

Publish schedule
--------------

* `PUT /locations/64/schedules/83959.json` will update the schedule from the parameters passed.

```json
{
  "do": "publish",
  "message": "a new schedule is available!",
  "deliver_emails": true
}
```

**Note:** You can also pass any parameters for updating a schedule

Republish schedule
--------------

* `PUT /locations/64/schedules/83959.json` will update the schedule from the parameters passed.

```json
{
  "do": "republish",
  "message": "a new schedule is available!",
  "deliver_emails": true
}
```

Delete schedule
--------------

* `DELETE /locations/64/schedules/83959.json`

will delete the schedule specified and return 204 No Content if that was successful. If the user does not have access to delete the schedule, you'll see 403 Forbidden.
