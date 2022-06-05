# Brightsign API Notes and Example Calls (Personal Use)

## Install Pre-requisitites

Ensure you have the needed tools:

```bash
sudo apt install -y curl jq direnv
```

## Configuration

Copy the file "envrc" to ".envrc" and then edit it to insert your BSN.cloud username, password, network name, client id, and secret.  The last two you will need to ask Brightsign support for. 

```bash
direnv allow
```

Now, when you enter this folder you will set the environment variables.

## Getting a Bearer Token

The script get-token will use the environment variables to make a call to the "token" endpoint to fecth a bearer token that can then be used to authenticate API calls.

```bash
./get-tokens
{
  "token_type": "bearer",
  "access_token": "this-is-not-a-real-token-cQwVKeq6FGXvLmrn7CQsPFstDXQWlSCXQwHz1qTEVRGhJpIgB9n8kCkGdJXcvegA1D",
  "refresh_token": ""this-is-not-a-real-token-3aaEzWgOm8N9AaacSdD1GCZx10iiGImYUk5fM4KMuSrMAVCNRuyZGpXG0I56T2DSG",
  "expires_in": 899,
  "person": {
    "id": 12345,
    "login": "gherlein@somewhere.com",
    "firstName": "Greg",
    "lastName": "Herlein",
    "users": [
      {
        "id": 12345,
        "role": {
          "id": 1,
          "name": "Administrators"
        },
        "status": "Enabled",
        "network": {
          "id": 12345,
          "name": "SomeTest",
          "status": "Active",
          "subscription": {
            "level": "Trial",
            "startDate": "2022-05-25T00:36:42.127Z",
            "endDate": "2022-06-24T00:36:42.12Z"
          }
        }
      }
    ]
  },
  "scope": "bsn.api.self",
  ".issued": "Sun, 05 Jun 2022 17:12:01 GMT",
  ".expires": "Sun, 05 Jun 2022 17:27:01 GMT"
}
```
NOTE: the data was obscured for security reasons.


