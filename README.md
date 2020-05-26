

## How to use

### Creating a session

POST .../api/v1/session

Request:
```json
{
    "name": "Lunch at Alberto's",
    "description": "A poll to decide if we lunch at Alberto's House",
    "votingStartDate": "2020-01-01T11:00:00",
    "votingEndDate": "2020-01-01T11:30:00"
}
```

Response: HTTP 201
```json
{
    "id": 1,
    "name": "Lunch at Alberto's",
    "description": "A poll to decide if we lunch at Alberto's House",
    "votingStartDate": "2020-01-01T11:00:00",
    "votingEndDate": "2020-01-01T11:30:00"
}
```

### Requesting session info

GET .../api/v1/session/<session-id>

Response: HTTP 200
```json
{
    "id": 1,
    "name": "Lunch at Alberto's",
    "description": "A poll to decide if we lunch at Alberto's House",
    "votingStartDate": "2020-01-01T11:00:00",
    "votingEndDate": "2020-01-01T11:30:00",
    "voteCount": {
        "yes": 6,
        "no": 2
    }
}
```


### Voting

POST .../api/v1/vote

Request:
```json
{
    "sessionId": 1,
    "vote": true
}
```

Response: HTTP 201
```json
{
    "message": "Vote created"
}
```