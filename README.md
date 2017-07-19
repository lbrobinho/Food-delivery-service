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

  * food.com/restaurants

     * GET: Passing name(optional), page and size (optional) as parameters and get list of restaurants

     * DELETE: Delete all restaurants

     * POST: Upload a bunch of restaurants

  * food.com/restaurants/[id]

     * GET: Get details of the restaurant

     * DELETE: Delete the restaurant

  * food.com/restaurants/[id]/menu

     * POST: Upload a menus with items

     * GET: Passing page and size (optional) as parameters and get a menu

     * DELETE: Delete the menu

  * food.com/restaurants/[id]/menu/[itemId]

     * GET: menu items by item id

     * DELETE: delete a menu item
   
   * food.com/restaurants/[id]/menu/[itemId]/price

     * GET: Get the price of item
     
     * Post: upload price

* Order

   * food.com/orders

     * POST: create a list of orders

     * GET: passing page and size (optional) as parameters and get list of orders
     

   * food.com/orders/[id]?[orderId]
  
     * GET: get specifical order
     
     * DELETE: delete an order by orderId

   * food.com/orders/[id]/paid

    * GET get if the order is paid

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


 
