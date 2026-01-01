## Sample Data Insertion

Below is sample data inserted into MongoDB collections such as, 
**customers**, **items**, **shopping_carts**, and **suppliers**.

```javascript
// Insert into customers collection
db.customers.insertMany()
```
### Customers - Sample insert results(4 documents)

<img width="600" height="600" alt="Image" src="https://github.com/user-attachments/assets/6fa12b03-3633-48e1-9e4e-e9d316c439af" />

--- 

<img width="600" height="600" alt="Image" src="https://github.com/user-attachments/assets/e9f1b30a-a946-4cfd-84d4-12e03f35ded7" />

```javascript
// Insert into items collection
db.items.insertMany([
  {
    itemID: 1,
    itemName: 'Slow release fertiliser 20kg',
    price: 40.00,
    qtyOnHand: 10,
    supplierID: 1
  },
  {
    itemID: 2,
    itemName: 'Organic fertiliser 20kg',
    price: 50.00,
    qtyOnHand: 20,
    supplierID: 1
  },
  {
    itemID: 3,
    itemName: 'METHOD wall cabinet',
    price: 400.00,
    qtyOnHand: 30,
    supplierID: 2
  },
  {
    itemID: 4,
    itemName: 'Applaro outdoor sofa set',
    price: 1500.00,
    qtyOnHand: 40,
    supplierID: 2
  }
]);
```

```javascript
// Insert into shopping_Carts collection
db.shopping_Carts.insertOne({
  cartID: 1,
  cartDateTime: '2022-02-20 12:00:00',
  deliveryInstruction: 'Deliver to business address',
  deliveredOrNot: '1',
  deliveryDate: '2022-02-22',
  ratingFromCustomer: '5',
  customerID: 1,
  cart_item: [
    {
      cartID: 1,
      itemID: 1,
      qtyOrdered: 2
    },
    {
      cartID: 1,
      itemID: 2,
      qtyOrdered: 3
    }
  ]
});

db.shopping_Carts.insertOne({
  cartID: 2,
  cartDateTime: '2022-02-20 14:30:00',
  deliveryInstruction: 'Deliver to personal address',
  deliveredOrNot: '1',
  deliveryDate: '2022-02-23',
  ratingFromCustomer: '4',
  customerID: 2,
  cart_item: [
    {
      cartID: 2,
      itemID: 3,
      qtyOrdered: 1
    },
    {
      cartID: 2,
      itemID: 4,
      qtyOrdered: 1
    },
    {
      cartID: 2,
      itemID: 1,
      qtyOrdered: 3
    }
  ]
});

db.shopping_Carts.insertOne({
  cartID: 3,
  cartDateTime: ISODate('2022-02-22 16:00:00'),
  deliveryInstruction: null,
  deliveredOrNot: '0',
  deliveryDate: null,
  ratingFromCustomer: null,
  customerID: 2,
  cart_item: [
    {
      cartID: 3,
      itemID: 1,
      qtyOrdered: 4
    }
  ]
});

db.shopping_Carts.insertOne({
  cartID: 4,
  cartDateTime: ISODate('2022-02-23 09:30:00'),
  deliveryInstruction: 'Deliver to delivery address',
  deliveredOrNot: '0',
  deliveryDate: null,
  ratingFromCustomer: null,
  customerID: 3,
  cart_item: [
    {
      cartID: 4,
      itemID: 2,
      qtyOrdered: 2
    }
  ]
});
```

```javascript
// Insert into suppliers collection
db.suppliers.insertOne({
  supplierID: 1,
  supplierName: 'Garden Grower',
  email: 'business@gardensupplier.com.au',
  contactPhoneNo: '08-27732420',
  supplier_addresses: [
    {
      supplierAddressID: 1,
      addressType: 'Business',
      street: '1 King Street',
      city: 'Adelaide',
      postalCode: '5000',
      state: 'SA',
      country: 'Australia',
      supplierID: 1
    },
    {
      supplierAddressID: 2,
      addressType: 'Postal',
      street: 'Box 100 Grote Street Mail Center',
      city: 'Adelaide',
      postalCode: '5000',
      state: 'SA',
      country: 'Australia',
      supplierID: 1
    }
  ],
  items_supplied: [
    {
      itemID: 1,
      itemName: 'Slow release fertilliser 20kg',
      price: '40.00'
    },
    {
      itemID: 2,
      itemName: 'Organic fertilliser 20kg',
      price: '50.00'
    }
  ]
});

db.suppliers.insertOne({
  supplierID: 2,
  supplierName: 'Home Improvement',
  email: 'office@homeimprovement.com.au',
  contactPhoneNo: '08-82544665',
  supplier_addresses: [
    {
      supplierAddressID: 3,
      addressType: 'Business',
      street: '2 Queen Street',
      city: 'Melbourne',
      postalCode: '3000',
      state: 'VIC',
      country: 'Australia',
      supplierID: 2
    },
    {
      supplierAddressID: 4,
      addressType: 'Postal',
      street: 'Box 200 Bourke Street Post Office',
      city: 'Melbourne',
      postalCode: '3000',
      state: 'VIC',
      country: 'Australia',
      supplierID: 2
    }
  ],
  items_supplied: [
    {
      itemID: 3,
      itemName: 'METHOD wall cabinet',
      price: '400.00'
    },
    {
      itemID: 4,
      itemName: 'Applaro outdoor sofa set', 
      price: '1500.00'
    }
  ]
});
```

---


