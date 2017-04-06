# Errors

The BLACK<strong>BX</strong> API uses the following error codes and each, have a default message:


Error Code | Message
---------- | -------
200 | OK
201 | Created
202 | Accepted
203 | Non Authoritive Information
204 | No Content
205 | Reset Content
206 | Partial Content
301 | Moved Permanently
302 | Found
307 | Temporary Redirect
308 | Permanent Redirect
400 | Bad Request
401 | Unauthorized
402 | Payment Required
403 | Forbidden
404 | Not Found
405 | Method Not Allowed
406 | Not Acceptable
407 | Proxy Authentication Required
408 | Request Time Out
409 | Conflict
410 | Gone
411 | Length Required
412 | Precondition Required
413 | Payload Too Large
414 | URI Too Long
415 | Unsupported Media Type
416 | Range Not Satisfiable
417 | Exception Failed
421 | Misdirect Request
428 | Precondition Required
429 | Too Many Requests
500 | Internal Server Error
501 | Not Implemented Yet
503 | Service Unavailable
504 | Gateway Timeout

The default message can be replaced by calling 
```php
	Http::status(statusCode, message: $request)
```
