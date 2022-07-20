# Reporting API (Beta)

[![version](https://img.shields.io/badge/version-0.1.0--beta-yellow.svg)](https://semver.org)

Please Note: **the Reporting API is currently in beta. Changes may still occur**

To view the changelog please see [here](CHANGELOG.md)

Beta domain URL:

`https://reporting.api.uat.netacea.cloud`

## Authentication

Closed endpoints require a valid api kay to be included in the header of the request.

### Vendor API Key

For Vendor access, a valid Vendor Api Key should be provided in the header of a request.

```
X-Vendor-Api-Key
```

**CURL example:**

```bash
curl --header "X-Vendor-Api-Key: 9ca82657-e815-45df-b7eb-722b55267481" https://reporting.api.uat.netacea.cloud/domains/e96e6ef1-6763-4bc9-b2a1-0a038c54a235/dashboards
```

A valid API Key will be provided by netacea, please contact netacea for more information.

## Data Endpoints

### Endpoints for accessing data:

* **Coming Soon** [Audit Trail](#audit-trail) : `GET /domains/{domainID}/audit-trail`
* [Attacks](#attacks) : `GET /domains/{domainID}/attacks`
* [Attack](#attack) : `GET /domains/{domainID}/attacks/{attackID}`

### QuickSight Embed Endpoints

* [Dashboards](#dashboards) : `GET /domains/{domainID}/dashboards`
* [Dashboard Embed](#dashboard-embed) : `GET /domains/{domainID}/dashboards/{dashboardID}`

---

## Audit Trail (Coming Soon)

Returns an array of the latest 100 lines of audit trail data for a given domain

**URL** : `/domains/{domainID}/audit-trail`

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

* **The endpoint is in production and will be available soon**

---

## Attacks

Returns an array of the latest 100 lines of attack data for a given domain

**URL** : `/domains/{domainID}/attacks`

**Method** : `GET`

**Auth required** : YES

**Permissions required** : Vendor

## Success Response

**Code** : `200 OK`

**Content example**

```json
[
    {
        "id": "cdd1f2f1-71ff-4a58-96bf-79e879ec6949",
        "start_time": "2022-07-18T02:10:00.005Z",
        "end_time": "2022-07-18T03:10:00.005Z",
        "total_requests_mitigated": 61301,
        "total_attack_requests": 65872,
        "type": "Credential Stuffing"
    },
]
```

### Notes

---

## Attack

Returns an object with data related to a single attack

**URL** : `/domains/{domainID}/attacks/{attackID}`

**Method** : `GET`

**Auth required** : YES

**Permissions required** : Vendor

## Success Response

**Code** : `200 OK`

```json
{
    "id": "7f7a9b3c-f144-48b3-85d8-0e2d351c59a1",
    "start_time": "2022-07-15T08:18:00.003Z",
    "end_time": "2022-07-15T11:18:00.004Z",
    "date_created": "2022-07-15T11:18:00.072Z",
    "total_requests": 183420,
    "total_requests_mitigated": 170581,
    "total_requests_unmitigated": 12839,
    "top_ips": [
        {
            "key": "162.9.0.10",
            "doc_count": 150
        },
        {
            "key": "202.4.245.38",
            "doc_count": 153
        },
        {
            "key": "202.4.240.109",
            "doc_count": 388
        },
        {
            "key": "182.219.226.192",
            "doc_count": 593
        },
        {
            "key": "12.4.122.16",
            "doc_count": 774
        },
        {
            "key": "16.106.107.220",
            "doc_count": 809
        },
        {
            "key": "169.167.169.145",
            "doc_count": 1121
        },
        {
            "key": "172.12.12.252",
            "doc_count": 1125
        },
        {
            "key": "182.91.251.2",
            "doc_count": 1396
        },
        {
            "key": "12.4.122.16",
            "doc_count": 1467
        }
    ],
    "top_datacentres": [
        {
            "key": "Alphabet.z",
            "doc_count": 166
        },
        {
            "key": "Googolplex Solutions",
            "doc_count": 462
        },
        {
            "key": "Digital Puddle",
            "doc_count": 766
        },
        {
            "key": "Microsoft Plc",
            "doc_count": 768
        },
        {
            "key": "Golf Web Services",
            "doc_count": 772
        },
        {
            "key": "Indigo Web Services",
            "doc_count": 807
        },
        {
            "key": "Beta Web Services",
            "doc_count": 1063
        },
        {
            "key": "Hotel Web Services",
            "doc_count": 1520
        },
        {
            "key": "Alpha",
            "doc_count": 1526
        },
        {
            "key": "Money Web Services",
            "doc_count": 1577
        }
    ],
    "top_countries": [
        {
            "key": "Taiwan",
            "doc_count": 85435
        },
        {
            "key": "Singapore",
            "doc_count": 85436
        }
    ],
    "top_paths": [
        {
            "key": "/clothing/mens/shoes",
            "doc_count": 24029
        },
        {
            "key": "/clothing/women",
            "doc_count": 32038
        },
        {
            "key": "/clothing/men",
            "doc_count": 42717
        },
        {
            "key": "clothing/mens/shoes/prices",
            "doc_count": 72087
        }
    ],
    "top_user_agents": [
        {
            "key": "Mozilla/5.0 (compatible, MSIE, Windows NT; Trident; rv) like Gecko",
            "doc_count": 233
        },
        {
            "key": "Mozilla/5.0 (Windows NT; Win64; x64) AppleWebKit (KHTML, like Gecko) Chrome Safari",
            "doc_count": 302
        },
        {
            "key": "Pesky Password Pincher",
            "doc_count": 336
        },
        {
            "key": "Account Snatcher 3000",
            "doc_count": 648
        },
        {
            "key": "Mozilla/5.0 (Linux; Android; SAMSUNG Build) AppleWebKit (KHTML, like Gecko) SamsungBrowser Chrome Mobile Safari",
            "doc_count": 667
        },
        {
            "key": "Mozilla/5.0 (Windows NT; Win64; x64; rv) Gecko Firefox",
            "doc_count": 1010
        },
        {
            "key": "Mozilla/5.0 (Windows NT; Win64; x64) AppleWebKit (KHTML, like Gecko) Chrome Safari",
            "doc_count": 1251
        },
        {
            "key": "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_4) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/74.0.3729.169 Safari/537.36",
            "doc_count": 1376
        },
        {
            "key": "Cred Trader UK",
            "doc_count": 1484
        },
        {
            "key": "Mozilla/5.0 (Windows NT 6.1; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/76.0.3809.132 Safari/537.36",
            "doc_count": 1563
        }
    ],
    "num_distinct_paths": 4,
    "num_distinct_ips": 50,
    "num_distinct_datacentres": 32,
    "num_distinct_countries": 2,
    "num_distinct_user_agents": 20,
    "time_first_recommendation": "2022-07-15T08:19:00.003Z",
    "time_first_mitigation": "2022-07-15T08:24:00.003Z",
    "type": "Other",
    "total_dc_recommendations": 0,
    "total_ip_recommendations": 0,
    "total_attack_requests": 170871
}
``` 

### Notes

---

## Actioned (Coming Soon)

This endpoint will return data for the following:

- Threat Visitor
- Threat IP Address
- Threat User Agent
- Threat Data Centre
- Trusted Visitor
- Trusted IP Address
- Trusted User Agent
- Trusted Data Centre

<!-- **URL** : `/domains/{domainID}/attacks`

**Method** : `GET`

**Auth required** : YES

**Permissions required** : Vendor

## Success Response

**Code** : `200 OK`

**Content example**

```json
[
    {
        "id": "cdd1f2f1-71ff-4a58-96bf-79e879ec6949",
        "start_time": "2022-07-18T02:10:00.005Z",
        "end_time": "2022-07-18T03:10:00.005Z",
        "total_requests_mitigated": 61301,
        "total_attack_requests": 65872,
        "type": "Credential Stuffing"
    },
]
```

### Notes -->

---

## Dashboards

Returns a array of QuickSight dashboards available for a given domain

**URL** : `/domains/{domainID}/dashboards`

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

**URL** : `/domains/{domainID}/dashboards/{dashboardID}`

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