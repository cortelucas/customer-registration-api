# Clients

Endpoint for customer management.

```ts
const clientsController = new ClientsController(client);
```

## Class Name

`ClientsController`

## Methods

* [Insert Customer](../../doc/controllers/clients.md#insert-customer)
* [Query All Customers](../../doc/controllers/clients.md#query-all-customers)
* [Querry Customer by Id](../../doc/controllers/clients.md#querry-customer-by-id)


# Insert Customer

This Endpoint is used for Creating a new user.

```ts
async insertCustomer(
  body?: unknown,
  requestOptions?: RequestOptions
): Promise<ApiResponse<unknown>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | `unknown \| undefined` | Body, Optional | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

`unknown`

## Example Usage

```ts
const contentType = null;
try {
  const { result, ...httpResponse } = await clientsController.insertCustomer();
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
  "message": "Cliente criado com sucesso.",
  "id_usuario": "9aad1ad1-57d1-4fae-b01c-b959de731e5d"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiError` |


# Query All Customers

This Endpoint is used to search for all clients.

```ts
async queryAllCustomers(
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
  const { result, ...httpResponse } = await clientsController.queryAllCustomers();
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
[
  {
    "client_id": "c1a42cef-381c-489d-b692-535ef781d474",
    "name": "Jhon",
    "lastName": "Doe",
    "phones": [
      {
        "ddd": 11,
        "number": 999190000
      }
    ],
    "address": {
      "street": "Rua São Paulo",
      "number": 1221,
      "district": "Centro",
      "city": "Coast City",
      "state": "SP",
      "postalCode": "88765-000"
    }
  },
  {
    "client_id": "b04bf3b9-bf31-44de-bf16-8d2b6d40587e",
    "name": "Jhonny",
    "lastName": "Doe",
    "phones": [
      {
        "ddd": 11,
        "number": 999887654
      }
    ],
    "address": {
      "street": "Rua Aves Truz",
      "number": 3344,
      "district": "Centro",
      "city": "Coast City",
      "state": "SP",
      "postalCode": "88765-000"
    }
  },
  {
    "client_id": "d78f930f-e958-42ca-bdc8-42ff73e4304d",
    "name": "Davi",
    "lastName": "Moreira",
    "phones": [
      {
        "ddd": 89,
        "number": 26583584
      },
      {
        "ddd": 89,
        "number": 999209546
      }
    ],
    "address": {
      "street": "Avenida Professora Maria Lina de Araújo",
      "number": 46,
      "district": "Centro",
      "city": "Acauã",
      "state": "PI",
      "postalCode": "64748-970"
    }
  }
]
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiError` |
| 404 | Not Found | `ApiError` |


# Querry Customer by Id

This Endpoint is used to search for a client.

```ts
async querryCustomerById(
  clientId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<unknown>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `clientId` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

`unknown`

## Example Usage

```ts
const clientId = 'client_id8';
try {
  const { result, ...httpResponse } = await clientsController.querryCustomerById(clientId);
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
  "client_id": "9aad1ad1-57d1-4fae-b01c-b959de731e5d",
  "name": "Tereza",
  "lastName": "Simone",
  "phones": [
    {
      "ddd": 66,
      "number": 37274372
    },
    {
      "ddd": 66,
      "number": 999312293
    }
  ],
  "address": {
    "street": "Avenida Governador Dante Martins de Oliveira",
    "number": 115,
    "district": "Centro",
    "city": "Apiacás",
    "state": "MT",
    "postalCode": null
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiError` |
| 404 | Not Found | `ApiError` |

