## Show [/api/authz/{account}/resources/{kind}/{id}/]

### Retrieve a resources's record [GET]

Retrieves a resource's metadata, including annotations.

**Permission Required**

`read` permission on the resource.

---

:[conjur_auth_header_table](partials/conjur_auth_header_table.md)

**Response**

|Code|Description|
|----|-----------|
|200|The response body contains the resource's record|
|403|You don't have permission to view the record|
|404|No record exists with the given ID|

+ Parameters
    + account: conjur (string) - organization account name
    + kind: variable_group (string) - kind of the resource, for example 'variable' or 'host'
    + id: aws_keys (string) - ID of the resource to show

+ Request
    :[conjur_auth_header_code](partials/conjur_auth_header_code.md)

+ Response 200 (application/json; charset=utf-8)

    ```
    {
      "id": "conjur:variable_group:aws_keys",
      "owner": "conjur:group:ops",
      "permissions": [],
      "annotations": []
    }
    ```