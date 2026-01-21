# Api para Productos

Se detalla sobre el funcionamiento del API para productos

```
GET http://186.4.199.239:61034/estandar/ws/ec.com.sidesoft.custom.ws.api.Products
```

#### Headers

<table><thead><tr><th></th><th width="374"></th></tr></thead><tbody><tr><td>Content-Type</td><td>application/json</td></tr></tbody></table>

#### Autenticacion

> Username: Openbravo
>
> Password: 1234

### Prueba de EndPoint - GET&#x20;

```
http://186.4.199.239:61034/estandar/ws/ec.com.sidesoft.custom.ws.api.Products?code=0013
```

Resultado OK :

```json
{
  "status": 0,
  "data": {
    "id": "D2B0F81E966447A5B965C1AA114DAD75",
    "sku": "0013",
    "name": "PAN 1",
    "upc": "null",
    "category": "31_SUMINISTRO SS",
    "unit": {
      "id": "100",
      "name": "Unit"
    },
    "isStocked": false,
    "isPurchased": true,
    "isSale": true,
    "isGeneric": false,
    "productType": "I",
    "priceList": [
      {
        "id": "BE41AA2D48A7481EA3DC7FE99F2F1407",
        "name": "COMPRA-DOLARES",
        "cost": 0,
        "unitPrice": 10,
        "listPrice": 10,
        "limitPrice": 0,
        "isTaxIncluded": false,
        "isSalePriceList": false
      },
      {
        "id": "B7D1B99783474B3A85FEB736D29C9724",
        "name": "VENTA-DOLARES",
        "cost": 0,
        "unitPrice": 19,
        "listPrice": 19,
        "limitPrice": 0,
        "isTaxIncluded": false,
        "isSalePriceList": true
      }
    ],
    "prices": [
      {
        "priceList": "COMPRA-DOLARES",
        "price": 10
      },
      {
        "priceList": "VENTA-DOLARES",
        "price": 19
      }
    ]
  },
  "message": ""
}
```

### Prueba de EndPoint -  PUT

Este endpoint nos ayudara a actualizar un registro de productos&#x20;

```
PUT http://186.4.199.239:61034/estandar/ws/ec.com.sidesoft.custom.ws.api.Products
```

#### Headers

<table><thead><tr><th></th><th width="374"></th></tr></thead><tbody><tr><td>Content-Type</td><td>application/json</td></tr></tbody></table>

#### Autenticacion

> Username: Openbravo
>
> Password: 1234

#### Ejemplo&#x20;

```
http://186.4.199.239:61034/estandar/ws/ec.com.sidesoft.custom.ws.api.Products
```

#### Body

```json
{
  "sku": "0013",
  "name": "PAN 1",
  "upc": null,
  "categoryCode": "31",
  "uomCode": "100",
  "isStocked": false,
  "isPurchased": true,
  "isSale": true,
  "isGeneric": false,
  "productType": "I",
  "prices": [
    {
      "priceListCode": "COMPRA-DOLARES",
      "standardPrice": 10,
      "listPrice": 10,
      "priceLimit": 0,
      "cost": 0
    },
    {
      "priceListCode": "VENTA-DOLARES",
      "standardPrice": 19,
      "listPrice": 19,
      "priceLimit": 0,
      "cost": 0
    }
  ]
}

```

#### Resultado: OK

```json
{3 items
"status":0
"data":{13 items
"id":"D2B0F81E966447A5B965C1AA114DAD75"
"sku":"0013"
"name":"PAN 1"
"upc":"null"
"category":"31_SUMINISTRO SS"
"unit":{2 items
"id":"100"
"name":"Unit"
}
"isStocked":false
"isPurchased":true
"isSale":true
"isGeneric":false
"productType":"I"
"priceList":[2 items
0:{8 items
"id":"BE41AA2D48A7481EA3DC7FE99F2F1407"
"name":"COMPRA-DOLARES"
"cost":0
"unitPrice":10
"listPrice":10
"limitPrice":0
"isTaxIncluded":false
"isSalePriceList":false
}
1:{8 items
"id":"B7D1B99783474B3A85FEB736D29C9724"
"name":"VENTA-DOLARES"
"cost":0
"unitPrice":19
"listPrice":19
"limitPrice":0
"isTaxIncluded":false
"isSalePriceList":true
}
]
"prices":[2 items
0:{2 items
"priceList":"COMPRA-DOLARES"
"price":10
}
1:{2 items
"priceList":"VENTA-DOLARES"
"price":19
}
]
}
"message":""
}
```



### Prueba EndPoint - POST

Ahora vamos a crear un tercero de prueba para ver el funcionamiento del endpoint

```
POST http://186.4.199.239:61034/estandar/ws/ec.com.sidesoft.custom.ws.api.Products
```

#### Headers

<table><thead><tr><th></th><th width="374"></th></tr></thead><tbody><tr><td>Content-Type</td><td>application/json</td></tr></tbody></table>

#### Autenticacion

> Username: Openbravo
>
> Password: 1234

#### Ejemplo&#x20;

```
http://186.4.199.239:61034/estandar/ws/ec.com.sidesoft.custom.ws.api.Products
```

#### Body

```json
{
  "sku": "PRUEBA-WS-001",
  "name": "PRODUCTO PRUEBA WS",
  "upc": null,
  "uomCode": "100",
  "categoryCode": "31",
  "taxCategoryCode": "RETENCIONES IVA",
  "productType": "I",
  "isStocked": true,
  "isPurchased": true,
  "isSale": true,
  "prices": [
    {
      "priceListCode": "VENTA-DOLARES",
      "standardPrice": 4,
      "listPrice": 4,
      "priceLimit": 0,
      "cost": 0
    }
  ]
}

```

#### Resultado: OK

```json
{
  "status": 0,
  "data": {
    "id": "B5CD1C53BBA94C5ABE5D44B73828942F",
    "sku": "PRUEBA-WS-001",
    "name": "PRODUCTO PRUEBA WS",
    "upc": "null",
    "category": "31_PRODUCTO DE CONTROL",
    "unit": {
      "id": "100",
      "name": "Unit"
    },
    "isStocked": true,
    "isPurchased": true,
    "isSale": true,
    "isGeneric": false,
    "productType": "I",
    "priceList": [],
    "prices": []
  },
  "message": ""
}
```
