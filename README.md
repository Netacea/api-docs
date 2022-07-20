# Netacea External API Documentation

![Netacea Header](https://assets.ntcacdn.net/header.jpg)

## Authentication

Closed endpoints require a valid api kay to be included in the header of the request.

### Vendor API Key

For Vendor access, a valid Vendor Api Key should be provided in the header of a request.

```
X-Vendor-Api-Key
```

**CURL example:**

```bash
curl --header "X-Vendor-Api-Key: 9ca82657-e815-45df-b7eb-722b55267481" https://reporting.api.uat.netacea.cloud/domain/e96e6ef1-6763-4bc9-b2a1-0a038c54a235/dashboards
```

A valid API Key will be provided by netacea, please contact netacea for more information.

API Keys can be used to access all netacea apis with permission based access

#### Reporting API

Returns reporting data/dashboards for domains

See documentation [here](reporting/reporting-api.md)

#### Domain API

Allows for Vendor integration with accounts and domains

**Coming Soon**