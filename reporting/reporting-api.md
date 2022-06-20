# Reporting API (Alpha)

Please Note: **the Reporting API is currently in alpha and is available as a mock only. Changes may still occur**

Alpha domain URL (Mock only):

`https://reporting.api.dev-red.netacea.cloud`

## Authentication

Closed endpoints require a valid api kay to be included in the header of the request.

### Vendor API Key

For Vendor access, a valid Vendor Api Key should be provided in the header of a request.

```
X-Vendor-Api-Key
```

**CURL example:**

```bash
curl --header "X-Vendor-Api-Key: 9ca82657-e815-45df-b7eb-722b55267481" https://reporting.api.dev-red.netacea.cloud/domain/e96e6ef1-6763-4bc9-b2a1-0a038c54a235/dashboards
```

A valid API Key will be provided by netacea, please contact netacea for more information.

## Data Endpoints

### Endpoints for accessing data:

* [Audit Trail](#audit-trail) : `GET /domain/{domainID}/audit-trail`
* [Attacks](#attacks) : `GET /domain/{domainID}/attacks`
* **Coming Soon** [Attack](#attack) : `GET /domain/{domainID}/attacks/{attackID}`

### QuickSight Embed Endpoints

* [Dashboards](#dashboards) : `GET /domain/{domainID}/dashboards`
* [Dashboard Embed](#dashboard-embed) : `GET /domain/{domainID}/dashboards/{dashboardID}`

---

## Audit Trail

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
]
```

### Notes

* **This is a mock endpoint which returns an array of 100 examples of random audit trail data**

---

## Attacks

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

### Notes

* **This is a mock endpoint which returns an array of 100 examples of random attack data**

---

## Attack

**Coming Soon**

Returns an object with data related to a single attack

**URL** : `/domain/{domainID}/attacks/{attackID}`

**Method** : `GET`

**Auth required** : YES

**Permissions required** : Vendor

## Success Response

**Code** : `200 OK`

<!-- **Content example**

```json

``` 

### Notes

* **This is a mock endpoint which return an example of a single attack**

-->

---

## Dashboards

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

### Notes

* This is an example endpoint, which returns a list of dashboards from an example account

---

## Dashboard Embed

Returns a embed url for a QuickSight dashboard available for a given domain

**URL** : `/domain/{domainID}/dashboards/{dashboardID}`

**Method** : `GET`

**Auth required** : YES

**Permissions required** : Vendor

## Success Response

**Code** : `200 OK`

**Content example**

```json
{
    "embed_url": "https://eu-west-1.quicksight.aws.amazon.com/embed/139a34f5cf964c418548bafa5616e261/dashboards/feb49339-2583-4bf8-86e1-f855ac1e6e6a?code=AYABeIkvPlIiGPf7XGl9IVlv1U0AAAABAAdhd3Mta21zAEthcm46YXdzOmttczpldS13ZXN0LTE6MzU2MzA1MTgzMDczOmtleS83ZTYwMTNkMC0xM2I0LTRmODItYmI1NC00YjllMTM4NzczNjYAuAECAQB4mmfdaL-WJblO_x3fgpluVFAFiuT29EIrIJ6BR4V1br8BO1HV4q_WY5p9Gs21CBYEaQAAAH4wfAYJKoZIhvcNAQcGoG8wbQIBADBoBgkqhkiG9w0BBwEwHgYJYIZIAWUDBAEuMBEEDFXG5Xf9wRfyKe5whQIBEIA7I2IudP7byOfV4cNpGsknnpEpVnLzaoJPZAYxjvTN59keZCWkj1tXcedK5AiIF55pTm4SSW0CI-cqqaoCAAAAAAwAABAAAAAAAAAAAAAAAAAAEI3hGAEtKi6yopiYzjf1rP____8AAAABAAAAAAAAAAAAAAABAAAA5bgINEGlJ0CeaZhdbLcxj1IJFqkka7YCEtJjXJsYm6IEw9Yhhkof3Aijp1jOOcHu9QXPdObjFlfw4jOCqxyvLC8hsNnPMRKJf5XkPVG8mPtZoAJDXEAEvw0xMe-op0mGPRNOmQmt0862V7dBTSHnSbVNvapMiJgcrQ9B_mxXNQHrv2rsGsGs1tFhCvZLQDZALHLsP3dsBFN3cHD5URAZcLYPo-YZCkbpM0ABgQwYxwgWVQdYwU4nAGwnBwRRpzx2WyzOnuF-eUtnR1ALuhQ4a3GkB5ejTSResRw7QrLz9Wrw5ikl79FgvknltHry27SHLJuV_7Pb&identityprovider=quicksight&isauthcode=true"
}
```

### Notes

* An vanilla javascript example of embedding can be found [here](dashboard-embed.html)
* To embed a dashboard a valid HTTPS domain must be used and these must be added to QuickSight. Please request to add a domain by contacting netacea. Domains can be added to auto include subdomains