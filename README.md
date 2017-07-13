# Food-delivery-service
Searching restaurants, getting menus, ordering foods and paying for an order.
## Functions
    1.Search a restaurant based on restaurant name.
    
    2.Order food by choosing menu items, quantity and adding a note about his/her restrictions.
    
    3.User can also fills in delivery address.
    
    4.The order should contain food items user ordered, quantity, price and order time.
    
    5.User should be able to pay by providing credit card number, expiration date, and security code.
    
    6.After payment is made successfully, it should return payment ID, timestamp and then the order is considered as completed so the user can see the estimated delivery time.

## Services
    The application is built on micro-service design. The application consists of three modules.
    
* Restaurant
  * User can serch restaurant, and get menu.

* Order
  * User can place order

* Payment
  * User can pay for order.
 
* Deliver
  * User can get payment ID, timestamp, and see the estimated delivery time.
 
## Databases
* Restaurant

  * Relational database

  * Three table - because they are one to many and we can query restaurant info without querying its menu

* Order

  * mongoDB

  * The reason I used mongoDB is an order can have various number of items in it.

* Payment

  * Relational database (structured, query by id)
 
 ## APIs 
 The format of POST request can be found in the test data (Restaurants.json, Orders.json, Payments.json)

* Restaurant

  * xxx.com/restaurants

    * GET: Passing name(optional), page and size (optional) as parameters and get list of restaurants

    * DELETE: Delete all restaurants

    * POST: Upload a bunch of restaurants

*foo.com/restaurants/[id]

GET get details of the restaurant

DELETE delete the restaurant

GET /restaurants/[id]/menus to get the menus of the restaurant

foo.com/menus

POST create a list of menus

GET passing page and size (optional) as parameters and get list of menus

DELETE delete all menus

foo.com/menus/[id]

GET get info of the menu

DELETE delete a menu

foo.com/menu_items

GET passing page and size (optional) as parameters and get list of menu items

POST upload a list of menu items

DELETE delete all menu items

foo.com/menu_items/[id]

GET menu items by menu id

DELETE delete a menu item

GET /menu_items/[id]/price to get the price of it

Order

foo.com/orders

POST create a list of orders

GET passing page and size (optional) as parameters and get list of orders

foo.com/orders/[id]

GET query info
foo.com/orders/[id]/is_paid

GET get if the order is paid

PUT set if it is paid

foo.com/orders/[id]/is_cancelled

GET get if the order is cancelled

PUT set if it is cancelled

Payment

foo.com/payment

GET passing page and size (optional) as parameters and get list of payments

POST create a payment

foo.com/payment/[id]

GET Return its info


 
