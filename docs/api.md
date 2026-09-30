# API Reference

NexusFlag provides a lightweight RESTful API to manage event challenges, player sessions, and real-time flag submissions.

---

## Base URL

All API requests should be directed to your hosted instance base URL:

```text
http://<your-server-ip>:<port>/api/v1
```

## Authentication

All protected endpoints require authentication using a Bearer token. You must include the token in the Authorization header of your HTTP requests:

- Header Name: Authorization
- Header Value: Bearer <your_access_token>

## Endpoints Summary

Below is a quick reference table of all available API endpoints:

| Method | Endpoint | Description | Auth Required |
| :--- | :--- | :--- | :--- |
| `POST` | `/auth/login` | Authenticate player and issue token | No |
| `GET` | `/challenges` | Retrieve a list of active challenges | Yes |
| `GET` | `/challenges/{id}` | Get specific challenge details | Yes |
| `POST` | `/challenges/submit` | Submit a flag for validation | Yes |
| `GET` | `/scoreboard` | Retrieve current event rankings | No |

## Detailed Endpoints Reference

### Authenticate Player

Obtain an access token by submitting team/player credentials.

- URL: `/auth/login`
- Method: `POST`
- Content-Type: `application/json`

Request Body:

```json
{
  "username": "cyber_ninja",
  "password": "secure_password123"
}
```

Response (200 OK):

```json
{
  "access_token": "nf_token_9f8d7c6b5a4321",
  "token_type": "bearer",
  "expires_in": 86400
}
```

### List All Challenges

Retrieve all available challenges grouped or listed for the current event.

- URL: `/challenges`
- Method: `GET`
- Headers: `Authorization: Bearer <token>`

Response (200 OK):

```json
[
  {
    "id": 1,
    "title": "Baby's First RSA",
    "category": "Crypto",
    "points": 100,
    "solved_count": 42
  },
  {
    "id": 2,
    "title": "Hidden in Plain Sight",
    "category": "Steganography",
    "points": 250,
    "solved_count": 12
  }
]
```

### Get Challenge Details

Fetch full description, hints, and parameters for a specific challenge.

- URL: `/challenges/{id}`
- Method: `GET`
- Headers: `Authorization: Bearer <token>`

Response (200 OK):

```json
{
  "id": 1,
  "title": "Baby's First RSA",
  "category": "Crypto",
  "points": 100,
  "description": "We intercepted this encrypted message using a weak public exponent. Can you decrypt it?",
  "files": [
    "[https://example.com/downloads/rsa_chall.zip](https://example.com/downloads/rsa_chall.zip)"
  ],
  "hints": [
    "Look up small e padding attacks."
  ]
}
```

### Submit Flag

Submit a flag attempt for a specific challenge.

- URL: `/challenges/submit`
- Method: `POST`
- Headers: `Authorization: Bearer <token>`
- Content-Type: `application/json`

Request Body:

```json
{
  "challenge_id": 1,
  "flag": "FLAG{rsa_is_easy_when_e_is_small}"
}
```

Response (200 OK - Correct Flag):

```json
{
  "correct": true,
  "message": "Correct flag! Points awarded.",
  "new_score": 350
}
```

Response (400 Bad Request - Incorrect Flag):

```json
{
  "correct": false,
  "message": "Incorrect flag. Try again!"
}
```

### Get Scoreboard

Retrieve the current public scoreboard rankings.

- URL: `/scoreboard`
- Method: `GET`
- Auth Required: No

Response (200 OK):

```json
[
  {
    "rank": 1,
    "team_name": "BitShift",
    "score": 1450,
    "last_solve": "2026-06-06T14:22:10Z"
  },
  {
    "rank": 2,
    "team_name": "NullPointer",
    "score": 1200,
    "last_solve": "2026-06-06T13:10:45Z"
  }
]
```
