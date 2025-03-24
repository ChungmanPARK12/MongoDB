## 🧪 Sample Data Insertion

Below is the sample data used for inserting records into MongoDB collections such as `customers`, `items`, `shopping_Carts`, and `suppliers`.

```javascript
// Insert into customers collection
db.customers.insertOne({
  customerID: 1,
  firstName: 'John',
  lastName: 'Brown',
  email: 'jbrown100@yahoo.com',
  annualSpend: 100.00,
  phones: [
    {
      phoneID: 1,
      phoneNumber: '0427788128',
      phoneType: 'Personal',
      customerID: 1
    }
  ],
  customerAddresses: [
    {
      customerAddressID: 1,
      addressType: 'Business',
      street: '1st street',
      city: 'Adelaide',
      postCode: '5000',
      state: 'SA',
      country: 'Australia',
      customerID: 1
    }
  ],
  interest: [
    {
      interestID: 1,
      interestName: 'furniture',
      customerID: 1
    }
  ]
});

db.customers.insertOne({
  customerID: 2,
  firstName: 'Jack',
  lastName: 'White',
  email: 'jwhite200@yahoo.com',
  annualSpend: 200.00,
  phones: [
    {
      phoneID: 2,
      phoneNumber: '0414237921',
      phoneType: 'Personal',
      customerID: 2
    },
    {
      phoneID: 3,
      phoneNumber: '08-81091122',
      phoneType: 'Business',
      customerID: 2
    }
  ],
  customerAddresses: [
    {
      customerAddressID: 2,
      addressType: 'Personal',
      street: '2nd Street',
      city: 'Melbourne',
      postCode: '3001',
      state: 'VIC',
      country: 'Australia',
      customerID: 2
    }
  ]
});

db.customers.insertOne({
  customerID: 3,
  firstName: 'Jill',
  lastName: 'Black',
  email: 'jblack300@yahoo.com',
  annualSpend: 300.00,
  phones: [
    {
      phoneID: 4,
      phoneNumber: '08-85678888',
      phoneType: 'Business',
      customerID: 3
    }
  ],
  customerAddresses: [
    {
      customerAddressID: 5,
      addressType: 'Postal',
      street: 'Box 400 Blackwood Post Office',
      city: 'Blackwood',
      postCode: '5051'
    }
  ]
});
```

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


