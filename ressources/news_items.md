News Items
=======================

Get news items
----------

* `GET /locations/64/news_items.json` will return all news_items

```json
[
  {
    created_at: "2014-11-24T22:41:57+01:00",
    updated_at: "2014-11-24T23:06:58+01:00",
    id: 14013,
    title: "corrupti facere a sed. Provident, sequi.",
    body: "<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Accusamus dicta fugit corporis doloremque maxime soluta dolorum ex, reprehenderit itaque, recusandae blanditiis debitis saepe distinctio, corrupti facere a sed. Provident, sequi.</p> ",
    author_id: 493,
    department_id: null,
    location_id: 64,
    attachment_url: "https://api.staffomaticapp.com/attachments/original/missing.png",
    attachment_name: null,
    send_to_all_locations: false,
    user_ids: [791],
    comments_count: 12,
    attachments_count: 12,
    commentable: true,
    attachable: true
  }
]
```

Get news item
----------

* `GET /locations/64/news_items.json` will return the specified news item       .

```json
{
    created_at: "2014-11-24T22:41:57+01:00",
    updated_at: "2014-11-24T23:06:58+01:00",
    id: 14013,
    title: "corrupti facere a sed. Provident, sequi.",
    body: "<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Accusamus dicta fugit corporis doloremque maxime soluta dolorum ex, reprehenderit itaque, recusandae blanditiis debitis saepe distinctio, corrupti facere a sed. Provident, sequi.</p> ",
    author_id: 493,
    department_id: null,
    location_id: 64,
    attachment_url: "https://api.staffomaticapp.com/attachments/original/missing.png",
    attachment_name: null,
    send_to_all_locations: false,
    user_ids: [791],
    comments_count: 12,
    attachments_count: 12,
    commentable: true,
    attachable: true
}
```

Create news item
--------------

* `POST /locations/64/news_items.json` will create a new news item from the parameters passed.

```json
{
  "title": "Lorem ipsum dolor sit amet",
  "body": "consectetur adipisicing elit.",
  "send_to_all_locations": false,
  "user_ids": ["791","493"],
  "commentable": true,
  "attachable": true
}
```

This will return `201 Created` with the current JSON representation of the news item if the creation was a success.


Update news item
--------------

* `PUT /locations/64/news_items/83959.json` will update the news item from the parameters passed.

```json
{
  "user_ids": ["493"]
}
```

Delete news item
--------------

* `DELETE /locations/64/news_items/83959.json`
