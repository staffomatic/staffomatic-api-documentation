Notification Settings
=======================

Get notification settings for user
----------

* `GET /users/493/notification_settings.json` will return all notification_settings

```json
[
  {
    "id": "schedule",
    "value": false
  },
  {
    "id": "application",
    "value": true
  },
  {
    "id": "absence",
    "value": true
  },
  {
    "id": "news_item",
    "value": true
  }
]
```

Update notification settings for user
--------------

* `PUT /users/493/notification_settings/schedule.json` will update the schedule settings from the parameters passed.

```json
{
  "id": "schedule",
  "value": false
}
```

* `PUT /users/493/notification_settings/application.json` will update the application settings from the parameters passed.

```json
{
  "id": "application",
  "value": false
}
```

* `PUT /users/493/notification_settings/absence.json` will update the absence settings from the parameters passed.

```json
{
  "id": "absence",
  "value": false
}
```

* `PUT /users/493/notification_settings/news_item.json` will update the news_item settings from the parameters passed.

```json
{
  "id": "news_item",
  "value": false
}
```
