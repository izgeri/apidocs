## Show [/api/pubkeys/{login}/]

### Show keys for a user [GET]

Lists all public keys uploaded for a specific user. No authentication or authorization is required to show public keys.

If the user is unknown or has no public keys in Conjur, the response is an empty string.

**Response**

|Code|Description|
|----|-----------|
|200|Public key list in authorized_keys format (one key per line)|

+ Parameters
    + login: alice (string) - The user's login name

+ Response 200 (text/html;charset=utf-8)

    ```
    ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDFDhYPIMHAqlQghhdmEa98UrfK9HBX8AaW4aSj5sVwigy7wFMs9yjPfK/mGOV5T5g5TuSe8EQfRfX4Mp6yv40ta4ETAJti7cjoh8KwkxnKPUQmhkgWmTJRfwUwYq12yzmqFp7nZ6JNfng39TvD+L6McpFgC+O7O3IeGBHSz8PB6QE7TbvICSbOPU43d1MQpsvtbgIAM6rTC44JAPor9YoHSne1dsaNCsu4xFUXROJpD2V6eSRHw8tpN6vzxgym5ZDRMCWPhhN82xmEwPFt6qi6nN5ky0qTzPtJhsTu0dPjyJbgLfyFOu/iPTPHi9oWXuMJpwry9cMTG/wcAR8JG5lJ alice@bigcorp.com
    ```
