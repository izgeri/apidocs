## Add Host [/api/layers/{id}/hosts/{?hostid}]

### Add a host to a layer [POST]

Adds a new host to an existing layer. The host will assume all privileges of the layer.

This operation is idempotent: if the host is already in the layer, adding it again will do nothing.

Both `id` and `hostid` must be query-escaped: `/` -> `%2F`, `:` -> `%3A`.

---

:[conjur_auth_header_table](partials/conjur_auth_header_table.md)


**Response**

|Code|Description|
|----|-----------|
|200|Host added to the layer|
|403|Permission denied|
|404|Existing layer or host not found|

+ Parameters
    + id: jenkins%2Fslaves (string) - ID of the layer, query-escaped
    + hostid: demo%3Ahost%3Aslave01 (string) - Fully qualified ID of the host to add, query-escaped

+ Request (application/json)
    :[conjur_auth_header_code](partials/conjur_auth_header_code.md)

+ Response 200 (application/json)

    ```
    {
      "id": "jenkins/slaves",
      "userid": "demo",
      "ownerid": "demo:group:ops",
      "roleid": "demo:layer:jenkins/slaves",
      "resource_identifier": "demo:layer:jenkins/slaves",
      "hosts": [
        "demo:host:slave01"
      ]
    }
    ```