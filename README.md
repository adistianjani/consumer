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
    "banyak": 17,
    "data": [
        {
            "id_fish": 1,
            "name": "arwana",
            "price": 5000,
            "location": "konoha",
            "photo_url": null
        },
        {
            "id_fish": 2,
            "name": "megalodon",
            "price": 10000,
            "location": "konoha",
            "photo_url": null
        },
        {
            "id_fish": 3,
            "name": "cupang",
            "price": 2000,
            "location": "konoha",
            "photo_url": null
        },
        {
            "id_fish": 4,
            "name": "megalodon",
            "price": 9000,
            "location": "barat",
            "photo_url": null
        },
        {
            "id_fish": 5,
            "name": "biawak",
            "price": 6000,
            "location": "barat",
            "photo_url": null
        },
        {
            "id_fish": 6,
            "name": "gurame",
            "price": 2000,
            "location": "jepang",
            "photo_url": null
        },
        {
            "id_fish": 48,
            "name": "bandeng",
            "price": 15000,
            "location": "jepang",
            "photo_url": null
        },
        {
            "id_fish": 49,
            "name": "bandeng",
            "price": 15000,
            "location": "barat",
            "photo_url": null
        },
        {
            "id_fish": 62,
            "name": "Pindang",
            "price": 200000,
            "location": "Surabaya",
            "photo_url": null
        },
        {
            "id_fish": 63,
            "name": "Tongkol",
            "price": 200000,
            "location": "Surabaya",
            "photo_url": null
        },
        {
            "id_fish": 68,
            "name": "ikan gabus",
            "price": 23000,
            "location": "Jl. Kasih 10",
            "photo_url": null
        },
        {
            "id_fish": 69,
            "name": "Ikan Bandeng",
            "price": 15000,
            "location": "Jl. Kasih 10",
            "photo_url": null
        },
        {
            "id_fish": 77,
            "name": "bandeng",
            "price": 20000,
            "location": "barat",
            "photo_url": "https://blabla"
        },
        {
            "id_fish": 78,
            "name": "arwanaa",
            "price": 30000,
            "location": "konoha",
            "photo_url": "https://blabla"
        },
        {
            "id_fish": 82,
            "name": "FIsher Segar",
            "price": 89,
            "location": "lombok",
            "photo_url": "05-Oct-20221212684520832617619.jpg"
        },
        {
            "id_fish": 83,
            "name": "Pemandangan Segar",
            "price": 20,
            "location": "lombok",
            "photo_url": "06-Oct-20222170633292461802552.jpg"
        },
        {
            "id_fish": 84,
            "name": "arwanaa",
            "price": 30000,
            "location": "barat",
            "photo_url": "https://blabla"
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
    "banyak": 1,
    "data": [
        {
            "id_fish": 1,
            "name": "arwana",
            "weight": 100,
            "price": 5000,
            "photo_url": null
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
            "id_fish": 1,
            "name": "arwana",
            "saller_name": "naruto",
            "location": "konoha",
            "weight": 100,
            "price": 5000,
            "photo_url": null
        }
    ]
}
```
### Check fish in cart

- Endpoint
  - /consumer/ikan/cek/:idConsumer/:idIkan
- Method
  - GET
- Request Params
  - idConsumer = int
  - idIkan = int

```json
{
    "tabel": "Cart",
    "data": [
        {
            "id": 1,
            "notes": "potong 3",
            "weight": 100,
            "id_fish": 2,
            "id_consumer": 1
        },
        {
            "id": 2,
            "notes": "potong 50",
            "weight": 100,
            "id_fish": 2,
            "id_consumer": 1
        },
        {
            "id": 5,
            "notes": "potong 3",
            "weight": 10,
            "id_fish": 2,
            "id_consumer": 1
        }
    ]
}
```

### Get cart consumer

- Endpoint
  - /consumer/keranjang/:idConsumer
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
            "id_consumer": 1,
            "photo_url": null
        },
        {
            "id_cart": 2,
            "id_fish": 2,
            "name_fish": "megalodon",
            "weight": 100,
            "price": 10000,
            "notes": "potong 50",
            "id_consumer": 1,
            "photo_url": null
        },
        {
            "id_cart": 3,
            "id_fish": 3,
            "name_fish": "cupang",
            "weight": 5,
            "price": 2000,
            "notes": "utuh",
            "id_consumer": 1,
            "photo_url": null
        },
        {
            "id_cart": 5,
            "id_fish": 2,
            "name_fish": "megalodon",
            "weight": 10,
            "price": 10000,
            "notes": "potong 3",
            "id_consumer": 1,
            "photo_url": null
        },
        {
            "id_cart": 7,
            "id_fish": 1,
            "name_fish": "arwana",
            "weight": 1,
            "price": 5000,
            "notes": "x",
            "id_consumer": 1,
            "photo_url": null
        }
    ]
}
```

### Input cart & edit cart consumer 

- Endpoint
  - /consumer/keranjang/input/edit
- Method
  - POST
- Request Body
  - id_fish = int
  - id_consumer = int
  - notes = string
  - weight = int
- Response

- jika data belum ada, maka input cart
```json
{
  "message": "Input Success"
}
```
- jika data sudah ada, maka edit cart
```json
{
  "message": "Edit Success"
}
```

### Input cart consumer 

- Endpoint
  - /consumer/keranjang/input 
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

### Get all order 

- Endpoint
  - /consumer/pesanan/all/
- Method
  - GET
- Response
```json
{
    "banyak": 7,
    "data": [
        {
            "id_ordering": 1,
            "date": "2008-11-11T05:23:44.000Z",
            "total_price": "50000",
            "status": "sending"
        },
        {
            "id_ordering": 1,
            "date": "2008-11-11T05:23:44.000Z",
            "total_price": "100000",
            "status": "sending"
        },
        {
            "id_ordering": 2,
            "date": "2123-11-11T05:23:00.000Z",
            "total_price": "50000",
            "status": "waiting"
        },
        {
            "id_ordering": 2,
            "date": "2123-11-11T05:23:00.000Z",
            "total_price": "100000",
            "status": "waiting"
        },
        {
            "id_ordering": 3,
            "date": "2008-11-10T21:23:44.000Z",
            "total_price": "20000",
            "status": "waiting"
        },
        {
            "id_ordering": 4,
            "date": "2008-11-10T21:23:44.000Z",
            "total_price": "20000",
            "status": "waiting"
        },
        {
            "id_ordering": 2,
            "date": "2123-11-11T05:23:00.000Z",
            "total_price": "90000",
            "status": "waiting"
        }
    ]
}
```

### Get all order by id consumer

- Endpoint
  - /consumer/pesanan/all/idConsumer/:idConsumer
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
            "id_ordering": 1,
            "date": "2008-11-11T05:23:44.000Z",
            "total_price": "50000",
            "status": "sending",
            "invoice_url": null
        },
        {
            "id_ordering": 1,
            "date": "2008-11-11T05:23:44.000Z",
            "total_price": "100000",
            "status": "sending",
            "invoice_url": null
        }
    ]
}
```

### Get all order by id order

- Endpoint
  - /consumer/pesanan/all/idOrder/:idOrder
- Method
  - GET
- Request Params
  - idOrder = int
- Response

```json
{
    "banyak": 1,
    "data": [
        {
            "id_ordering": 1,
            "date": "2008-11-11T05:23:44.000Z",
            "total_price": "150000",
            "status": "sending"
        }
    ]
}
```

### Get order by idorder & idconsumer

- Endpoint
  - /consumer/pesanan/:idConsumer/:idOrder
- Method
  - GET
- Request Params
  - idConsumer = int
  - idOrder = int
- Response

```json
{
    "banyak": 3,
    "data": [
        {
            "id_ordering": 2,
            "consumer_name": "zoro",
            "date": "2123-11-11T05:23:00.000Z",
            "fish_name": "arwana",
            "weight": 10,
            "fish_price": 5000,
            "status": "waiting",
            "photo_url": null,
            "invoice_url": null
        },
        {
            "id_ordering": 2,
            "consumer_name": "zoro",
            "date": "2123-11-11T05:23:00.000Z",
            "fish_name": "megalodon",
            "weight": 10,
            "fish_price": 10000,
            "status": "waiting",
            "photo_url": null,
            "invoice_url": null
        },
        {
            "id_ordering": 2,
            "consumer_name": "zoro",
            "date": "2123-11-11T05:23:00.000Z",
            "fish_name": "megalodon",
            "weight": 10,
            "fish_price": 9000,
            "status": "waiting",
            "photo_url": null,
            "invoice_url": null
        }
    ]
}
```

### Get order by id order

- Endpoint
  - /consumer/pesanan/idOrder/:idOrder
- Method
  - GET
- Request Params
  - idOrder = int
- Response

```json
{
    "banyak": 2,
    "data": [
        {
            "id_ordering": 1,
            "consumer_name": "tsubasa",
            "date": "2008-11-11T05:23:44.000Z",
            "fish_name": "arwana",
            "weight": 10,
            "fish_price": 5000,
            "status": "sending",
            "photo_url": null
        },
        {
            "id_ordering": 1,
            "consumer_name": "tsubasa",
            "date": "2008-11-11T05:23:44.000Z",
            "fish_name": "megalodon",
            "weight": 10,
            "fish_price": 10000,
            "status": "sending",
            "photo_url": null
        }
    ]
}
```

### Get order by id consumer

- Endpoint
  - /consumer/pesanan/idConsumer/:idConsumer
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
            "id_ordering": 2,
            "consumer_name": "zoro",
            "date": "2123-11-11T05:23:00.000Z",
            "fish_name": "arwana",
            "weight": 10,
            "fish_price": 5000,
            "status": "waiting",
            "photo_url": null
        },
        {
            "id_ordering": 2,
            "consumer_name": "zoro",
            "date": "2123-11-11T05:23:00.000Z",
            "fish_name": "megalodon",
            "weight": 10,
            "fish_price": 10000,
            "status": "waiting",
            "photo_url": null
        },
        {
            "id_ordering": 3,
            "consumer_name": "zoro",
            "date": "2008-11-10T21:23:44.000Z",
            "fish_name": "cupang",
            "weight": 10,
            "fish_price": 2000,
            "status": "waiting",
            "photo_url": null
        },
        {
            "id_ordering": 4,
            "consumer_name": "zoro",
            "date": "2008-11-10T21:23:44.000Z",
            "fish_name": "cupang",
            "weight": 10,
            "fish_price": 2000,
            "status": "waiting",
            "photo_url": null
        },
        {
            "id_ordering": 2,
            "consumer_name": "zoro",
            "date": "2123-11-11T05:23:00.000Z",
            "fish_name": "megalodon",
            "weight": 10,
            "fish_price": 9000,
            "status": "waiting",
            "photo_url": null
        }
    ]
}
```

### Input order consumer

- Endpoint
  - /consumer/pesanan/input
- Method
  - POST
- Request Body
  - date = format(YYYY-MM-DD hh:mm:ss)
  - notes = string
  - status = string
  - kurir = string
  - alamat = string
  - invoice_url = string

- Response

```json
{
    "message": "input success",
    "id_ordering": 85
}
```

### Input detail order consumer

- Endpoint
  - /consumer/pesanan/input/detail/:id_consumer
- Method
  - POST

- Request Body
  - data = array (id_cart)
  - id_ordering = int
```json
{
    "data": [182, 207],
    "id_ordering": "114"
}
``` 

- Response

```json
{
    "message": "Input data Success"
}
```

### Create invoice

- Endpoint
  - /payment/create/invoice
- Method
  - POST
- Request Body
  - externalID: string;
  - payerEmail: string;
  - description: string;
  - amount: number;
- Response

```json
{
    "message": "Input Success",
    "data": {
        "id": "63648877798a2f8b86c29f6d",
        "external_id": "4",
        "user_id": "633cfec05aa61c3d545bfd58",
        "status": "PENDING",
        "merchant_name": "Fishku Indonesia",
        "merchant_profile_picture_url": "https://xnd-merchant-logos.s3.amazonaws.com/business/production/633cfec05aa61c3d545bfd58-1664944416727.jpeg",
        "amount": 25000,
        "description": "test",
        "expiry_date": "2022-11-05T03:35:19.163Z",
        "invoice_url": "https://checkout-staging.xendit.co/web/63648877798a2f8b86c29f6d",
        "available_banks": [
            {
                "bank_code": "MANDIRI",
                "collection_type": "POOL",
                "transfer_amount": 25000,
                "bank_branch": "Virtual Account",
                "account_holder_name": "FISHKU INDONESIA",
                "identity_amount": 0
            },
            {
                "bank_code": "BRI",
                "collection_type": "POOL",
                "transfer_amount": 25000,
                "bank_branch": "Virtual Account",
                "account_holder_name": "FISHKU INDONESIA",
                "identity_amount": 0
            },
            {
                "bank_code": "BNI",
                "collection_type": "POOL",
                "transfer_amount": 25000,
                "bank_branch": "Virtual Account",
                "account_holder_name": "FISHKU INDONESIA",
                "identity_amount": 0
            },
            {
                "bank_code": "PERMATA",
                "collection_type": "POOL",
                "transfer_amount": 25000,
                "bank_branch": "Virtual Account",
                "account_holder_name": "FISHKU INDONESIA",
                "identity_amount": 0
            },
            {
                "bank_code": "BCA",
                "collection_type": "POOL",
                "transfer_amount": 25000,
                "bank_branch": "Virtual Account",
                "account_holder_name": "FISHKU INDONESIA",
                "identity_amount": 0
            }
        ],
        "available_retail_outlets": [
            {
                "retail_outlet_name": "ALFAMART"
            },
            {
                "retail_outlet_name": "INDOMARET"
            }
        ],
        "available_ewallets": [
            {
                "ewallet_type": "OVO"
            },
            {
                "ewallet_type": "DANA"
            },
            {
                "ewallet_type": "SHOPEEPAY"
            },
            {
                "ewallet_type": "LINKAJA"
            },
            {
                "ewallet_type": "ASTRAPAY"
            }
        ],
        "available_direct_debits": [
            {
                "direct_debit_type": "DD_BRI"
            }
        ],
        "available_paylaters": [],
        "should_exclude_credit_card": false,
        "should_send_email": false,
        "created": "2022-11-04T03:35:19.696Z",
        "updated": "2022-11-04T03:35:19.696Z",
        "currency": "IDR",
        "customer_notification_preference": {
            "invoice_created": [],
            "invoice_reminder": [],
            "invoice_expired": [],
            "invoice_paid": [
                "email"
            ]
        }
    },
    "invoice_url": "https://checkout-staging.xendit.co/web/63648877798a2f8b86c29f6d"
}
```

### Get invoice url by invoice ID

- Endpoint
  - /consumer/payment/invoice/:invoiceID
- Method
  - GET
- Request Params
  - invoiceID = string
- Response

```json
{
    "data": "https://checkout-staging.xendit.co/web/6363bafcb1d95a57566acfa6"
}
```

## Machine Learning Detection

### Ikan Kembung
- Endpoint
  - /predict?ikan=kembung
- Method
  - POST
- Request Body
  - file = files
- Response

```json
{
    "prediction": "Tidak Segar"
}
```

### Ikan Tongkol
- Endpoint
  - /predict?ikan=tongkol
- Method
  - POST
- Request Body
  - file = files
- Response

```json
{
    "prediction": "Segar"
}
```

### Ikan Bandeng
- Endpoint
  - /predict?ikan=bandeng
- Method
  - POST
- Request Body
  - file = files
- Response

```json
{
    "prediction": "Tidak Segar"
}
```

----

Base URL:

<p >
  <a href="https://apis.fishku.id">apis.fishku.id</a>
</p>

### Get data ikan
- Endpoint
  - /consumer/detect/fish/
- Method
  - GET
- Response

```json
{
    "banyak": 3,
    "data": [{
            "id": 1,
            "name": "kembung",
            "photo": null
        },
        {
            "id": 2,
            "name": "tongkol",
            "photo": null
        },
        {
            "id": 3,
            "name": "bandeng",
            "photo": null
        }
    ]
}
```
## Storage

### Show photo
- Endpoint
  - /photo/:name
- Method
  - GET
- Request Params
  - name = string
- Response
  - photo
