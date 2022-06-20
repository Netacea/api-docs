# Netacea External API Documentation

![Netacea Header](https://assets.ntcacdn.net/header.jpg)

## Authentication

Closed endpoints require a valid api kay to be included in the header of the request.

### Vendor API Key

For Vendor access, a valid Vendor Api Key should be provided in the header of a request. CURL example:

```
X-Vendor-Api-Key
```

```
curl --header "X-Vendor-Api-Key: 9ca82657-e815-45df-b7eb-722b55267481" https://reporting.api.dev-red.netacea.cloud/domain/e96e6ef1-6763-4bc9-b2a1-0a038c54a235/dashboards
```

A valid API Key will be provided by netacea, please contact netacea for more information.

## Reporting API (Alpha)

**Please Note: the Reporting API is currently available as alpha a mock only, changes may still occur**

Alpha domain URL (Mock only):

```
https://reporting.api.dev-red.netacea.cloud
```

### Data Endpoints

Endpoints for accessing data:

**Please Note: To embed a dashboard the request domain must first be added to the list of approved domains. For more information [see here](reporting/approved-domains.md)**

* [Audit Trail](reporting/audit-trail.md) : `GET /domain/{domainID}/audit-trail`
* [Attacks](reporting/attacks.md) : `GET /domain/{domainID}/attacks`
* Attack: **Coming Soon**

### QuickSight Embed Endpoints

* [Dashboards](reporting/dashboards.md) : `GET /domain/{domainID}/dashboards`
* [Dashboard Embed](reporting/dashboard-embed.md) : `GET /domain/{domainID}/dashboards/{dashboardID}`