# JSON API
- /__self__
	- /photos
- /member/ID
	- /photos/1
- /member/ID/__related__
	- /photos/1/comments
- /member/ID/__self__
	- /photos/1/relationships/comments

[reference](http://jsonapi.org/recommendations/)

---

# Naming
- start, end __a~z__
- char accept __a~z, -, 0~9__

---

# Filter
> GET /comments?filter[post]=1,2&filter[author]=12 HTTP/1.1

---

# __self__ - get whole response

```
GET /comments HTTP/1.1

{
  "data": [{
      "type": "comments",
      "id": "1",
      "attributes": {
          "text": "HATEOS are the thing!"
      },
      "links": {
          "self": "/comments/1"
      },
      "relationships": {
        "author": {
          "links": {
            "self": "/comments/1/relationships/author",
            "related": "/comments/1/author"
          }
        },
        "articles": {
          "links": {
            "self": "/comments/1/relationships/articles",
            "related": "/comments/1/articles"
          }
        }
      }
  }],
  "links": {
      "self": "/comments"
  }
```

---

# HTTP Verbs

- GET
- POST - create new one
- PUT - __replace__ as this one
- PATCH - __modify__ as folowing parameters
- DELETE  

> Old browser, such as IE8, implement by __POST__ action with header __X-HTTP-Method-Override: PATCH__


---

# Response when Async

>
HTTP/1.1 __202 Accepted__
Content-Type: application/vnd.api+json
Content-Location: https://example.com/photos/queue-jobs/5234

{
  "data": {
    "type": "__queue-jobs__",
    "id": "5234",
    "attributes": {
      "status": "Pending request, waiting other process"
    },
    "links": {
      "self": "/photos/__queue-jobs__/5234"
    }
  }
}

---

# Queue status
- query
>>>
	GET /photos/__queue-jobs__/5234 HTTP/1.1
	Accept: application/vnd.api+json  

- complete response
>>>
	HTTP/1.1 __303 See other__
	Content-Type: application/vnd.api+json
	Location: https://example.com/photos/4577
