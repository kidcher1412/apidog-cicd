---
title: Mock_API_Practice
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - ruby: Ruby
  - python: Python
  - php: PHP
  - java: Java
  - go: Go
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: "@tarslib/widdershins v4.0.30"

---

# Mock_API_Practice

Base URLs:

* <a href="http://127.0.0.1:5201">Develop Env: http://127.0.0.1:5201</a>

# Authentication

- HTTP Authentication, scheme: bearer

# Auth

<a id="opIdAuthController_login"></a>

## POST AuthController_login

POST /auth/login

> Body Parameters

```json
{
  "username": "string",
  "password": "string",
  "ip": "string"
}
```

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Authorization|header|string| no |none|
|body|body|[userAccountDto](#schemauseraccountdto)| no |none|

> Response Examples

> 201 Response

```json
{
  "statusCode": 200,
  "isSuccess": true,
  "message": "Thành công",
  "messageErrors": [],
  "payload": {
    "username": "Thong_TLR",
    "accessToken": "eyJhbGciOiJIUzI1NiIsInR...",
    "refreshToken": "eyJhbGciOiJIUzI1NiIsInR...",
    "role": "admin",
    "expired": "17061046756"
  }
}
```

> 400 Response

```json
{
  "statusCode": 400,
  "isSuccess": false,
  "message": "Thất bại",
  "messageErrors": [
    "fail to processing program",
    "check log file"
  ],
  "payload": null
}
```

> 401 Response

```json
{
  "statusCode": 401,
  "isSuccess": false,
  "message": "Thất bại",
  "messageErrors": [
    "Tài khoản hoặc mật khẩu không chính xác"
  ],
  "payload": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|API response|[ApiResponseBad](#schemaapiresponsebad)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **201**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|[AuthPayloadDto](#schemaauthpayloaddto)|true|none||Dữ liệu trả về|
|»» username|string|true|none||Tên đăng nhập của người dùng|
|»» accessToken|string|true|none||Access Token để xác thực|
|»» refreshToken|string|true|none||Refresh Token để làm mới Access Token|
|»» role|string|true|none||Vai trò của người dùng|
|»» expired|string|true|none||Thông tin về thời gian hết hạn|

HTTP Status Code **400**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|object|true|none||dữ  liệu trả về từ lệnh (có thể null khi lỗi)|

HTTP Status Code **401**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|null|true|none||Dữ liệu trả về|

<a id="opIdAuthController_refreshToken"></a>

## POST AuthController_refreshToken

POST /auth/refresh

> Body Parameters

```json
{
  "refreshToken": "string"
}
```

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Authorization|header|string| no |none|
|body|body|object| no |none|
|» refreshToken|body|string| no |none|

> Response Examples

> 201 Response

```json
{
  "statusCode": 200,
  "isSuccess": true,
  "message": "Thành công",
  "messageErrors": [],
  "payload": {
    "username": "john_doe",
    "accessToken": "eyJhbGciOiJIUzI1NiIsInR...",
    "refreshToken": "eyJhbGciOiJIUzI1NiIsInR...",
    "role": "admin",
    "expired": "17061046756"
  }
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|API response|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|API response|[ApiResponseBad](#schemaapiresponsebad)|

### Responses Data Schema

HTTP Status Code **201**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|object|true|none||Dữ liệu trả về|
|»» username|string|true|none||Tên đăng nhập của người dùng|
|»» accessToken|string|true|none||Access Token để xác thực|
|»» refreshToken|string|true|none||Refresh Token để làm mới Access Token|
|»» role|string|true|none||Vai trò của người dùng|
|»» expired|string|true|none||Thông tin về thời gian hết hạn|

HTTP Status Code **400**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|object|true|none||dữ  liệu trả về từ lệnh (có thể null khi lỗi)|

# Home

<a id="opIdHomeController_getClientIp"></a>

## GET HomeController_getClientIp

GET /home

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Authorization|header|string| no |none|

> Response Examples

> 200 Response

```json
{
  "statusCode": 200,
  "isSuccess": true,
  "message": "Thành công",
  "messageErrors": [],
  "payload": "consectetur labore non do aliqua"
}
```

> 400 Response

```json
{
  "statusCode": 400,
  "isSuccess": false,
  "message": "Thất bại",
  "messageErrors": [
    "fail to processing program",
    "check log file"
  ],
  "payload": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|API response|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|API response|[ApiResponseBad](#schemaapiresponsebad)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|string|true|none||Dữ liệu trả về|

HTTP Status Code **400**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|object|true|none||dữ  liệu trả về từ lệnh (có thể null khi lỗi)|

HTTP Status Code **401**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|null|true|none||Dữ liệu trả về|

# ExchangeInvoice

<a id="opIdExchangeInvoiceController_Auto_Cancel_New"></a>

## GET Auto Cancel

GET /exchange-invoice/auto-cancel

API để thực hiện cancel hàng loạt hóa đơn ở trạng thái new trong ngày

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Authorization|header|string| no |none|

> Response Examples

> 200 Response

```json
{
  "statusCode": 200,
  "isSuccess": true,
  "message": "Thành công",
  "messageErrors": [],
  "payload": {}
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]¦null|false|none||Danh sách lỗi nếu có|
|» payload|object¦null|false|none||Dữ liệu trả về|

HTTP Status Code **400**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|null|false|none||Dữ liệu trả về|

HTTP Status Code **401**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|null|true|none||Dữ liệu trả về|

<a id="opIdExchangeInvoiceController_Get_FXT_Receipt"></a>

## GET Query Receipt

GET /exchange-invoice/exchange-receipt

API để lấy dữ liệu danh sách thông tin chung của hóa đơn

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|receiptId|query|string| no |none|
|currencyCode|query|string| no |none|
|fromDate|query|string| no |none|
|toDate|query|string| no |none|
|minAmount|query|number| no |none|
|maxAmount|query|number| no |none|
|fromId|query|number| no |none|
|toId|query|number| no |none|
|customerName|query|string| no |none|
|status|query|string| no |none|
|Authorization|header|string| no |none|

#### Enum

|Name|Value|
|---|---|
|status|NEW|
|status|PUBLICED|
|status|CANCELED|
|status|COMPLETED|

> Response Examples

> 200 Response

```json
{
  "statusCode": 200,
  "isSuccess": true,
  "message": "Thành công",
  "messageErrors": [],
  "payload": [
    {
      "id": "101",
      "createdDate": "2025-03-24T12:00:00Z",
      "createdBy": "Username 1",
      "updatedDate": "string",
      "updatedBy": "string",
      "customerName": "Khách Hàng A",
      "passport": "015884785",
      "address": "Địa chỉ A",
      "status": "NEW",
      "totalExchange": "NEW"
    }
  ]
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|false|none||Danh sách lỗi nếu có|
|» payload|[[ReceiptItemReturnDto](#schemareceiptitemreturndto)]¦null|true|none||Dữ liệu trả về|
|»» id|number|true|none||Số hóa đơn|
|»» createdDate|string|true|none||Ngày tạo hóa đơn|
|»» createdBy|string|true|none||Tên tài khoản đã tạo hóa đơn|
|»» updatedDate|string¦null|false|none||Ngày cập nhật hóa đơn|
|»» updatedBy|string¦null|false|none||Tên tài khoản đã cập nhật hóa đơn|
|»» customerName|string|true|none||Tên người nộp tiền của hóa đơn|
|»» passport|string|true|none||Số passport của người nộp tiền của hóa đơn|
|»» address|string|true|none||Địa chỉ của người nộp tiền của hóa đơn|
|»» status|string|true|none||Trạng thái hóa đơn|
|»» totalExchange|number|true|none||Tổng tiền VND đã trao đổi trong hóa đơn|

HTTP Status Code **400**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|null|false|none||Dữ liệu trả về|

HTTP Status Code **401**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|null|true|none||Dữ liệu trả về|

<a id="opIdExchangeInvoiceController_Create_FXT_Invoice"></a>

## POST Create Receipt

POST /exchange-invoice/exchange-receipt

API để thêm dữ liệu invoice

> Body Parameters

```json
{
  "customerName": "string",
  "passport": "string",
  "address": "string",
  "username": "string",
  "itemsDetail": [
    {
      "fromCurrencyId": 0,
      "toCurrencyId": 0,
      "unitValue": 0,
      "exchangeRate": 0,
      "quality": 0
    }
  ]
}
```

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Authorization|header|string| no |none|
|body|body|[ExchangeInvoiceCreateDto](#schemaexchangeinvoicecreatedto)| no |none|

> Response Examples

> 201 Response

```json
{
  "statusCode": 200,
  "isSuccess": true,
  "message": "Thành công",
  "messageErrors": [],
  "payload": 0
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|Inline|
|502|[Bad Gateway](https://tools.ietf.org/html/rfc7231#section-6.6.3)|API response|[ApiResponseBad](#schemaapiresponsebad)|

### Responses Data Schema

HTTP Status Code **201**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]¦null|true|none||Danh sách lỗi nếu có|
|» payload|number|true|none||Dữ liệu trả về|

HTTP Status Code **400**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|null|false|none||Dữ liệu trả về|

HTTP Status Code **401**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|null|true|none||Dữ liệu trả về|

HTTP Status Code **502**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|object|true|none||dữ  liệu trả về từ lệnh (có thể null khi lỗi)|

<a id="opIdExchangeInvoiceController_Delete_FXT_Exchange_Rate"></a>

## DELETE Cancel Invoice

DELETE /exchange-invoice/exchange-receipt

API để thêm hủy hóa đơn đã tạo

> Body Parameters

```json
{
  "receiptId": "string"
}
```

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Authorization|header|string| no |none|
|body|body|[ReceiptDetailQueryDto](#schemareceiptdetailquerydto)| no |none|

> Response Examples

> 200 Response

```json
{
  "statusCode": 200,
  "isSuccess": true,
  "message": "Thành công",
  "messageErrors": [],
  "payload": 5
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|API response|[ApiResponseNumber](#schemaapiresponsenumber)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|Inline|
|502|[Bad Gateway](https://tools.ietf.org/html/rfc7231#section-6.6.3)|API response|[ApiResponseBad](#schemaapiresponsebad)|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|number|true|none||dữ  liệu trả về từ lệnh (có thể null khi lỗi)|

HTTP Status Code **400**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|null|false|none||Dữ liệu trả về|

HTTP Status Code **401**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|null|true|none||Dữ liệu trả về|

HTTP Status Code **502**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|object|true|none||dữ  liệu trả về từ lệnh (có thể null khi lỗi)|

<a id="opIdExchangeInvoiceController_Get_FXT_Detail_Receipt"></a>

## GET Query Detail Receipt

GET /exchange-invoice/exchange-detail-invoice

API để lấy dữ liệu chi tiết receipt exchange

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|receiptId|query|string| no |none|
|Authorization|header|string| no |none|

> Response Examples

> 200 Response

```json
{
  "statusCode": 200,
  "isSuccess": true,
  "message": "Thành công",
  "messageErrors": [],
  "payload": {
    "id": "23",
    "createdDate": "2025-03-24 12:00:00",
    "createdBy": "Username",
    "updatedDate": "string",
    "updatedBy": "string",
    "customerName": "Khách Hàng A",
    "passport": "015884785",
    "address": "Địa chỉ A",
    "status": "NEW",
    "detail": [
      {
        "currencyCode": "USD",
        "items": [
          {
            "fromCurrency": null,
            "toCurrency": null,
            "valueUnit": null,
            "quality": null,
            "total": null,
            "exchangeRate": null,
            "createBy": null
          }
        ],
        "total": 0,
        "totalExchange": 0
      }
    ],
    "totalExchange": 112000
  }
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|API response|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|API response|[ApiResponseBad](#schemaapiresponsebad)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|[ReceiptDetailReturnDbDto](#schemareceiptdetailreturndbdto)|true|none||Dữ liệu trả về|
|»» id|number|true|none||Số hóa đơn|
|»» createdDate|string|true|none||Ngày tạo hóa đơn|
|»» createdBy|string|true|none||Tài khoản tạo hóa đơn|
|»» updatedDate|string¦null|false|none||Ngày chỉnh sửa hóa đơn|
|»» updatedBy|string¦null|false|none||Tài khoản cập nhật hóa đơn|
|»» customerName|string|true|none||Tên người nộp tiền của hóa đơn|
|»» passport|string|true|none||Số passport của người nộp tiền của hóa đơn|
|»» address|string|true|none||Địa chỉ của người nộp tiền của hóa đơn|
|»» status|string|true|none||Trạng thái hóa đơn|
|»» detail|[[TypeOfCurrencyCodeDto](#schematypeofcurrencycodedto)]|true|none||Danh sách chi tiết loại tiền tệ|
|»»» currencyCode|string|true|none||Mã ngoại tệ trao đổi|
|»»» items|[[DetailReceiptReturnDbDto](#schemadetailreceiptreturndbdto)]|true|none||Danh sách chi tiết mệnh giá món trao đổi ngoại tệ|
|»»»» fromCurrency|string|true|none||Mã ngoại tệ khách mang tới trao đổi|
|»»»» toCurrency|string|true|none||Mã ngoại tệ khách muốn trao đổi|
|»»»» valueUnit|number|true|none||mệnh giá tiền|
|»»»» quality|number|true|none||Số lượng tờ mệnh giá|
|»»»» total|number|true|none||Tổng tiền thu được sau khi tính|
|»»»» exchangeRate|number|true|none||Tỉ giá nhận được khi trao đổi ngoại tệ|
|»»»» createBy|string|true|none||Tên tài khoản đã tạo|
|»»» total|number|true|none||số tiền ngoại tệ thu vào của món ngoại tệ sau khi tính|
|»»» totalExchange|number|true|none||tổng số tiền VND đổi được tại món ngoại tệ thu vào|
|»» totalExchange|number|true|none||Tổng tiền VND sau khi tính toán tất cả chi tiết trong hóa đơn|

HTTP Status Code **400**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|object|true|none||dữ  liệu trả về từ lệnh (có thể null khi lỗi)|

HTTP Status Code **401**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|null|true|none||Dữ liệu trả về|

<a id="opIdExchangeInvoiceController_Get_FXT_Exchange_Rate_Current"></a>

## GET Get Exchange Rate

GET /exchange-invoice/exchange-rate-current

API để thêm dữ liệu invoice

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|dateQuery|query|string| no |none|
|Authorization|header|string| no |none|

> Response Examples

> 200 Response

```json
{
  "statusCode": 200,
  "isSuccess": true,
  "message": "Thành công",
  "messageErrors": [],
  "payload": [
    {
      "timeUpdate": "2024-12-02",
      "items": [
        {
          "id": 45417469.24802777,
          "currencyCode": "TOP",
          "currencyName": "Quetzal",
          "currencyUnit": "Ut Excepteur deserunt ad reprehenderit",
          "dateCreated": "2026-03-14",
          "ca1": 10499191.573762268,
          "ca2": 55816105.50797799,
          "ca3": null,
          "trs": 21795012.643270925
        },
        {
          "id": 13042222.868257493,
          "currencyCode": "MGA",
          "currencyName": "Cuban Peso",
          "currencyUnit": "exercitation do",
          "dateCreated": "2024-10-25",
          "ca1": -28942790.38528192,
          "ca2": null,
          "ca3": null,
          "trs": null
        },
        {
          "id": 16993489.747570172,
          "currencyCode": "SZL",
          "currencyName": "Iceland Krona",
          "currencyUnit": "elit anim veniam commodo",
          "dateCreated": "2024-06-05",
          "ca1": null,
          "ca2": -12062859.663111508,
          "ca3": null,
          "trs": 84077630.73661748
        }
      ]
    },
    {
      "timeUpdate": "2025-07-03",
      "items": [
        {
          "id": -35889230.5943856,
          "currencyCode": "IDR",
          "currencyName": "New Zealand Dollar",
          "currencyUnit": "labore in voluptate nisi",
          "dateCreated": "2025-06-17",
          "ca1": -84827419.45055449,
          "ca2": -90865486.52383897,
          "ca3": 12909093.104645833,
          "trs": null
        }
      ]
    },
    {
      "timeUpdate": "2024-09-02",
      "items": [
        {
          "id": -70312596.801883,
          "currencyCode": "MRU",
          "currencyName": "Saudi Riyal",
          "currencyUnit": "Excepteur",
          "dateCreated": "2024-10-16",
          "ca1": 91272641.11529246,
          "ca2": null,
          "ca3": null,
          "trs": -44972978.87869056
        },
        {
          "id": 3383077.1730178,
          "currencyCode": "PGK",
          "currencyName": "Seychelles Rupee",
          "currencyUnit": "dolor irure",
          "dateCreated": "2025-01-06",
          "ca1": -50963641.64323064,
          "ca2": -60507837.641701646,
          "ca3": null,
          "trs": null
        }
      ]
    }
  ]
}
```

> 400 Response

```json
{
  "statusCode": 400,
  "isSuccess": false,
  "message": "Thất bại",
  "messageErrors": [
    "fail to processing program",
    "check log file"
  ],
  "payload": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|API response|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|API response|[ApiResponseBad](#schemaapiresponsebad)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|[[CurrencyRateListGroupTimeDto](#schemacurrencyratelistgrouptimedto)]|true|none||Dữ liệu trả về|
|»» timeUpdate|string|true|none||Thời gian thực hiện cập nhật tỷ giá|
|»» items|[[CurrencyRateListReturnDbDto](#schemacurrencyratelistreturndbdto)]|true|none||Danh sách các ngoại tệ kèm tỷ giá|
|»»» id|number|true|none||Mã id ngoại tệ|
|»»» currencyCode|string|true|none||Mã ngoại tệ|
|»»» currencyName|string|true|none||Tên ngoại tệ|
|»»» currencyUnit|string|true|none||Đơn vị tính ngoại tệ|
|»»» dateCreated|string|true|none||Ngày tỷ giá ngoại tệ được tạo|
|»»» ca1|number¦null|true|none||Tỷ giá CA1 của ngoại tệ (USD)|
|»»» ca2|number¦null|true|none||Tỷ giá CA2 của ngoại tệ (USD)|
|»»» ca3|number¦null|true|none||Tỷ giá CA3 của ngoại tệ (USD)|
|»»» trs|number¦null|true|none||Tỷ giá TRS của ngoại tệ (USD)|

HTTP Status Code **400**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|object|true|none||dữ  liệu trả về từ lệnh (có thể null khi lỗi)|

HTTP Status Code **401**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|null|true|none||Dữ liệu trả về|

<a id="opIdExchangeInvoiceController_Get_List_Currency"></a>

## GET Get List Currency

GET /exchange-invoice/list-currency

API để thêm dữ liệu invoice

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Authorization|header|string| no |none|

> Response Examples

> 200 Response

```json
{
  "statusCode": 200,
  "isSuccess": true,
  "message": "Thành công",
  "messageErrors": [],
  "payload": [
    {
      "id": 0,
      "currencyCode": "string",
      "currencyName": "string",
      "currencyUnit": "string",
      "currencyLocation": "string",
      "status": "string"
    }
  ]
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|API response|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|API response|[ApiResponseBad](#schemaapiresponsebad)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|[[CurrencyEntity](#schemacurrencyentity)]|true|none||Dữ liệu trả về|
|»» id|number|true|none||Mã id ngoại tệ|
|»» currencyCode|string|true|none||Mã ngoại tệ|
|»» currencyName|string|true|none||Tên ngoại tệ|
|»» currencyUnit|string|true|none||Đơn vị tính ngoại tệ|
|»» currencyLocation|string¦null|true|none||khu vực ngoại tệ đặt|
|»» status|string|true|none||Trạng thái ngoại tệ|

HTTP Status Code **400**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|object|true|none||dữ  liệu trả về từ lệnh (có thể null khi lỗi)|

HTTP Status Code **401**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|null|true|none||Dữ liệu trả về|

<a id="opIdExchangeInvoiceController_Set_FXT_Exchange_Rate_Test"></a>

## POST Set Exchange Rate

POST /exchange-invoice/insert-exchange-rate-test

API để thêm dữ liệu Rate cho đồng tiền trong ngày

> Body Parameters

```json
[
  "string"
]
```

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Authorization|header|string| no |none|
|body|body|array[string]| no |none|

> Response Examples

> 201 Response

```json
{
  "statusCode": 200,
  "isSuccess": true,
  "message": "Thành công",
  "messageErrors": [],
  "payload": 5
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|API response|[ApiResponseNumber](#schemaapiresponsenumber)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|Inline|
|502|[Bad Gateway](https://tools.ietf.org/html/rfc7231#section-6.6.3)|API response|[ApiResponseBad](#schemaapiresponsebad)|

### Responses Data Schema

HTTP Status Code **201**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|number|true|none||dữ  liệu trả về từ lệnh (có thể null khi lỗi)|

HTTP Status Code **400**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|null|false|none||Dữ liệu trả về|

HTTP Status Code **401**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|null|true|none||Dữ liệu trả về|

HTTP Status Code **502**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|object|true|none||dữ  liệu trả về từ lệnh (có thể null khi lỗi)|

<a id="opIdExchangeInvoiceController_Get_FXT_Last_Day_Change_Currency"></a>

## GET Get the last date currency has change

GET /exchange-invoice/last-change-currency

API để tìm kiếm dữ liệu ngày cuối cùng cập nhật ngoại tệ

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|currencyCode|query|string| no |none|
|Authorization|header|string| no |none|

> Response Examples

> 200 Response

```json
{
  "statusCode": 200,
  "isSuccess": true,
  "message": "Thành công",
  "messageErrors": [],
  "payload": "string"
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|API response|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|API response|[ApiResponseBad](#schemaapiresponsebad)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|string|true|none||Dữ liệu trả về|

HTTP Status Code **400**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|object|true|none||dữ  liệu trả về từ lệnh (có thể null khi lỗi)|

HTTP Status Code **401**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|null|true|none||Dữ liệu trả về|

<a id="opIdExchangeInvoiceController_Public_FXT_Exchange_Receipt"></a>

## POST Public exchange

POST /exchange-invoice/public-exchange

API để phát hành hóa đơn thu

> Body Parameters

```json
{
  "receiptId": "string"
}
```

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Authorization|header|string| no |none|
|body|body|[ReceiptDetailQueryDto](#schemareceiptdetailquerydto)| no |none|

> Response Examples

> 201 Response

```json
{
  "statusCode": 200,
  "isSuccess": true,
  "message": "Thành công",
  "messageErrors": [],
  "payload": 5
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|API response|[ApiResponseNumber](#schemaapiresponsenumber)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|Inline|
|502|[Bad Gateway](https://tools.ietf.org/html/rfc7231#section-6.6.3)|API response|[ApiResponseBad](#schemaapiresponsebad)|

### Responses Data Schema

HTTP Status Code **201**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|number|true|none||dữ  liệu trả về từ lệnh (có thể null khi lỗi)|

HTTP Status Code **400**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|null|false|none||Dữ liệu trả về|

HTTP Status Code **401**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|null|true|none||Dữ liệu trả về|

HTTP Status Code **502**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|object|true|none||dữ  liệu trả về từ lệnh (có thể null khi lỗi)|

<a id="opIdExchangeInvoiceController_Get_Exchange_Bill_Rate"></a>

## GET Get Bill Invoice

GET /exchange-invoice/exchange-receipt-bill

API để thêm dữ liệu invoice

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|receiptId|query|string| no |none|
|Authorization|header|string| no |none|

> Response Examples

> 200 Response

> 400 Response

```json
{
  "statusCode": 400,
  "isSuccess": false,
  "message": "Thất bại",
  "messageErrors": [
    "fail to processing program",
    "check log file"
  ],
  "payload": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Trả về file PDF biên nhận|string|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|API response|[ApiResponseBad](#schemaapiresponsebad)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **400**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|object|true|none||dữ  liệu trả về từ lệnh (có thể null khi lỗi)|

HTTP Status Code **401**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|null|true|none||Dữ liệu trả về|

<a id="opIdExchangeInvoiceController_Get_Reprot_Cash_Book_PDF"></a>

## GET Get PDF cash book by Day

GET /exchange-invoice/cash-book-pdf-month

API để lấy pdf report day

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|month|query|number| no |none|
|year|query|number| no |none|
|fromId|query|number| no |none|
|toId|query|number| no |none|
|currencyCode|query|string| no |none|
|fromDate|query|string| no |none|
|toDate|query|string| no |none|
|Authorization|header|string| no |none|

> Response Examples

> 200 Response

> 400 Response

```json
{
  "statusCode": 400,
  "isSuccess": false,
  "message": "Thất bại",
  "messageErrors": [
    "fail to processing program",
    "check log file"
  ],
  "payload": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Trả về file PDF biên nhận|string|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|API response|[ApiResponseBad](#schemaapiresponsebad)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **400**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|object|true|none||dữ  liệu trả về từ lệnh (có thể null khi lỗi)|

HTTP Status Code **401**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|null|true|none||Dữ liệu trả về|

<a id="opIdExchangeInvoiceController_Get_Reprot_Report_PDF"></a>

## GET Get PDF report by Day

GET /exchange-invoice/report-pdf-month

API để lấy pdf report month

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|month|query|number| no |none|
|year|query|number| no |none|
|fromId|query|number| no |none|
|toId|query|number| no |none|
|currencyCode|query|string| no |none|
|fromDate|query|string| no |none|
|toDate|query|string| no |none|
|Authorization|header|string| no |none|

> Response Examples

> 200 Response

> 400 Response

```json
{
  "statusCode": 400,
  "isSuccess": false,
  "message": "Thất bại",
  "messageErrors": [
    "fail to processing program",
    "check log file"
  ],
  "payload": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Trả về file PDF biên nhận|string|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|API response|[ApiResponseBad](#schemaapiresponsebad)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **400**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|object|true|none||dữ  liệu trả về từ lệnh (có thể null khi lỗi)|

HTTP Status Code **401**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|null|true|none||Dữ liệu trả về|

<a id="opIdExchangeInvoiceController_Get_Reprot_Cash_Book_Id_PDF"></a>

## GET Get PDF Cash Book by Id

GET /exchange-invoice/cash-book-pdf-id

API để lấy pdf Cash Book Id

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|month|query|number| no |none|
|year|query|number| no |none|
|fromId|query|number| no |none|
|toId|query|number| no |none|
|currencyCode|query|string| no |none|
|fromDate|query|string| no |none|
|toDate|query|string| no |none|
|Authorization|header|string| no |none|

> Response Examples

> 200 Response

> 400 Response

```json
{
  "statusCode": 400,
  "isSuccess": false,
  "message": "Thất bại",
  "messageErrors": [
    "fail to processing program",
    "check log file"
  ],
  "payload": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Trả về file PDF biên nhận|string|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|API response|[ApiResponseBad](#schemaapiresponsebad)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **400**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|object|true|none||dữ  liệu trả về từ lệnh (có thể null khi lỗi)|

HTTP Status Code **401**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|null|true|none||Dữ liệu trả về|

<a id="opIdExchangeInvoiceController_Get_Reprot_Report_id_PDF"></a>

## GET Get PDF report by Id

GET /exchange-invoice/report-pdf-id

API để lấy pdf report Id

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|month|query|number| no |none|
|year|query|number| no |none|
|fromId|query|number| no |none|
|toId|query|number| no |none|
|currencyCode|query|string| no |none|
|fromDate|query|string| no |none|
|toDate|query|string| no |none|
|Authorization|header|string| no |none|

> Response Examples

> 200 Response

> 400 Response

```json
{
  "statusCode": 400,
  "isSuccess": false,
  "message": "Thất bại",
  "messageErrors": [
    "fail to processing program",
    "check log file"
  ],
  "payload": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Trả về file PDF biên nhận|string|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|API response|[ApiResponseBad](#schemaapiresponsebad)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **400**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|object|true|none||dữ  liệu trả về từ lệnh (có thể null khi lỗi)|

HTTP Status Code **401**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|null|true|none||Dữ liệu trả về|

<a id="opIdExchangeInvoiceController_Get_Reprot_Cash_Book_Slask_Id_PDF"></a>

## GET Get cash book at slack inventory

GET /exchange-invoice/cash-book-slack-pdf-id

API để lấy pdf report day

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|month|query|number| no |none|
|year|query|number| no |none|
|fromId|query|number| no |none|
|toId|query|number| no |none|
|currencyCode|query|string| no |none|
|fromDate|query|string| no |none|
|toDate|query|string| no |none|
|Authorization|header|string| no |none|

> Response Examples

> 200 Response

> 400 Response

```json
{
  "statusCode": 400,
  "isSuccess": false,
  "message": "Thất bại",
  "messageErrors": [
    "fail to processing program",
    "check log file"
  ],
  "payload": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Trả về file PDF biên nhận|string|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|API response|[ApiResponseBad](#schemaapiresponsebad)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **400**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|object|true|none||dữ  liệu trả về từ lệnh (có thể null khi lỗi)|

HTTP Status Code **401**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|null|true|none||Dữ liệu trả về|

<a id="opIdExchangeInvoiceController_Get_Reprot_End_Book_Month_PDF"></a>

## GET Get PDF end book month

GET /exchange-invoice/end-book-month-pdf

API để lấy pdf end book month

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|month|query|number| no |none|
|year|query|number| no |none|
|fromId|query|number| no |none|
|toId|query|number| no |none|
|currencyCode|query|string| no |none|
|fromDate|query|string| no |none|
|toDate|query|string| no |none|
|Authorization|header|string| no |none|

> Response Examples

> 200 Response

> 400 Response

```json
{
  "statusCode": 400,
  "isSuccess": false,
  "message": "Thất bại",
  "messageErrors": [
    "fail to processing program",
    "check log file"
  ],
  "payload": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Trả về file PDF biên nhận|string|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|API response|[ApiResponseBad](#schemaapiresponsebad)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **400**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|object|true|none||dữ  liệu trả về từ lệnh (có thể null khi lỗi)|

HTTP Status Code **401**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|null|true|none||Dữ liệu trả về|

# ReportExchange

<a id="opIdReportExchangeController_getOpeningBalance"></a>

## GET Query Open Balance

GET /report-exchange/open-balance

API để lấy dữ liệu tồn kho của tiền tệ tại thời điểm cụ thể

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|currencyCode|query|string| no |none|
|date|query|string| no |none|
|Authorization|header|string| no |none|

> Response Examples

> 200 Response

```json
{
  "statusCode": 200,
  "isSuccess": true,
  "message": "Thành công",
  "messageErrors": [],
  "payload": 5
}
```

> 400 Response

```json
{
  "statusCode": 200,
  "isSuccess": true,
  "message": "Thành công",
  "messageErrors": [],
  "payload": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|API response|[ApiResponseNumber](#schemaapiresponsenumber)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|Inline|
|502|[Bad Gateway](https://tools.ietf.org/html/rfc7231#section-6.6.3)|API response|[ApiResponseBad](#schemaapiresponsebad)|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|number|true|none||dữ  liệu trả về từ lệnh (có thể null khi lỗi)|

HTTP Status Code **400**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|null|false|none||Dữ liệu trả về|

HTTP Status Code **401**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|null|true|none||Dữ liệu trả về|

HTTP Status Code **502**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|object|true|none||dữ  liệu trả về từ lệnh (có thể null khi lỗi)|

<a id="opIdReportExchangeController_GetReportByDay"></a>

## GET Query make data receipts to cash book,report 

GET /report-exchange/reprot-by-day

API để lấy dữ liệu hóa đơn để tổng hợp và cung cấp dưới dạng xử lý sổ quỹ và báo cáo

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|fromDate|query|string| no |none|
|toDate|query|string| no |none|
|currencyCode|query|string| no |none|
|fromId|query|number| no |none|
|toId|query|number| no |none|
|Authorization|header|string| no |none|

> Response Examples

> 200 Response

```json
{
  "statusCode": 200,
  "isSuccess": true,
  "message": "Thành công",
  "messageErrors": [],
  "payload": {
    "uniqueCurrencies": [
      "USD"
    ],
    "rowsExpense": [
      {
        "currencyCode": "USD",
        "closingBalance": "1250",
        "tranxDate": "2025-03-24 12:00:00",
        "openingBalance": "15400"
      },
      {
        "currencyCode": "USD",
        "closingBalance": "1250",
        "tranxDate": "2025-03-24 12:00:00",
        "openingBalance": "15400"
      }
    ],
    "rowsCurrencyExchange": [
      {
        "date": "2025-03-27",
        "fromCurrency": "USD",
        "exchangeReceiptId": "EXR-20250327-001",
        "total": "1000",
        "totalExchange": 950,
        "openingBalance": 500,
        "closingBalance": 0,
        "createBy": "admin",
        "custommer": "Nguyễn Văn A"
      }
    ],
    "rowsCurrencyReport": [
      {
        "currencyCode": "USD",
        "items": [
          {
            "fromCurrency": "1",
            "toCurrency": "1",
            "valueUnit": -52377491.44444166,
            "quality": 5,
            "total": 16588316.423826918,
            "exchangeRate": 98222581.49293658,
            "createBy": "Username"
          }
        ],
        "total": 13033062.593468964,
        "totalExchange": -7547859.854566634
      }
    ]
  }
}
```

> 400 Response

```json
{
  "statusCode": 400,
  "isSuccess": false,
  "message": "Thất bại",
  "messageErrors": [
    "fail to processing program",
    "check log file"
  ],
  "payload": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|API response|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|API response|[ApiResponseBad](#schemaapiresponsebad)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|[ReportByDayRes](#schemareportbydayres)|true|none||Dữ liệu trả về|
|»» uniqueCurrencies|[string]|true|none||Danh sách mã ngoại tệ trao đổi|
|»» rowsExpense|[[ReportExpenseReturnDbDto](#schemareportexpensereturndbdto)]|true|none||Danh sách chi phí theo ngày|
|»»» currencyCode|string|true|none||Mã ngoại tệ thực hiện nhiệm chi|
|»»» closingBalance|number|true|none||Số tiền đã thực hiện chi|
|»»» tranxDate|string|true|none||ngày thực hiện nhiệm chi|
|»»» openingBalance|number|true|none||số dư tồn kho sau khi nhiệm chi|
|»» rowsCurrencyExchange|[[DailyDataDto](#schemadailydatadto)]|true|none||Danh sách dữ liệu trao đổi tiền tệ theo ngày|
|»»» date|string|true|none||Ngày giao dịch (YYYY-MM-DD)|
|»»» fromCurrency|string|true|none||Mã ngoại tệ nguồn|
|»»» exchangeReceiptId|number|true|none||Mã giao dịch nhận tiền tệ|
|»»» total|any|true|none||Tổng số tiền giao dịch hoặc chuỗi số dạng string|

*oneOf*

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|»»»» *anonymous*|number|false|none||none|

*xor*

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|»»»» *anonymous*|string|false|none||none|

*continued*

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|»»» totalExchange|any|true|none||Tổng số tiền quy đổi hoặc chuỗi số dạng string|

*oneOf*

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|»»»» *anonymous*|number|false|none||none|

*xor*

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|»»»» *anonymous*|string|false|none||none|

*continued*

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|»»» openingBalance|number|true|none||Số dư đầu kỳ|
|»»» closingBalance|number|true|none||Số dư cuối kỳ (mặc định 0)|
|»»» createBy|string|true|none||Người tạo giao dịch|
|»»» custommer|string|true|none||Tên khách hàng|
|»» rowsCurrencyReport|[[TypeOfCurrencyCodeDto](#schematypeofcurrencycodedto)]|true|none||Danh sách báo cáo loại tiền tệ|
|»»» currencyCode|string|true|none||Mã ngoại tệ trao đổi|
|»»» items|[[DetailReceiptReturnDbDto](#schemadetailreceiptreturndbdto)]|true|none||Danh sách chi tiết mệnh giá món trao đổi ngoại tệ|
|»»»» fromCurrency|string|true|none||Mã ngoại tệ khách mang tới trao đổi|
|»»»» toCurrency|string|true|none||Mã ngoại tệ khách muốn trao đổi|
|»»»» valueUnit|number|true|none||mệnh giá tiền|
|»»»» quality|number|true|none||Số lượng tờ mệnh giá|
|»»»» total|number|true|none||Tổng tiền thu được sau khi tính|
|»»»» exchangeRate|number|true|none||Tỉ giá nhận được khi trao đổi ngoại tệ|
|»»»» createBy|string|true|none||Tên tài khoản đã tạo|
|»»» total|number|true|none||số tiền ngoại tệ thu vào của món ngoại tệ sau khi tính|
|»»» totalExchange|number|true|none||tổng số tiền VND đổi được tại món ngoại tệ thu vào|

HTTP Status Code **400**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|object|true|none||dữ  liệu trả về từ lệnh (có thể null khi lỗi)|

HTTP Status Code **401**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|null|true|none||Dữ liệu trả về|

<a id="opIdReportExchangeController_createExpense"></a>

## POST Create expense invoice

POST /report-exchange/create-expense

API để tạo dữ liệu chi ghi nhận hệ thống

> Body Parameters

```json
{
  "dateQuery": "string",
  "currencyId": 0,
  "closingBalance": 0
}
```

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Authorization|header|string| no |none|
|body|body|[ExpenseInvoiceCreateDto](#schemaexpenseinvoicecreatedto)| no |none|

> Response Examples

> 200 Response

```json
{
  "statusCode": 200,
  "isSuccess": true,
  "message": "Thành công",
  "messageErrors": [],
  "payload": 5
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|API response|[ApiResponseNumber](#schemaapiresponsenumber)|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|Inline|
|502|[Bad Gateway](https://tools.ietf.org/html/rfc7231#section-6.6.3)|API response|[ApiResponseBad](#schemaapiresponsebad)|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|number|true|none||dữ  liệu trả về từ lệnh (có thể null khi lỗi)|

HTTP Status Code **400**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|null|false|none||Dữ liệu trả về|

HTTP Status Code **401**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|null|true|none||Dữ liệu trả về|

HTTP Status Code **502**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» statusCode|number|true|none||Mã trạng thái HTTP|
|» isSuccess|boolean|true|none||Trạng thái thành công|
|» message|string|true|none||Thông báo phản hồi|
|» messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|» payload|object|true|none||dữ  liệu trả về từ lệnh (có thể null khi lỗi)|

# Data Schema

<h2 id="tocS_CurrencyRateListReturnDbDto">CurrencyRateListReturnDbDto</h2>

<a id="schemacurrencyratelistreturndbdto"></a>
<a id="schema_CurrencyRateListReturnDbDto"></a>
<a id="tocScurrencyratelistreturndbdto"></a>
<a id="tocscurrencyratelistreturndbdto"></a>

```json
{
  "id": 0,
  "currencyCode": "string",
  "currencyName": "string",
  "currencyUnit": "string",
  "dateCreated": "string",
  "ca1": 0,
  "ca2": 0,
  "ca3": 0,
  "trs": 0
}

```

### Attribute

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|id|number|true|none||Mã id ngoại tệ|
|currencyCode|string|true|none||Mã ngoại tệ|
|currencyName|string|true|none||Tên ngoại tệ|
|currencyUnit|string|true|none||Đơn vị tính ngoại tệ|
|dateCreated|string|true|none||Ngày tỷ giá ngoại tệ được tạo|
|ca1|number¦null|true|none||Tỷ giá CA1 của ngoại tệ (USD)|
|ca2|number¦null|true|none||Tỷ giá CA2 của ngoại tệ (USD)|
|ca3|number¦null|true|none||Tỷ giá CA3 của ngoại tệ (USD)|
|trs|number¦null|true|none||Tỷ giá TRS của ngoại tệ (USD)|

<h2 id="tocS_CurrencyRateListGroupTimeDto">CurrencyRateListGroupTimeDto</h2>

<a id="schemacurrencyratelistgrouptimedto"></a>
<a id="schema_CurrencyRateListGroupTimeDto"></a>
<a id="tocScurrencyratelistgrouptimedto"></a>
<a id="tocscurrencyratelistgrouptimedto"></a>

```json
{
  "timeUpdate": "string",
  "items": [
    {
      "id": 0,
      "currencyCode": "string",
      "currencyName": "string",
      "currencyUnit": "string",
      "dateCreated": "string",
      "ca1": 0,
      "ca2": 0,
      "ca3": 0,
      "trs": 0
    }
  ]
}

```

### Attribute

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|timeUpdate|string|true|none||Thời gian thực hiện cập nhật tỷ giá|
|items|[[CurrencyRateListReturnDbDto](#schemacurrencyratelistreturndbdto)]|true|none||Danh sách các ngoại tệ kèm tỷ giá|

<h2 id="tocS_CurrencyEntity">CurrencyEntity</h2>

<a id="schemacurrencyentity"></a>
<a id="schema_CurrencyEntity"></a>
<a id="tocScurrencyentity"></a>
<a id="tocscurrencyentity"></a>

```json
{
  "id": 0,
  "currencyCode": "string",
  "currencyName": "string",
  "currencyUnit": "string",
  "currencyLocation": "string",
  "status": "string"
}

```

### Attribute

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|id|number|true|none||Mã id ngoại tệ|
|currencyCode|string|true|none||Mã ngoại tệ|
|currencyName|string|true|none||Tên ngoại tệ|
|currencyUnit|string|true|none||Đơn vị tính ngoại tệ|
|currencyLocation|string¦null|true|none||khu vực ngoại tệ đặt|
|status|string|true|none||Trạng thái ngoại tệ|

<h2 id="tocS_ApiResponse">ApiResponse</h2>

<a id="schemaapiresponse"></a>
<a id="schema_ApiResponse"></a>
<a id="tocSapiresponse"></a>
<a id="tocsapiresponse"></a>

```json
{
  "statusCode": 200,
  "isSuccess": true,
  "message": "Thành công",
  "messageErrors": [],
  "payload": {}
}

```

### Attribute

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|statusCode|number|true|none||Mã trạng thái HTTP|
|isSuccess|boolean|true|none||Trạng thái thành công|
|message|string|true|none||Thông báo phản hồi|
|messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|payload|object|true|none||Dữ liệu trả về|

<h2 id="tocS_AuthPayloadDto">AuthPayloadDto</h2>

<a id="schemaauthpayloaddto"></a>
<a id="schema_AuthPayloadDto"></a>
<a id="tocSauthpayloaddto"></a>
<a id="tocsauthpayloaddto"></a>

```json
{
  "username": "john_doe",
  "accessToken": "eyJhbGciOiJIUzI1NiIsInR...",
  "refreshToken": "eyJhbGciOiJIUzI1NiIsInR...",
  "role": "admin",
  "expired": "17061046756"
}

```

### Attribute

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|username|string|true|none||Tên đăng nhập của người dùng|
|accessToken|string|true|none||Access Token để xác thực|
|refreshToken|string|true|none||Refresh Token để làm mới Access Token|
|role|string|true|none||Vai trò của người dùng|
|expired|string|true|none||Thông tin về thời gian hết hạn|

<h2 id="tocS_ApiResponseNumber">ApiResponseNumber</h2>

<a id="schemaapiresponsenumber"></a>
<a id="schema_ApiResponseNumber"></a>
<a id="tocSapiresponsenumber"></a>
<a id="tocsapiresponsenumber"></a>

```json
{
  "statusCode": 200,
  "isSuccess": true,
  "message": "Thành công",
  "messageErrors": [],
  "payload": 5
}

```

### Attribute

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|statusCode|number|true|none||Mã trạng thái HTTP|
|isSuccess|boolean|true|none||Trạng thái thành công|
|message|string|true|none||Thông báo phản hồi|
|messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|payload|number|true|none||dữ  liệu trả về từ lệnh (có thể null khi lỗi)|

<h2 id="tocS_RefreshTokenDto">RefreshTokenDto</h2>

<a id="schemarefreshtokendto"></a>
<a id="schema_RefreshTokenDto"></a>
<a id="tocSrefreshtokendto"></a>
<a id="tocsrefreshtokendto"></a>

```json
{
  "refreshToken": "string"
}

```

### Attribute

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|refreshToken|string|false|none||none|

<h2 id="tocS_userAccountDtoGetUsername">userAccountDtoGetUsername</h2>

<a id="schemauseraccountdtogetusername"></a>
<a id="schema_userAccountDtoGetUsername"></a>
<a id="tocSuseraccountdtogetusername"></a>
<a id="tocsuseraccountdtogetusername"></a>

```json
{
  "username": "string"
}

```

### Attribute

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|username|string|false|none||none|

<h2 id="tocS_ApiResponseBad">ApiResponseBad</h2>

<a id="schemaapiresponsebad"></a>
<a id="schema_ApiResponseBad"></a>
<a id="tocSapiresponsebad"></a>
<a id="tocsapiresponsebad"></a>

```json
{
  "statusCode": 400,
  "isSuccess": false,
  "message": "Thất bại",
  "messageErrors": [
    "fail to processing program",
    "check log file"
  ],
  "payload": null
}

```

### Attribute

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|statusCode|number|true|none||Mã trạng thái HTTP|
|isSuccess|boolean|true|none||Trạng thái thành công|
|message|string|true|none||Thông báo phản hồi|
|messageErrors|[string]|true|none||Danh sách lỗi nếu có|
|payload|object|true|none||dữ  liệu trả về từ lệnh (có thể null khi lỗi)|

<h2 id="tocS_ReceiptDetailQueryDto">ReceiptDetailQueryDto</h2>

<a id="schemareceiptdetailquerydto"></a>
<a id="schema_ReceiptDetailQueryDto"></a>
<a id="tocSreceiptdetailquerydto"></a>
<a id="tocsreceiptdetailquerydto"></a>

```json
{
  "receiptId": "string"
}

```

### Attribute

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|receiptId|string|false|none||none|

<h2 id="tocS_ItemExchangeInvoiceCreateDto">ItemExchangeInvoiceCreateDto</h2>

<a id="schemaitemexchangeinvoicecreatedto"></a>
<a id="schema_ItemExchangeInvoiceCreateDto"></a>
<a id="tocSitemexchangeinvoicecreatedto"></a>
<a id="tocsitemexchangeinvoicecreatedto"></a>

```json
{
  "fromCurrencyId": 0,
  "toCurrencyId": 0,
  "unitValue": 0,
  "exchangeRate": 0,
  "quality": 0
}

```

### Attribute

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|fromCurrencyId|number|false|none||none|
|toCurrencyId|number|false|none||none|
|unitValue|number|false|none||none|
|exchangeRate|number|false|none||none|
|quality|number|false|none||none|

<h2 id="tocS_ExchangeInvoiceCreateDto">ExchangeInvoiceCreateDto</h2>

<a id="schemaexchangeinvoicecreatedto"></a>
<a id="schema_ExchangeInvoiceCreateDto"></a>
<a id="tocSexchangeinvoicecreatedto"></a>
<a id="tocsexchangeinvoicecreatedto"></a>

```json
{
  "customerName": "string",
  "passport": "string",
  "address": "string",
  "username": "string",
  "itemsDetail": [
    {
      "fromCurrencyId": 0,
      "toCurrencyId": 0,
      "unitValue": 0,
      "exchangeRate": 0,
      "quality": 0
    }
  ]
}

```

### Attribute

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|customerName|string|false|none||none|
|passport|string|false|none||none|
|address|string|false|none||none|
|username|string|false|none||none|
|itemsDetail|[[ItemExchangeInvoiceCreateDto](#schemaitemexchangeinvoicecreatedto)]|false|none||none|

<h2 id="tocS_ExchangeRateReturnDbDto">ExchangeRateReturnDbDto</h2>

<a id="schemaexchangeratereturndbdto"></a>
<a id="schema_ExchangeRateReturnDbDto"></a>
<a id="tocSexchangeratereturndbdto"></a>
<a id="tocsexchangeratereturndbdto"></a>

```json
{
  "currencyId": 2,
  "currencyCode": "USD",
  "currencyName": "Dollas",
  "currencyUnit": "Dollas",
  "exchangeRate": 24500,
  "sellRate": 24500,
  "buyRate": 24500
}

```

### Attribute

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|currencyId|number|true|none||Mã số ngoại tệ trên dữ liệu hệ thống|
|currencyCode|string|true|none||Mã ngoại tệ trên hệ thống|
|currencyName|string|true|none||Tên ngoại tệ trên hệ thống|
|currencyUnit|string|true|none||Đơn vị tính ngoại tệ trên hệ thống|
|exchangeRate|number|true|none||Tỷ giá ngoại tệ trao đổi trên hệ thống|
|sellRate|number|true|none||Tỷ giá mua vào tiền mặt ngoại tệ trên hệ thống|
|buyRate|number|true|none||Tỷ giá bán ra tiền mặt ngoại tệ trên hệ thống|

<h2 id="tocS_ExchangeRateQueryDto">ExchangeRateQueryDto</h2>

<a id="schemaexchangeratequerydto"></a>
<a id="schema_ExchangeRateQueryDto"></a>
<a id="tocSexchangeratequerydto"></a>
<a id="tocsexchangeratequerydto"></a>

```json
{
  "dateQuery": "string"
}

```

### Attribute

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|dateQuery|string|false|none||none|

<h2 id="tocS_CurrencyRateItemCreateDbDto">CurrencyRateItemCreateDbDto</h2>

<a id="schemacurrencyrateitemcreatedbdto"></a>
<a id="schema_CurrencyRateItemCreateDbDto"></a>
<a id="tocScurrencyrateitemcreatedbdto"></a>
<a id="tocscurrencyrateitemcreatedbdto"></a>

```json
{
  "currencyCode": "string",
  "ca1": 0,
  "ca2": 0,
  "ca3": 0,
  "trs": 0
}

```

### Attribute

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|currencyCode|string|false|none||none|
|ca1|number|false|none||none|
|ca2|number|false|none||none|
|ca3|number|false|none||none|
|trs|number|false|none||none|

<h2 id="tocS_GetPdfDayDto">GetPdfDayDto</h2>

<a id="schemagetpdfdaydto"></a>
<a id="schema_GetPdfDayDto"></a>
<a id="tocSgetpdfdaydto"></a>
<a id="tocsgetpdfdaydto"></a>

```json
{
  "month": 0,
  "year": 0,
  "fromId": 0,
  "toId": 0,
  "currencyCode": "string",
  "fromDate": "string",
  "toDate": "string"
}

```

### Attribute

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|month|number|false|none||none|
|year|number|false|none||none|
|fromId|number|false|none||none|
|toId|number|false|none||none|
|currencyCode|string|false|none||none|
|fromDate|string|false|none||none|
|toDate|string|false|none||none|

<h2 id="tocS_ReportByDayQueryDto">ReportByDayQueryDto</h2>

<a id="schemareportbydayquerydto"></a>
<a id="schema_ReportByDayQueryDto"></a>
<a id="tocSreportbydayquerydto"></a>
<a id="tocsreportbydayquerydto"></a>

```json
{
  "fromDate": "string",
  "toDate": "string",
  "currencyCode": "string",
  "fromId": 0,
  "toId": 0
}

```

### Attribute

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|fromDate|string|false|none||none|
|toDate|string|false|none||none|
|currencyCode|string|false|none||none|
|fromId|number|false|none||none|
|toId|number|false|none||none|

<h2 id="tocS_ReportByCurrencyQueryDto">ReportByCurrencyQueryDto</h2>

<a id="schemareportbycurrencyquerydto"></a>
<a id="schema_ReportByCurrencyQueryDto"></a>
<a id="tocSreportbycurrencyquerydto"></a>
<a id="tocsreportbycurrencyquerydto"></a>

```json
{
  "currencyCode": "string",
  "fromExchangeId": 0,
  "toExchangeId": 0
}

```

### Attribute

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|currencyCode|string|false|none||none|
|fromExchangeId|number|false|none||none|
|toExchangeId|number|false|none||none|

<h2 id="tocS_ExpenseInvoiceCreateDto">ExpenseInvoiceCreateDto</h2>

<a id="schemaexpenseinvoicecreatedto"></a>
<a id="schema_ExpenseInvoiceCreateDto"></a>
<a id="tocSexpenseinvoicecreatedto"></a>
<a id="tocsexpenseinvoicecreatedto"></a>

```json
{
  "dateQuery": "string",
  "currencyId": 0,
  "closingBalance": 0
}

```

### Attribute

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|dateQuery|string|false|none||none|
|currencyId|number|false|none||none|
|closingBalance|number|false|none||none|

<h2 id="tocS_CreateExchangeReceiptDto">CreateExchangeReceiptDto</h2>

<a id="schemacreateexchangereceiptdto"></a>
<a id="schema_CreateExchangeReceiptDto"></a>
<a id="tocScreateexchangereceiptdto"></a>
<a id="tocscreateexchangereceiptdto"></a>

```json
{
  "created_by": "string",
  "updated_by": "string",
  "customer_name": "string",
  "passport": "string",
  "address": "string",
  "status": "string",
  "content": "string"
}

```

### Attribute

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|created_by|string|false|none||none|
|updated_by|string|false|none||none|
|customer_name|string|false|none||none|
|passport|string|false|none||none|
|address|string|false|none||none|
|status|string|false|none||none|
|content|string|false|none||none|

<h2 id="tocS_ReceiptItemReturnDto">ReceiptItemReturnDto</h2>

<a id="schemareceiptitemreturndto"></a>
<a id="schema_ReceiptItemReturnDto"></a>
<a id="tocSreceiptitemreturndto"></a>
<a id="tocsreceiptitemreturndto"></a>

```json
{
  "id": "101",
  "createdDate": "2025-03-24T12:00:00Z",
  "createdBy": "Username 1",
  "updatedDate": "string",
  "updatedBy": "string",
  "customerName": "Khách Hàng A",
  "passport": "015884785",
  "address": "Địa chỉ A",
  "status": "NEW",
  "totalExchange": "NEW"
}

```

### Attribute

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|id|number|true|none||Số hóa đơn|
|createdDate|string|true|none||Ngày tạo hóa đơn|
|createdBy|string|true|none||Tên tài khoản đã tạo hóa đơn|
|updatedDate|string¦null|false|none||Ngày cập nhật hóa đơn|
|updatedBy|string¦null|false|none||Tên tài khoản đã cập nhật hóa đơn|
|customerName|string|true|none||Tên người nộp tiền của hóa đơn|
|passport|string|true|none||Số passport của người nộp tiền của hóa đơn|
|address|string|true|none||Địa chỉ của người nộp tiền của hóa đơn|
|status|string|true|none||Trạng thái hóa đơn|
|totalExchange|number|true|none||Tổng tiền VND đã trao đổi trong hóa đơn|

<h2 id="tocS_ReceiptDetailReturnDbDto">ReceiptDetailReturnDbDto</h2>

<a id="schemareceiptdetailreturndbdto"></a>
<a id="schema_ReceiptDetailReturnDbDto"></a>
<a id="tocSreceiptdetailreturndbdto"></a>
<a id="tocsreceiptdetailreturndbdto"></a>

```json
{
  "id": "23",
  "createdDate": "2025-03-24 12:00:00",
  "createdBy": "Username",
  "updatedDate": "string",
  "updatedBy": "string",
  "customerName": "Khách Hàng A",
  "passport": "015884785",
  "address": "Địa chỉ A",
  "status": "NEW",
  "detail": [
    {
      "currencyCode": "USD",
      "items": [
        {
          "fromCurrency": "1",
          "toCurrency": "1",
          "valueUnit": 0,
          "quality": 5,
          "total": 0,
          "exchangeRate": 0,
          "createBy": "Username"
        }
      ],
      "total": 0,
      "totalExchange": 0
    }
  ],
  "totalExchange": 112000
}

```

### Attribute

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|id|number|true|none||Số hóa đơn|
|createdDate|string|true|none||Ngày tạo hóa đơn|
|createdBy|string|true|none||Tài khoản tạo hóa đơn|
|updatedDate|string¦null|false|none||Ngày chỉnh sửa hóa đơn|
|updatedBy|string¦null|false|none||Tài khoản cập nhật hóa đơn|
|customerName|string|true|none||Tên người nộp tiền của hóa đơn|
|passport|string|true|none||Số passport của người nộp tiền của hóa đơn|
|address|string|true|none||Địa chỉ của người nộp tiền của hóa đơn|
|status|string|true|none||Trạng thái hóa đơn|
|detail|[[TypeOfCurrencyCodeDto](#schematypeofcurrencycodedto)]|true|none||Danh sách chi tiết loại tiền tệ|
|totalExchange|number|true|none||Tổng tiền VND sau khi tính toán tất cả chi tiết trong hóa đơn|

<h2 id="tocS_DetailReceiptReturnDbDto">DetailReceiptReturnDbDto</h2>

<a id="schemadetailreceiptreturndbdto"></a>
<a id="schema_DetailReceiptReturnDbDto"></a>
<a id="tocSdetailreceiptreturndbdto"></a>
<a id="tocsdetailreceiptreturndbdto"></a>

```json
{
  "fromCurrency": "1",
  "toCurrency": "1",
  "valueUnit": 0,
  "quality": 5,
  "total": 0,
  "exchangeRate": 0,
  "createBy": "Username"
}

```

### Attribute

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|fromCurrency|string|true|none||Mã ngoại tệ khách mang tới trao đổi|
|toCurrency|string|true|none||Mã ngoại tệ khách muốn trao đổi|
|valueUnit|number|true|none||mệnh giá tiền|
|quality|number|true|none||Số lượng tờ mệnh giá|
|total|number|true|none||Tổng tiền thu được sau khi tính|
|exchangeRate|number|true|none||Tỉ giá nhận được khi trao đổi ngoại tệ|
|createBy|string|true|none||Tên tài khoản đã tạo|

<h2 id="tocS_TypeOfCurrencyCodeDto">TypeOfCurrencyCodeDto</h2>

<a id="schematypeofcurrencycodedto"></a>
<a id="schema_TypeOfCurrencyCodeDto"></a>
<a id="tocStypeofcurrencycodedto"></a>
<a id="tocstypeofcurrencycodedto"></a>

```json
{
  "currencyCode": "USD",
  "items": [
    {
      "fromCurrency": "1",
      "toCurrency": "1",
      "valueUnit": 0,
      "quality": 5,
      "total": 0,
      "exchangeRate": 0,
      "createBy": "Username"
    }
  ],
  "total": 0,
  "totalExchange": 0
}

```

### Attribute

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|currencyCode|string|true|none||Mã ngoại tệ trao đổi|
|items|[[DetailReceiptReturnDbDto](#schemadetailreceiptreturndbdto)]|true|none||Danh sách chi tiết mệnh giá món trao đổi ngoại tệ|
|total|number|true|none||số tiền ngoại tệ thu vào của món ngoại tệ sau khi tính|
|totalExchange|number|true|none||tổng số tiền VND đổi được tại món ngoại tệ thu vào|

<h2 id="tocS_CurrencyRateListCreateDto">CurrencyRateListCreateDto</h2>

<a id="schemacurrencyratelistcreatedto"></a>
<a id="schema_CurrencyRateListCreateDto"></a>
<a id="tocScurrencyratelistcreatedto"></a>
<a id="tocscurrencyratelistcreatedto"></a>

```json
{
  "timeUpdate": "string",
  "items": [
    {
      "currencyCode": "string",
      "ca1": 0,
      "ca2": 0,
      "ca3": 0,
      "trs": 0
    }
  ]
}

```

### Attribute

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|timeUpdate|string|false|none||none|
|items|[[CurrencyRateItemCreateDbDto](#schemacurrencyrateitemcreatedbdto)]|false|none||none|

<h2 id="tocS_ReportByDayRes">ReportByDayRes</h2>

<a id="schemareportbydayres"></a>
<a id="schema_ReportByDayRes"></a>
<a id="tocSreportbydayres"></a>
<a id="tocsreportbydayres"></a>

```json
{
  "uniqueCurrencies": [
    "USD"
  ],
  "rowsExpense": [
    {
      "currencyCode": "USD",
      "closingBalance": 0,
      "tranxDate": "2025-03-24 12:00:00",
      "openingBalance": 0
    }
  ],
  "rowsCurrencyExchange": [
    {
      "date": "2025-03-27",
      "fromCurrency": "USD",
      "exchangeReceiptId": 0,
      "total": 1000,
      "totalExchange": 950,
      "openingBalance": 500,
      "closingBalance": 0,
      "createBy": "admin",
      "custommer": "Nguyễn Văn A"
    }
  ],
  "rowsCurrencyReport": [
    {
      "currencyCode": "USD",
      "items": [
        {
          "fromCurrency": "1",
          "toCurrency": "1",
          "valueUnit": 0,
          "quality": 5,
          "total": 0,
          "exchangeRate": 0,
          "createBy": "Username"
        }
      ],
      "total": 0,
      "totalExchange": 0
    }
  ]
}

```

### Attribute

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|uniqueCurrencies|[string]|true|none||Danh sách mã ngoại tệ trao đổi|
|rowsExpense|[[ReportExpenseReturnDbDto](#schemareportexpensereturndbdto)]|true|none||Danh sách chi phí theo ngày|
|rowsCurrencyExchange|[[DailyDataDto](#schemadailydatadto)]|true|none||Danh sách dữ liệu trao đổi tiền tệ theo ngày|
|rowsCurrencyReport|[[TypeOfCurrencyCodeDto](#schematypeofcurrencycodedto)]|true|none||Danh sách báo cáo loại tiền tệ|

<h2 id="tocS_userAccountDto">userAccountDto</h2>

<a id="schemauseraccountdto"></a>
<a id="schema_userAccountDto"></a>
<a id="tocSuseraccountdto"></a>
<a id="tocsuseraccountdto"></a>

```json
{
  "username": "string",
  "password": "string",
  "ip": "string"
}

```

### Attribute

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|username|string|false|none||Tên tài khoản đăng nhập|
|password|string|false|none||Mật khẩu đăng nhập|
|ip|string|false|none||ip máy đăng nhập|

<h2 id="tocS_ReceiptQueryDto">ReceiptQueryDto</h2>

<a id="schemareceiptquerydto"></a>
<a id="schema_ReceiptQueryDto"></a>
<a id="tocSreceiptquerydto"></a>
<a id="tocsreceiptquerydto"></a>

```json
{
  "receiptId": "string",
  "currencyCode": "string",
  "fromDate": "string",
  "toDate": "string",
  "minAmount": 0,
  "maxAmount": 0,
  "fromId": 0,
  "toId": 0,
  "customerName": "string",
  "status": "NEW"
}

```

### Attribute

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|receiptId|string|false|none||none|
|currencyCode|string|false|none||none|
|fromDate|string|false|none||none|
|toDate|string|false|none||none|
|minAmount|number|false|none||none|
|maxAmount|number|false|none||none|
|fromId|number|false|none||none|
|toId|number|false|none||none|
|customerName|string|false|none||none|
|status|string|false|none||none|

#### Enum

|Name|Value|
|---|---|
|status|NEW|
|status|PUBLICED|
|status|CANCELED|
|status|COMPLETED|

<h2 id="tocS_ReportExpenseReturnDbDto">ReportExpenseReturnDbDto</h2>

<a id="schemareportexpensereturndbdto"></a>
<a id="schema_ReportExpenseReturnDbDto"></a>
<a id="tocSreportexpensereturndbdto"></a>
<a id="tocsreportexpensereturndbdto"></a>

```json
{
  "currencyCode": "USD",
  "closingBalance": 0,
  "tranxDate": "2025-03-24 12:00:00",
  "openingBalance": 0
}

```

### Attribute

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|currencyCode|string|true|none||Mã ngoại tệ thực hiện nhiệm chi|
|closingBalance|number|true|none||Số tiền đã thực hiện chi|
|tranxDate|string|true|none||ngày thực hiện nhiệm chi|
|openingBalance|number|true|none||số dư tồn kho sau khi nhiệm chi|

<h2 id="tocS_DailyDataDto">DailyDataDto</h2>

<a id="schemadailydatadto"></a>
<a id="schema_DailyDataDto"></a>
<a id="tocSdailydatadto"></a>
<a id="tocsdailydatadto"></a>

```json
{
  "date": "2025-03-27",
  "fromCurrency": "USD",
  "exchangeReceiptId": 0,
  "total": 1000,
  "totalExchange": 950,
  "openingBalance": 500,
  "closingBalance": 0,
  "createBy": "admin",
  "custommer": "Nguyễn Văn A"
}

```

### Attribute

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|date|string|true|none||Ngày giao dịch (YYYY-MM-DD)|
|fromCurrency|string|true|none||Mã ngoại tệ nguồn|
|exchangeReceiptId|number|true|none||Mã giao dịch nhận tiền tệ|
|total|any|true|none||Tổng số tiền giao dịch hoặc chuỗi số dạng string|

oneOf

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|» *anonymous*|number|false|none||none|

xor

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|» *anonymous*|string|false|none||none|

continued

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|totalExchange|any|true|none||Tổng số tiền quy đổi hoặc chuỗi số dạng string|

oneOf

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|» *anonymous*|number|false|none||none|

xor

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|» *anonymous*|string|false|none||none|

continued

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|openingBalance|number|true|none||Số dư đầu kỳ|
|closingBalance|number|true|none||Số dư cuối kỳ (mặc định 0)|
|createBy|string|true|none||Người tạo giao dịch|
|custommer|string|true|none||Tên khách hàng|

