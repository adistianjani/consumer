## Consumer

### Registrasi consumer

- Endpoint
  - /consumer/regist
- Method
  - POST
- Request Body
  - name = string
  - email = string
  - password = string , min 6
  - phone_number = int
  - address = string
- Response

```json
{
  "message": "Input Success"
}
```

### Login consumer

- Endpoint
  - /consumer/login
- Method
  - POST
- Request Body
  - email = string
  - password = string , min 6
- Response

```json
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MTcsImlhdCI6MTY2MTkzNTQ0OH0.9tUJRdqx3D4KlCEYxXcPiMNo7tPAeYOXUdG8_HtKljg",
  "data": [
    {
      "id": 17,
      "name": "contoh",
      "email": "contoh@gmail.com",
      "password": "$2b$10$PFvpFmnL9AuAPpRzHvYTzuAainD3dgbEnJnchzydp7onUQqvEORF2",
      "phone_number": "012345678901",
      "address": "jl contoh no 2"
    }
  ]
}
```

### Get all fish consumer

- Endpoint
  - /consumer/ikan/all
- Method
  - GET
- Response

```json
{
  "banyak": 8,
  "data": [
    {
      "id_fish": 1,
      "name": "arwana",
      "price": 5000
    },
    {
      "id_fish": 2,
      "name": "megalodon",
      "price": 10000
    },
    {
      "id_fish": 3,
      "name": "cupang",
      "price": 2000
    },
    {
      "id_fish": 4,
      "name": "megalodon",
      "price": 9000
    },
    {
      "id_fish": 5,
      "name": "biawak",
      "price": 6000
    },
    {
      "id_fish": 6,
      "name": "gurame",
      "price": 2000
    },
    {
      "id_fish": 48,
      "name": "bandeng",
      "price": 15000
    },
    {
      "id_fish": 49,
      "name": "bandeng",
      "price": 15000
    }
  ]
}
```

### Search fish consumer

- Endpoint
  - /consumer/ikan/:namaIkan
- Method
  - GET
- Request Params
  - namaIkan = string
- Response

```json
{
  "banyak": 2,
  "data": [
    {
      "id_fish": 2,
      "name": "megalodon",
      "price": 10000
    },
    {
      "id_fish": 4,
      "name": "megalodon",
      "price": 9000
    }
  ]
}
```

### Get detail fish consumer

- Endpoint
  - /consumer/ikan/detail/:idIkan
- Method
  - GET
- Request Params
  - idIkan = int

```json
{
  "banyak": 1,
  "data": [
    {
      "id_fish": 2,
      "name": "megalodon",
      "location": "konoha",
      "weight": 950,
      "price": 10000
    }
  ]
}
```

### Get cart consumer

- Endpoint
  - /consumer/keranjang/input
- Method
  - GET
- Request Params
  - idConsumer = int
- Response

```json
{
  "banyak": 5,
  "data": [
    {
      "id_cart": 1,
      "id_fish": 2,
      "name_fish": "megalodon",
      "weight": 100,
      "price": 10000,
      "notes": "potong 3",
      "id_consumer": 1
    },
    {
      "id_cart": 2,
      "id_fish": 2,
      "name_fish": "megalodon",
      "weight": 100,
      "price": 10000,
      "notes": "potong 50",
      "id_consumer": 1
    },
    {
      "id_cart": 3,
      "id_fish": 3,
      "name_fish": "cupang",
      "weight": 5,
      "price": 2000,
      "notes": "utuh",
      "id_consumer": 1
    },
    {
      "id_cart": 5,
      "id_fish": 2,
      "name_fish": "megalodon",
      "weight": 10,
      "price": 10000,
      "notes": "potong 3",
      "id_consumer": 1
    },
    {
      "id_cart": 7,
      "id_fish": 1,
      "name_fish": "arwana",
      "weight": 1,
      "price": 5000,
      "notes": "x",
      "id_consumer": 1
    }
  ]
}
```

### Input cart consumer

- Endpoint
  - /consumer/keranjang/:idConsumer
- Method
  - POST
- Request Params
  - email = string
  - password = string , min 6
- Request Body
  - id_fish = int
  - id_consumer = int
  - notes = string
  - weight = int
- Response

```json
{
  "message": "Input Success"
}
```

### Edit weight cart consumer

- Endpoint
  - /consumer/keranjang/edit/weight/:idCart
- Method
  - PUT
- Request Params
  - idCart = int
- Request Body
  - weight = int
- Response

```json
{
  "message": "Edit Success"
}
```

### Delete cart consumer

- Endpoint
  - /consumer/keranjang/delete/:idCart
- Method
  - DELETE
- Request Params
  - idCart = int
- Response

```json
{
  "message": "Delete Success"
}
```

### Get order consumer

- Endpoint
  - /consumer/pesanan/input
- Method
  - GET
- Request Params
  - idConsumer = int
- Response

```json
{
  "banyak": 2,
  "data": [
    {
      "id_ordering": "O1",
      "consumer_name": "tsubasa",
      "date": "2008-11-11T13:23:44.000Z",
      "fish_name": "arwana",
      "weight": 10,
      "fish_price": 5000
    },
    {
      "id_ordering": "O1",
      "consumer_name": "tsubasa",
      "date": "2008-11-11T13:23:44.000Z",
      "fish_name": "megalodon",
      "weight": 10,
      "fish_price": 10000
    }
  ]
}
```

### Input order consumer

- Endpoint
  - /consumer/pesanan/input/detail
- Method
  - POST
- Request Body
  - id = string
  - date = format(YYYY-MM-DD hh:mm:ss)
  - notes = string
  - status = string
- Response

```json
{
  "message": "Input Success"
}
```

### Input detail order consumer

- Endpoint
  - /consumer/pesanan/:idConsumer
- Method
  - POST
- Request Body
  - id_ordering = string
  - notes = string
  - weight = int
  - id_consumer = int
  - id_fish = int
- Response

```json
{
  "message": "Input Success"
}
```
