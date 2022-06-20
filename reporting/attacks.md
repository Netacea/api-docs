# Attacks

Returns an array of the latest 100 lines of attack data for a given domain

**URL** : `/domain/{domainID}/attacks`

**Method** : `GET`

**Auth required** : YES

**Permissions required** : Vendor

## Success Response

**Code** : `200 OK`

**Content example**

```json
[
    {
        "id": "b634ca9a-4c21-4f96-b112-b4e460a9cdb5",
        "label": "checkout",
        "end_time": "2022-06-08T09:40:00.003Z",
        "start_time": "2022-06-08T01:40:00.004Z",
        "total_attack_requests": 610477,
        "total_requests_mitigated": 602380
    }
]
```

## Notes

* **This is a mock endpoint which returns an array of 100 examples of random attack data**