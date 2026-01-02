# Lookup 1: customers - shopping_carts

This aggregation joins the `customers` related records in
`shopping_carts` using `customerId`.

```javascript
db.customers.aggregate([
  { $match: { customerId: "C001" } },
  {
    $lookup: {
      from: "shopping_carts",
      localField: "customerId",
      foreignField: "customerId",
      as: "shoppingCarts"
    }
  },
  {
    $project: {
      _id: 0,
      customerId: 1,
      firstName: 1,
      email: 1,
      "shoppingCarts.cartId": 1,
      "shoppingCarts.cartDateTime": 1,
      "shoppingCarts.deliveredOrNot": 1,
      "shoppingCarts.deliveryDate": 1,
      "shoppingCarts.ratingFromCustomer": 1,
      "shoppingCarts.cart_items": 1
    }
  }
]).pretty()

```

<table>
  <thead>
    <tr>
      <th align="center">
        Lookup result: Customer "C001" with related shopping_carts as (shoppingCarts)
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center">

`db.items.insertMany()`

<img
  src="https://github.com/user-attachments/assets/60305a31-f4ec-41f5-b8a0-6346e0913c6d"
  width="700"
  alt="Items sample insert results (5 documents)"
/>

  </tbody>
</table>

# Lookup 2: shopping_carts - items - suppliers

```javascript
db.shopping_carts.aggregate([
  { $match: { cartId: 1 } },

  // cart_items -> items details
  {
    $lookup: {
      from: "items",
      let: { itemIds: "$cart_items.itemId" },
      pipeline: [
        { $match: { $expr: { $in: ["$itemId", "$$itemIds"] } } },
        { $project: { _id: 0, itemId: 1, itemName: 1, price: 1, supplierId: 1 } }
      ],
      as: "itemDetails"
    }
  },

  // items.supplierId -> suppliers details
  {
    $lookup: {
      from: "suppliers",
      let: { supplierIds: "$itemDetails.supplierId" },
      pipeline: [
        { $match: { $expr: { $in: ["$supplierId", "$$supplierIds"] } } },
        { $project: { _id: 0, supplierId: 1, supplierName: 1, email: 1 } }
      ],
      as: "supplierDetails"
    }
  },

  // Minimised output for readability
  {
    $project: {
      _id: 0,
      cartId: 1,
      customerId: 1,
      cart_items: 1,
      itemDetails: 1,
      supplierDetails: 1
    }
  }
]).pretty()


```

<table>
  <thead>
    <tr>
      <th align="center">
      Lookup result: Shopping cart cartId = 1 with customerId, joined with related items and their corresponding suppliers
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center">

`db.items.insertMany()`

<img
  src="https://github.com/user-attachments/assets/01cc81d5-d172-4c39-a38b-0e20748cb64d"
  width="700"
  alt="Items sample insert results (5 documents)"
/>

  </tbody>
</table>