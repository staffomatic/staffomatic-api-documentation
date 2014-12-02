Locations
=======================

Get locations
----------

* `GET /locations.json` will return all locations

```json
[
  {
    "created_at": "2011-11-21T11:49:28+01:00",
    "updated_at": "2014-11-28T15:14:07+01:00",
    "id": 64,
    "name": "Mein Cafe!",
    "logo": "https://api.staffomaticapp.com/system/logos/64/api/1525596_227297620727879_2100097242_n.png?1413354842",
    "first_day_of_week": 1,
    "slot_minutes": 45,
    "min_time": 0,
    "max_time": 24,
    "default_view": "list_week",
    "default_event_minutes": 240,
    "show_event_header": true,
    "applications_visible": false,
    "assignments_visible": false,
    "allow_self_assign": false,
    "swap_shifts": true,
    "manners_address": "last_name",
    "users_sort_by": "working_hours",
    "notes_visible": true,
    "active_users_count": 12,
    "department_count": 10,
    "user_ids": []
  }
]
```

Get location
----------

* `GET /locations/64.json` will return the specified location.

```json
{
  "created_at": "2011-11-21T11:49:28+01:00",
  "updated_at": "2014-11-28T15:14:07+01:00",
  "id": 64,
  "name": "Mein Cafe!",
  "logo": "https://api.staffomaticapp.com/system/logos/64/api/1525596_227297620727879_2100097242_n.png?1413354842",
  "first_day_of_week": 1,
  "slot_minutes": 45,
  "min_time": 0,
  "max_time": 24,
  "default_view": "list_week",
  "default_event_minutes": 240,
  "show_event_header": true,
  "applications_visible": false,
  "assignments_visible": false,
  "allow_self_assign": false,
  "swap_shifts": true,
  "manners_address": "last_name",
  "users_sort_by": "working_hours",
  "notes_visible": true,
  "active_users_count": 12,
  "department_count": 10,
  "user_ids": []
}
```

Create location
--------------

* `POST /locations.json` will create a new location from the parameters passed.

```json
{
  "name": "My new location!",
  "allow_self_assign": true,
  "applications_visible": false,
  "assignments_visible": false,
  "default_event_minutes": 30,
  "first_day_of_wee": 1,
  "manners_address": "first_name",
  "max_time": "0",
  "min_time": "24",
  "notes_visible": true,
  "slot_minutes": "30",
  "swap_shifts": true,
  "users_sort_by": "alphabetical"
}
```

This will return `201 Created` with the current JSON representation of the location if the creation was a success.


Update location
--------------

PUT /locations/64.json will update the location from the parameters passed.

```json
{
  "name": "This is a new name for the location!"
}
```

Delete location
--------------

DELETE /locations/1.json will delete the location specified and return 204 No Content if that was successful. If the user does not have access to delete the location, you'll see 403 Forbidden.
