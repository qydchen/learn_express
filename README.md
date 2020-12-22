# Going through API design course

https://domain/product/version/resource/{id}

`domain` ensure that domain is never www, `api` `app` `developer` are the commonly used ones; use dedicated Domain
`product` (aka pacakages) logical grouping of resources (optional)
`version` multiple versionals of the api; insulates API consumers from API changes (optional; version management via Headers & Query Parameters)
`resource` depends on business domain
`{id}` identity of a resource

Use NOUNS to identify the resources

Most APIs use Plural (suggested)

Define ACTION as part of resource hierarchy if it does not apply to CRUD

- `estimates/price`
- `friendships/lookup`
- `people/{id}/followers/{id}`

Avoid nesting beyond three levels

Think about the end consumer's experience

`PUT` - Update ALL of the attributes of the resource

`PATCH` - Update SOME of the attributes of the resources - sometimes more performant

Twitter just uses GET and POST

## Data formats:

Common formats: json, csv, xml

Ways to determine formats?

- Query Params
  - `/news?output=json`
  - `/news?output=csv`
- HTTP Headers
  - `Accept: application/json`
  - `Accept: application/csv`
- Resource format suffix
  - `forecast/daily/{days}day.json`

<br>

- `200 Success`
- `415 Unsupported type` - for unsupported format API returns HTTP 415
- `5xx Issue in processing`
- `Content-Type application/json`

Ensure documentation of supported formats
