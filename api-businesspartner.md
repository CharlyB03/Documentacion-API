# API BusinessPartner

Se detalla sobre el funcionamiento del API para Terceros

```
GET http://186.4.199.239:61034/estandar/ws/ec.com.sidesoft.custom.ws.api.businessPartner?taxId=1799999999001
```

#### Headers

<table><thead><tr><th></th><th width="374"></th></tr></thead><tbody><tr><td>Content-Type</td><td>application/json</td></tr></tbody></table>

#### Autenticacion

> Username: Openbravo
>
> Password: 1234

### Prueba de EndPoint - GET&#x20;

Para poder obtener alguna informacion de nuestro tercero hacemos la busqueda por medio del identificador&#x20;

```
http://186.4.199.239:61034/estandar/ws/ec.com.sidesoft.custom.ws.api.businessPartner?taxId=http://localhost:8080/estandar/ws/ec.com.sidesoft.custom.ws.api.businessPartner?taxId=1799999999001
```

#### Resultado: OK

```json
{
  "status": 0,
  "data": {
    "id": "904FB349FD0B4B07BF7A1CA30DC27525",
    "taxId": "1723376289",
    "taxIdType": "D",
    "fiscalName": "AMAYA GAVILANES ALISSON MELISSA",
    "commercialName": "AMAYA GAVILANES ALISSON MELISSA",
    "email": "test@test.com",
    "typeTaxPayerId": "94E2DE7A29A941A79AF03DB239F4AB7D",
    "addresses": [
      {
        "id": "FD5F608AF96D4C7182D5A123FF72823C",
        "address": "FRANCISCO MATIZ S3-32 Y BALTAZAR GARCÍA, LOMA DE PUENGASI",
        "reference": "FRANCISCO MATIZ S3-32 Y BALTAZAR GARCÍA, LOMA DE PUENGASI",
        "countryCode": "EC",
        "province": "01",
        "isShipping": false,
        "isBilling": false,
        "phoneNumber": "0998450768",
        "alternativePhoneNumber": "0994906630"
      }
    ],
    "contactPersons": []
  },
  "message": ""
}
```

### Prueba de EndPoint -  PUT

Como vemos en el GET anterior tenemos en province un valor de 01 Ahora con este endpoint vamos a actualizar a 17 que es otro codigo de otra provincia&#x20;

```
PUT http://186.4.199.239:61034/estandar/ws/ec.com.sidesoft.custom.ws.api.businessPartner
```

#### Headers

<table><thead><tr><th></th><th width="374"></th></tr></thead><tbody><tr><td>Content-Type</td><td>application/json</td></tr></tbody></table>

#### Autenticacion

> Username: Openbravo
>
> Password: 1234

#### Ejemplo&#x20;

```
http://186.4.199.239:61034/estandar/ws/ec.com.sidesoft.custom.ws.api.businessPartner
```

#### Body

```json
{
  "taxId": "1723376289",
  "fiscalName": "AMAYA GAVILANES ALISSON MELISSA",
  "commercialName": "AMAYA GAVILANES ALISSON MELISSA",
  "email": "test@test.com",
  "addresses": [
    {
      "address": "FRANCISCO MATIZ S3-32 Y BALTAZAR GARCÍA, LOMA DE PUENGASI ",
      "reference": "FRANCISCO MATIZ S3-32 Y BALTAZAR GARCÍA, LOMA DE PUENGASI ",
      "countryCode": "EC",
      "province": "17",
      "canton": "1701",
      "isShipping": false,
      "isBilling": false,
      "phoneNumber": "0998450768",
      "alternativePhoneNumber": "0994906630"
    }
  ],
  "contactPersons": []
}

```

#### Resultado: OK

```json
{
  "status": 0,
  "data": {
    "taxId": "1723376289",
    "fiscalName": "AMAYA GAVILANES ALISSON MELISSA",
    "commercialName": "AMAYA GAVILANES ALISSON MELISSA",
    "email": "test@test.com",
    "addresses": [
      {
        "address": "FRANCISCO MATIZ S3-32 Y BALTAZAR GARCÍA, LOMA DE PUENGASI ",
        "reference": "FRANCISCO MATIZ S3-32 Y BALTAZAR GARCÍA, LOMA DE PUENGASI ",
        "countryCode": "EC",
        "province": "17",
        "canton": "1701",
        "isShipping": false,
        "isBilling": false,
        "phoneNumber": "0998450768",
        "alternativePhoneNumber": "0994906630"
      }
    ],
    "contactPersons": [],
    "id": "904FB349FD0B4B07BF7A1CA30DC27525"
  },
  "message": ""
}
```

### Prueba EndPoint - POST

Ahora vamos a crear un tercero de prueba para ver el funcionamiento del endpoint

```
POST http://186.4.199.239:61034/estandar/ws/ec.com.sidesoft.custom.ws.api.businessPartner
```

#### Headers

<table><thead><tr><th></th><th width="374"></th></tr></thead><tbody><tr><td>Content-Type</td><td>application/json</td></tr></tbody></table>

#### Autenticacion

> Username: Openbravo
>
> Password: 1234

#### Ejemplo&#x20;

```
http://186.4.199.239:61034/estandar/ws/ec.com.sidesoft.custom.ws.api.businessPartner
```

#### Body

```json
{
  "taxId": "1750253344123",
  "taxIdType": "R",
  "fiscalName": "CLIENTE PRUEBA WS",
  "commercialName": "CLIENTE PRUEBA WS",
  "email": "cliente.prueba.ws@test.com",
  "url": "https://example.com",
  "addresses": [
    {
      "address": "Av. Amazonas N34-123 y Eloy Alfaro",
      "reference": "Edificio X, piso 2",
      "countryCode": "EC",
      "province": "17",
      "canton": "1701",
      "isShipping": true,
      "isBilling": true,
      "phoneNumber": "0999999999",
      "alternativePhoneNumber": "022222222"
    }
  ],
  "contactPersons": [
    {
      "firstname": "Juan",
      "lastname": "Perez",
      "email": "juan.perez@test.com",
      "phoneNumber": "0999999998",
      "alternativePhoneNumber": "022222223",
      "position": "Compras",
      "comments": "Creado desde WS"
    }
  ]
}

```

#### Resultado: OK

```json
{
  "status": 0,
  "data": {
    "taxId": "1750253344123",
    "taxIdType": "R",
    "fiscalName": "CLIENTE PRUEBA WS",
    "commercialName": "CLIENTE PRUEBA WS",
    "email": "cliente.prueba.ws@test.com",
    "url": "https://example.com",
    "addresses": [
      {
        "address": "Av. Amazonas N34-123 y Eloy Alfaro",
        "reference": "Edificio X, piso 2",
        "countryCode": "EC",
        "province": "17",
        "canton": "1701",
        "isShipping": true,
        "isBilling": true,
        "phoneNumber": "0999999999",
        "alternativePhoneNumber": "022222222",
        "id": "1D3076D54A2149DC91DCC7CA87CAE225"
      }
    ],
    "contactPersons": [
      {
        "firstname": "Juan",
        "lastname": "Perez",
        "email": "juan.perez@test.com",
        "phoneNumber": "0999999998",
        "alternativePhoneNumber": "022222223",
        "position": "Compras",
        "comments": "Creado desde WS",
        "id": "F1F83E1C18B14F1698ACDE8E8FEC7AF2"
      }
    ],
    "id": "A567F9031A104F9B87249B982A7E3A8F"
  },
  "message": ""
}
```
