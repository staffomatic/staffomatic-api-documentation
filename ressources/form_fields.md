Form Fields
=======================

Get form_fields
----------

* `GET /users/493/form_fields.json` will return all form_fields for user 493

```json
[
   {
      "created_at":"2014-10-07T11:02:51+02:00",
      "updated_at":"2015-02-10T15:21:54+01:00",
      "id":149328,
      "field_type":"string",
      "name":"fun factor",
      "field_options":[],
      "value":"100%",
      "position":null
   }
]
```

Get form_field
----------

* `GET /users/493/form_fields/304129.json` will return the specified form_field.

```json
{
  "created_at":"2014-10-07T11:02:51+02:00",
  "updated_at":"2015-02-10T15:21:54+01:00",
  "id":149328,
  "field_type":"string",
  "name":"fun factor",
  "field_options":[],
  "value":"100%",
  "position":null
}
```

Update form_field
--------------

* `PUT /users/493/form_fields/304129.json` will update the form_field from the parameters passed.

```json
{
  "id":149328,
  "name":"fun factor",
  "value":"110%!!!"
}
```
