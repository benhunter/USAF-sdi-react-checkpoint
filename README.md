# USAF-sdi-react-checkpoint

# API Routes

GET `/emails`:
```
    {
      "sender": "katie@galvanize.com",
      "recipient": "jane@galvanize.com" ,
      "subject": "Standup meeting",
      "message": "Mr. and Mrs. Dursley, of number four, Privet Drive, were
        proud to say that they were perfectly normal, thank you very much.",
      "date": "2020-08-23T18:25:43.511Z",
      "id": 1
    }
```

GET `/emails/:id`:

e.g. `/emails/1`:

```
    {
      "sender": "katie@galvanize.com",
      "recipient": "jane@galvanize.com" ,
      "subject": "Standup meeting",
      "message": "Mr. and Mrs. Dursley, of number four, Privet Drive, were
        proud to say that they were perfectly normal, thank you very much.",
      "date": "2020-08-23T18:25:43.511Z",
      "id": 1
    }
```

GET `/search` with URI query:

e.g. `/search?query=meeting`:

```
    {
      "sender": "jean-marc@galvanize.com", "recipient": "jane@galvanize.com" ,
      "subject": "Retro meeting",
      "message": "They were the last people you’d expect to be involved
        in anything strange or mysterious, because they just didn’t hold with such nonsense.",
      "date": "2020-04-23T18:25:43.511Z",
      "id": 2},
```

POST `/send`:

```
  {
    "sender": String,
    "recipient": String,
    "subject": String,
    "message": String,
    "date": Date,
    "id": Number
  }
```

  # Resources:

  ## Command: curl

 The command `curl` stands for `client url`, and is a command that can be used to hit and endpoint.  For example - to hit the main google page:
 
 ```
 curl http://www.google.com
 ```

Below is an example of a POST call to the email endpoint:
  ```
   curl -d '{"sender": "string","recipient": "string","subject":"string","message": "string","date": "04/11/1982","id": 4001}' -H 'Content-Type: application/json' localhost:3001/send
```

Here is a summary of the arguments: 
1. `-d` is shorthand for `--data`, and can represent the json you are POSTing to the API in the body.
1. `-H` flag allows you to specify the content-type being sent in the body.  In our case that would be `'Content-Type: application/json'`.
1. The final argument is the url you are trying to hit: `localhost:3001/send`

...and you should see a response like this:
```
{"status":"success","message":"The message was successfully sent"}
```