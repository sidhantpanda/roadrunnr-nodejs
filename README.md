# Logistic Services
A NodeJS implementation for RoadRunnr delivery service

Copy roadrunnr.js into your repo

## Step 1
```javascript
var RoadRunnr = require('roadrunnr.js');
var Runnr = new RoadRunnr.Runnr();
```

## Step 2
```javascript
// Add pickup details
Runnr.OrderRequest.pickup.user.name                       = pickupName;
Runnr.OrderRequest.pickup.user.phone_no                   = pickupNumber;
Runnr.OrderRequest.pickup.user.email                      = pickupEmail;
Runnr.OrderRequest.pickup.user.type                       = 'merchant';
Runnr.OrderRequest.pickup.user.external_id                = 'FromID';
Runnr.OrderRequest.pickup.user.full_address.address       = pickupAddress;
Runnr.OrderRequest.pickup.user.full_address.city.name     = pickupCity;
Runnr.OrderRequest.pickup.user.full_address.geo.latitude  = pickupGeo.lat;
Runnr.OrderRequest.pickup.user.full_address.geo.longitude = pickupGeo.lng;

// Add drop details
Runnr.OrderRequest.drop.user.name                       = dropName;
Runnr.OrderRequest.drop.user.phone_no                   = dropNumber;
Runnr.OrderRequest.drop.user.email                      = dropEmail;
Runnr.OrderRequest.drop.user.type                       = 'customer';
Runnr.OrderRequest.drop.user.external_id                = 'ToID';
Runnr.OrderRequest.drop.user.full_address.address       = dropAddress;
Runnr.OrderRequest.drop.user.full_address.city.name     = dropCity;
Runnr.OrderRequest.drop.user.full_address.geo.latitude  = dropGeo.lat;
Runnr.OrderRequest.drop.user.full_address.geo.longitude = dropGeo.lng;

// Order Details
Runnr.OrderRequest.order_details.order_id                 = Order_ID;
Runnr.OrderRequest.order_details.order_value              = Order_Value;
Runnr.OrderRequest.order_details.amount_to_be_collected   = Amount_To_Be_Collected;
Runnr.OrderRequest.order_details.order_type.name          = 'CashOnDelivery';
Runnr.OrderRequest.order_details.order_items[0].quantity  = quantity;
Runnr.OrderRequest.order_details.order_items[0].price     = price;
Runnr.OrderRequest.order_details.order_items[0].item.name = itemName;
Runnr.OrderRequest.order_details.created_at               = "yyyy-mm-dd hh: MM";
```

## Step 3
```javascript
Runnr.ship(function(error, response) {
  if (error) {
    // Error from RoadRunnr
    console.error(response);
  } else {
    console.log(response);
  }
});
```