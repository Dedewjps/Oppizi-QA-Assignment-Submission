# Open Charge Map – Postman Tests

This Postman collection validates two endpoints:
- `GET /referencedata/`
- `GET /poi/`

Each request includes tests for:
- **Status code** = 200
- **Response time** < 1000 ms
- **Response schema** (partial JSON schema)
- **Business logic**
  - `/referencedata`: countries include **BR**, and connection types are non-empty
  - `/poi`: result length <= `maxresults`, ISO country `BR/BRA`, optional `Distance` within `distance + 0.5` km

## 1) Import into Postman
1. Download and import `OpenChargeMap.postman_collection.json`.
2. Download and import `OCM.postman_environment.json`.
3. Paste your API key into the `OCM_API_KEY` variable.
(You can find the key by inspecting the X-Api-Key header or ?key= query in network requests from https://map.openchargemap.io/#/search)

## 2) Run via Postman 
- Choose the collection, choose the desired request, and click **Run**.

## Notes
- Response time assertions (< 1000 ms) depend on your network. If they are flaky, consider loosening to 1500 ms for local runs.
- Schemas are **partial** to remain resilient to benign API changes while validating key fields.
- You can change the `latitude`, `longitude`, `distance`, and `maxresults` variables in the environment to test other areas.
