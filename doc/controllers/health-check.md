# Health-Check

EndpointEndpoint to check API health.

```ts
const healthCheckController = new HealthCheckController(client);
```

## Class Name

`HealthCheckController`


# Health Check

Health Check

```ts
async healthCheck(
  requestOptions?: RequestOptions
): Promise<ApiResponse<unknown>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

`unknown`

## Example Usage

```ts
try {
  const { result, ...httpResponse } = await healthCheckController.healthCheck();
  // Get more response info...
  // const { statusCode, headers } = httpResponse;
} catch(error) {
  if (error instanceof ApiError) {
    const errors = error.result;
    // const { statusCode, headers } = error;
  }
}
```

## Example Response

```
{
  "api_rest": {
    "name": "customer-registration-api",
    "status": "UP",
    "message": "API is OK"
  },
  "database": {
    "name": "customers",
    "status": "UP",
    "message": "Database is OK"
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiError` |

