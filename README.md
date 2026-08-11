# FFxAPI Like API

Flask-based API for sending likes with rotating or random token batches.

## Features

- Like API endpoint
- API Key protection
- Supports IND, BD, BR servers
- Rotating token batches
- Random token batches
- Profile checking before and after likes

---

# Installation

```bash
pip install flask requests aiohttp pycryptodome protobuf urllib3
```

---

# File Structure

```text
.
├── app.py
├── like_pb2.py
├── like_count_pb2.py
├── uid_generator_pb2.py
└── README.md
```

---

# Start Server

```bash
python app.py
```

Server:

```text
http://0.0.0.0:1000
```

---

# Like Endpoint

```http
GET /like
```

Parameters:

| Parameter | Required |
| ---------- | ---------- |
| uid | Yes |
| server_name | Yes |
| api_key | Yes |

Example:

```text
http://localhost:1000/like?uid=123456789&server_name=IND&api_key=YOUR_API_KEY
```

---

# Random Batch Mode

```text
&random=true
```

Example:

```text
http://localhost:1000/like?uid=123456789&server_name=IND&random=true&api_key=YOUR_API_KEY
```

---

# Token Information Endpoint

```http
GET /token_info
```

Example:

```text
http://localhost:1000/token_info
```

Response:

```json
{
    "IND": {
        "regular_tokens": 500,
        "visit_tokens": 500
    },
    "BD": {
        "regular_tokens": 400,
        "visit_tokens": 400
    }
}
```

---

# API Key

Default:

```text
YOUR_API_KEY
```

Header:

```http
X-API-KEY: YOUR_API_KEY
```

Or:

```text
?api_key=YOUR_API_KEY
```

---

# Supported Servers

| Server |
|----------|
| IND |
| BD |
| BR |
| US |
| SAC |
| NA |

---

# Credit and Support

```text
FFxAPI
https://t.me/Owner_Of_BSG
```
