# # Factory Metrics MS

## Endpoint

- `GET /api/projects/{projectId}/metrics?range=7d`

## Flux (Backstage -> Proxy -> Spring)

```mermaid
sequenceDiagram
  participant U as User (Browser)
  participant B as Backstage Backend
  participant S as Spring Boot MS

  U->>B: GET /api/proxy/factory/projects/12345/metrics?range=7d
  B->>S: GET /api/projects/12345/metrics?range=7d
  S-->>B: 200 JSON metrics
  B-->>U: 200 JSON metrics
```

## Exemple de réponse

```json
{"projectId":"12345","rows":[{"bucket_day":"2025-12-16","metric_key":"pipeline_duration_sec_p50","value":310.0,"unit":"s"}]}
```
ça me soule....
