
### customers Collection
```json
{
  "_id": ObjectId,
  "customerId": String,
  "firstName": String,
  "lastName": String,
  "email": String,
  "customer_addresses": [
    {
      "addressId": int,
      "addressType": String,
      "street": String,
      "city": String,
      "postCode": String,
      "state": String,
      "country": String
    }
  ],
  "phones": [
    {
      "phoneId": int,
      "phoneNumber": String,
      "phoneType": String
    }
  ],
  "interests": [
    {
      "interestId": int,
      "interestName": String
    }
  ]
}
```

---

### items Collection
```json
{
  "_id": ObjectId,
  "itemId": int,
  "itemName": String,
  "price": Decimal,
  "qtyHand": int,
  "supplierId": int
}
```

---

### suppliers Collection
```json
{
  "_id": ObjectId,
  "supplierId": int,
  "supplierName": String,
  "email": String,
  "supplier_addresses": [
    {
      "addressId": int,
      "addressType": String,
      "street": String,
      "city": String,
      "postCode": String,
      "state": String,
      "country": String
    }
  ],
  "suppliers_items": [
    {
      "itemId": int,
      "dateAvailable": Date
    }
  ]
}
```

---

### shopping_carts Collection
```json
{
  "_id": ObjectId,
  "cartId": int,
  "cartDateTime": Date,
  "deliveryInstruction": String,
  "deliveredOrNot": bool,
  "deliveryDate": Date,
  "ratingFromCustomer": int,
  "customerId": String,
  "cart_items": [
    {
      "itemId": int,
      "qtyOrdered": int
    }
  ]
}
```
---








