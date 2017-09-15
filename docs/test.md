# The Apex API

This API has the following attributes:

| Attribute | Value                 |
|-----------|-----------------------|
| namespace | com.yahoo.apex.parsec |
| version   | 1                     |


## Resources

### [ProjectResponse](#ProjectResponse)

#### POST /projects/

#### Request parameters:

| Name            | Type                              | Source                             | Options | Description |
|-----------------|-----------------------------------|------------------------------------|---------|-------------|
| creationRequest | [ProjectRequest](#projectrequest) | body                               |         |             |
| wssid           | String                            | header: X-YahooWSSID-Authorization |         |             |


#### Responses:

Expected:

| Code         | Type                                |
|--------------|-------------------------------------|
| 202 Accepted | [ProjectResponse](#projectresponse) |


Exception:

| Code                      | Type          | Comment |
|---------------------------|---------------|---------|
| 400 Bad Request           | ResourceError |         |
| 401 Unauthorized          | ResourceError |         |
| 403 Forbidden             | ResourceError |         |
| 409 Conflict              | ResourceError |         |
| 500 Internal Server Error | ResourceError |         |


#### PUT /projects/{id}

#### Request parameters:

| Name    | Type                              | Source                             | Options | Description |
|---------|-----------------------------------|------------------------------------|---------|-------------|
| id      | UUID                              | path                               |         |             |
| project | [ProjectRequest](#projectrequest) | body                               |         |             |
| wssid   | String                            | header: X-YahooWSSID-Authorization |         |             |


#### Responses:

Expected:

| Code   | Type            |
|--------|-----------------|
| 200 OK | ProjectResponse |


Exception:

| Code                      | Type          | Comment |
|---------------------------|---------------|---------|
| 400 Bad Request           | ResourceError |         |
| 401 Unauthorized          | ResourceError |         |
| 403 Forbidden             | ResourceError |         |
| 404 Not Found             | ResourceError |         |
| 409 Conflict              | ResourceError |         |
| 500 Internal Server Error | ResourceError |         |


#### GET /projects/{id}

#### Request parameters:

| Name | Type | Source | Options | Description |
|------|------|--------|---------|-------------|
| id   | UUID | path   |         |             |


#### Responses:

Expected:

| Code   | Type            |
|--------|-----------------|
| 200 OK | ProjectResponse |


Exception:

| Code                      | Type          | Comment |
|---------------------------|---------------|---------|
| 400 Bad Request           | ResourceError |         |
| 401 Unauthorized          | ResourceError |         |
| 404 Not Found             | ResourceError |         |
| 500 Internal Server Error | ResourceError |         |


### [NullResponse](#NullResponse)

#### POST /oAuthTokens

#### Request parameters:

| Name      | Type                    | Source                             | Options | Description |
|-----------|-------------------------|------------------------------------|---------|-------------|
| oAuthData | [OAuthData](#oauthdata) | body                               |         |             |
| wssid     | String                  | header: X-YahooWSSID-Authorization |         |             |


#### Responses:

Expected:

| Code           | Type |
|----------------|------|
| 204 No Content |      |


Exception:

| Code                      | Type          | Comment |
|---------------------------|---------------|---------|
| 400 Bad Request           | ResourceError |         |
| 401 Unauthorized          | ResourceError |         |
| 403 Forbidden             | ResourceError |         |
| 500 Internal Server Error | ResourceError |         |


## Types

### <a name="DateTime"></a> DateTime

e.g.2013-03-06T11:00:00Z

`DateTime` is an alias of type `String`

### <a name="ProjectRequest"></a> ProjectRequest
`ProjectRequest` is a `Struct` type with the following fields:

| Name        | Type   | Options | Description | Notes |
|-------------|--------|---------|-------------|-------|
| repoUrl     | String |         |             |       |
| custodian   | String |         |             |       |
| description | String |         |             |       |


### <a name="ProjectResponse"></a> ProjectResponse
`ProjectResponse` is a `Struct` type with the following fields:

| Name                 | Type                  | Options | Description | Notes |
|----------------------|-----------------------|---------|-------------|-------|
| id                   | UUID                  |         |             |       |
| name                 | String                |         |             |       |
| repoUrl              | String                |         |             |       |
| custodian            | String                |         |             |       |
| description          | String                |         |             |       |
| repo_update_time     | [DateTime](#datetime) |         |             |       |
| repo_head_sha        | String                |         |             |       |
| doc_generated_time   | [DateTime](#datetime) |         |             |       |
| doc_url              | String                |         |             |       |
| review_url           | String                |         |             |       |
| splunk_dashboard_url | String                |         |             |       |
| test_host_url        | String                |         |             |       |


### <a name="OAuthData"></a> OAuthData
`OAuthData` is a `Struct` type with the following fields:

| Name  | Type   | Options | Description | Notes |
|-------|--------|---------|-------------|-------|
| code  | String |         |             |       |
| state | String |         |             |       |


### <a name="NullResponse"></a> NullResponse
`NullResponse` is a `Struct` with no specified fields


[Swagger URL](https://git.corp.yahoo.com/pages/ApexTest/Swagger-UI/parsec/swagger-ui/?url=https://git.corp.yahoo.com/pages/ApexTest/project_1504853232033/swagger-json/test_swagger.json)
