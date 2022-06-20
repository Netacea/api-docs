# Audit Trail

Returns an array of the latest 100 lines of audit trail data for a given domain

**URL** : `/domain/{domainID}/audit-trail`

**Method** : `GET`

**Auth required** : YES

**Permissions required** : Vendor

## Success Response

**Code** : `200 OK`

**Content example**

```json
[
    {
        "change": "Removed datacenter from Captcha",
        "item": "anotherrandomDC",
        "reason": "Expired",
        "timestamp": "2022-06-09T09:00:05.042Z",
        "user": "Automated Policy"
    }
}
```

## Notes

* **This is a mock endpoint which returns an array of 100 examples of random audit trail data**