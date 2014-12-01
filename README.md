The New STAFFOMATIC API
=======================

The all-new STAFFOMATIC has an all-new API. This is a REST-style API that uses JSON for serialization and OAuth 2 for authentication.

STAFFOMATIC vs. EASYPEP
-----------------------

*EASYPEP* is our german speaking brand, *STAFFOMATIC* the international version. You can choose between those two  API enpoints `https://api.easypepapp.com` or `https://api.staffomaticapp.com`


Making a request
----------------

All URLs start with `http://api.easypepapp.com/v3/demo` or `http://api.staffomaticapp.com/v3/demo`. SSL only. The path is postfix with the API version and account subdomain. If we change the API in backward-incompatible ways, we'll bump the version marker and maintain stable support for the old URLs.

To make a request for all the locations on your account, you'd append the locations index path to the base url to form something like `http://api.staffomaticapp.com/v3/demo/locations.json`. In curl, that looks like:

```shell
curl -u email:password http://api.staffomaticapp.com/v3/demo/locations.json
```


To create something, it's the same deal except you also have to include the Content-Type header and the JSON data:

```shell
curl -u email:password \
  -H 'Content-Type: application/json' \
  -d '{ "name": "My new project!" }' \
  http://api.staffomaticapp.com/v3/demo/locations.json
```

That's all!

Authentication
-----------------------

If you're making a private integration with STAFFOMATIC for your own purposes, you can use HTTP Basic authentication. This is secure since all requests in the new STAFFOMATIC use SSL.

If you're making a public integration with STAFFOMATIC for others to enjoy, you must use OAuth 2. This allows users to authorize your application to use STAFFOMATIC on their behalf without having to copy/paste API tokens or touch sensitive login info.

Read the authentication guide to get started.


No XML, just JSON
-----------------------

We only support JSON for serialization of data. Our format is to have no root element and we use snake_case to describe attribute keys. This means that you have to send `Content-Type: application/json; charset=utf-8` when you're POSTing or PUTing data into Basecamp. **All API URLs end in .json to indicate that they accept and return JSON.**

You'll receive a 415 Unsupported Media Type response code if you attempt to use a different URL suffix or leave out the `Content-Type` header.

Pagination
-----------------------

Most collection APIs paginate their results. The first request returns up to 50 records. Check the next page for more results by adding &page=2, then &page=3, and so on until you get an empty response.


Use HTTP caching
-----------------------

You must make use of the HTTP freshness headers to lessen the load on our servers (and increase the speed of your application!). Most requests we return will include an ETag or Last-Modified header. When you first request a resource, store this value, and then submit them back to us on subsequent requests as If-None-Match and If-Modified-Since. If the resource hasn't changed, you'll see a 304 Not Modified response, which saves you the time and bandwidth of sending something you already have.


Handling errors
-----------------------

If STAFFOMATIC is having trouble, you might see a 5xx error. 500 means that the app is entirely down, but you might also see 502 Bad Gateway, 503 Service Unavailable, or 504 Gateway Timeout. It's your responsibility in all of these cases to retry your request later.


Rate limiting
-----------------------

You can perform up to 500 requests per 10 second period from the same IP address for the same account. If you exceed this limit, you'll get a 429 Too Many Requests response for subsequent requests. Check the Retry-After header to see how many seconds to wait before retrying the request.

API ready for use
-----------------------

* [absence_types](https://github.com/staffomatic/staffomatic-api-documentation/blob/master/ressources/absence_types.md)
* [absences](https://github.com/staffomatic/staffomatic-api-documentation/blob/master/ressources/absences.md)
* [account](https://github.com/staffomatic/staffomatic-api-documentation/blob/master/ressources/account.md)
* [applications](https://github.com/staffomatic/staffomatic-api-documentation/blob/master/ressources/applications.md)
* [departments](https://github.com/staffomatic/staffomatic-api-documentation/blob/master/ressources/departments.md)
* [locations](https://github.com/staffomatic/staffomatic-api-documentation/blob/master/ressources/locations.md)
* [schedules](https://github.com/staffomatic/staffomatic-api-documentation/blob/master/ressources/schedules.md)
* [shifts](https://github.com/staffomatic/staffomatic-api-documentation/blob/master/ressources/shifts.md)
* [users](https://github.com/staffomatic/staffomatic-api-documentation/blob/master/ressources/users.md)

API libraries
-----------------------
* [staffomatic.rb](https://github.com/staffomatic/staffomatic.rb)


Help us make it better
-----------------------

Please tell us how we can make the API better. If you have a specific feature request or if you found a bug, please use GitHub issues. Fork these docs and send a pull request with improvements.
