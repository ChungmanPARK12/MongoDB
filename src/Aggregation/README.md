Example:
```javascript
db.customers.aggregate([
   { 
	  $match: {customerID: 2}
	},		  
	{
	$lookup:
	{ 
	from: "shopping_Carts",
	localField: "customerID",
	foreignField: "customerID",
	as: "cart_items_details"
	}
    }
]).pretty()
```