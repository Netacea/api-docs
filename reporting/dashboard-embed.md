# Dashboard Embed

Returns a embed code for a QuickSight dashboard available for a given domain

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

## Notes

* An vanilla javascript example of embedding can be found [here](dashboard-embed.html)