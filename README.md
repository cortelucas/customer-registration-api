<!-- Generator: Widdershins v4.0.1 -->

<h1 id="customers-registration-api">Customers Registration API v1.0.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

API for customer management. 

Base URLs:

* <a href="http://localhost:3030">http://localhost:3030</a>

<h1 id="customers-registration-api-clients">clients</h1>

Endpoint for customer management.

## insertCustomer

<a id="opIdinsertCustomer"></a>

> Code samples


```http
POST /api/clients HTTP/1.1
Host: localhost:3030
Content-Length: 417

{
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
    "postalCode": "78595-970"
  }
}

```



`POST /clients`

*Insert customer*

This Endpoint is used for Creating a new user.

> Body parameter

```json
{
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
    "postalCode": "78595-970"
  }
}
```

<h3 id="insertcustomer-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|none|

> Example responses

> 201 Response

```json
{
  "message": "Cliente criado com sucesso.",
  "id_usuario": "9aad1ad1-57d1-4fae-b01c-b959de731e5d"
}
```

> 400 Response

```json
{
  "message": "Não foi possível cadastrar o cliente.",
  "details": "O campo \"ddd\" não foi informado."
}
```

<h3 id="insertcustomer-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|Inline|

<h3 id="insertcustomer-responseschema">Response Schema</h3>

### Response Headers

|Status|Header|Type|Format|Description|
|---|---|---|---|---|
|201|Content-Type|string||none|
|400|Date|string||none|
|400|Content-Type|string||none|
|400|Transfer-Encoding|string||none|
|400|Connection|string||none|
|400|Server|string||none|
|400|x-srv-trace|string||none|
|400|x-srv-span|string||none|
|400|Access-Control-Allow-Origin|string||none|
|400|X-RateLimit-Limit|integer||none|
|400|X-RateLimit-Remaining|integer||none|
|400|X-RateLimit-Reset|integer||none|
|400|ETag|string||none|
|400|Vary|string||none|
|400|Content-Encoding|string||none|

<aside class="success">
This operation does not require authentication
</aside>

## queryAllCustomers

<a id="opIdqueryAllCustomers"></a>

> Code samples

```http
GET /api/clients HTTP/1.1
Host: localhost:3030

```


`GET /clients`

*Query Clients*

This Endpoint is used to search for all clients.

> Example responses

> 200 Response

```json
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

> 400 Response

```json
{
  "message": "Não foi possível buscar os clientes.",
  "details": "Falha na conexão com o banco de dados. Tente novamente em alguns minutos."
}
```

> 404 Response

```json
{
  "message": "Não foi possível buscar os clientes.",
  "details": "Usuários não encontrados."
}
```

<h3 id="queryallcustomers-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|Inline|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|

<h3 id="queryallcustomers-responseschema">Response Schema</h3>

### Response Headers

|Status|Header|Type|Format|Description|
|---|---|---|---|---|
|200|Content-Type|string||none|
|400|Content-Type|string||none|
|404|Content-Type|string||none|

<aside class="success">
This operation does not require authentication
</aside>

## querryCustomerById

<a id="opIdquerryCustomerById"></a>

> Code samples


```http
GET /api/clients/b04bf3b9-bf31-44de-bf16-8d2b6d40587e HTTP/1.1
Host: localhost:3030

```


`GET /clients/{client_id}`

*Query Customer by ID*

This Endpoint is used to search for a client.

<h3 id="querrycustomerbyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|client_id|path|string|true|none|

> Query Params = client_id

```json
"9aad1ad1-57d1-4fae-b01c-b959de731e5d"
```

> Example responses

> 200 Response

```json
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

> 400 Response

```json
{
  "message": "Não foi possível buscar o cliente.",
  "details": "Falha na conexão com o banco de dados. Tente novamente em alguns minutos."
}
```

> 404 Response

```json
{
  "message": "Não foi possível buscar o cliente.",
  "details": "Usuário de ID. 2 não encontrado."
}
```

<h3 id="querrycustomerbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|Inline|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|Inline|

<h3 id="querrycustomerbyid-responseschema">Response Schema</h3>

### Response Headers

|Status|Header|Type|Format|Description|
|---|---|---|---|---|
|200|Content-Type|string||none|
|400|Content-Type|string||none|
|404|Content-Type|string||none|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="customers-registration-api-health-check">health-check</h1>

EndpointEndpoint to check API health.

## get__health-check

> Code samples


```http
GET /api/health-check HTTP/1.1
Host: localhost:3030

```

`GET /health-check`

*Health Check*

> Example responses

> 200 Response

```json
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

> 400 Response

```json
{
  "api_rest": {
    "nome": "API Cadastro Clientes",
    "status": "OK",
    "message": ""
  },
  "banco_de_dados": {
    "nome": "Postgresql Heroku",
    "status": "NOK",
    "message": "Timeout"
  }
}
```

<h3 id="get__health-check-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|Inline|

<h3 id="get__health-check-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

