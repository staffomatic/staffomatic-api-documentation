Users
=======================

Get users
----------

* `GET /locations/64/users.json` will return all users

```json
[
  {
    "created_at": "2011-11-10T15:10:13+01:00",
    "updated_at": "2014-12-01T20:50:33+01:00",
    "id": 493,
    "email": "admin@easypep.de",
    "first_name": "Admin",
    "last_name": "easyPEP",
    "locale": "de",
    "role": "admin",
    "image": "https://api.staffomaticapp.com/assets/images/missing/user.png",
    "phone_number_mobile": "017865646362",
    "phone_number_office": "04056788456",
    "company": "EASYPEP",
    "street": "Funhofweg 23",
    "additional_street": "bei Lange",
    "zip": "20234",
    "city": "Hamburg",
    "country": "",
    "max_vacation_days": 26,
    "comments_count": 2,
    "attachments_count": 2,
    "commentable": true,
    "attachable": true,
    "approved_absences_hours": 192,
    "max_hours_per_month": 20,
    "department_ids": [39166],
    "locked_at": null,
    "invited_by_id": null,
    "invitation_state": "accepted"
  }
]
```

Get user
----------

* `GET /locations/64/users/493.json` will return the specified user.

```json
{
  "created_at": "2011-11-10T15:10:13+01:00",
  "updated_at": "2014-12-01T20:50:33+01:00",
  "id": 493,
  "email": "admin@easypep.de",
  "first_name": "Admin",
  "last_name": "easyPEP",
  "locale": "de",
  "role": "admin",
  "image": "https://api.staffomaticapp.com/assets/images/missing/user.png",
  "phone_number_mobile": "017865646362",
  "phone_number_office": "04056788456",
  "company": "EASYPEP",
  "street": "Funhofweg 23",
  "additional_street": "bei Lange",
  "zip": "20234",
  "city": "Hamburg",
  "country": "",
  "max_vacation_days": 26,
  "comments_count": 2,
  "attachments_count": 2,
  "commentable": true,
  "attachable": true,
  "approved_absences_hours": 192,
  "max_hours_per_month": 20,
  "department_ids": [39166],
  "locked_at": null,
  "invited_by_id": null,
  "invitation_state": "accepted"
}
```

Invite user
--------------

* `POST /locations/64/users.json` will create a new user from the parameters passed.


```json
{
  "email": "admin+withinvitation@easypep.de",
  "department_ids": [39164, 39165],
  "do": "send_invitation"
}
```

This will return `201 Created` with the current JSON representation of the user if the creation was a success.

Create user
--------------

* `POST /locations/64/users.json` will create a new user from the parameters passed.


```json
{
  "first_name": "Peter",
  "last_name": "Quill",
  "department_ids": [39164, 39165]
}
```

This will return `201 Created` with the current JSON representation of the user if the creation was a success.



Update user
--------------

* `PUT /locations/64/users/83959.json` will update the user from the parameters passed.

```json
{
  "max_vacation_days": 30,
  "max_hours_per_month": 36,
  "gender": "male",
  "time_zone": "Europe/Berlin",
  "role": "staff",
  "company": "Easypep",
  "street": "Neuer Kamp 30",
  "additional_street": "",
  "zip": "20357",
  "city": "Hamburg",
  "country": "Germany",
  "locale": "de",
  "email": "admin+withinvitation@easypep.de",
  "first_name": "Nova",
  "last_name": "Prime",
  "phone_number_mobile": "231/48376616312",
  "phone_number_office": "231/48376616312",
  "commentable": "true",
  "attachable": "true"
}
```

Lock user
--------------

* `PUT /locations/64/users/83959.json` will lock the user

```json
{
  "do": "lock"
}
```

Unlock user
--------------

* `PUT /locations/64/users/83959.json` will lock the user

```json
{
  "do": "unlock"
}
```

Delete user
--------------

* `DELETE /locations/64/users/83959.json`
