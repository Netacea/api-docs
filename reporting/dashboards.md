# Dashboards

Returns a array of QuickSight dashboards available for a given domain

**URL** : `/domain/{domainID}/dashboards`

**Method** : `GET`

**Auth required** : YES

**Permissions required** : Vendor

## Success Response

**Code** : `200 OK`

**Content example**

```json
[
    {
        "id": "feb49339-2583-4bf8-86e1-f855ac1e6e6a",
        "name": "example-dashboard"
    }
]
```

## Notes

* This is an example endpoint, which returns a list of dashboards from an example account