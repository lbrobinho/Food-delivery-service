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
    The application is built on micro-service design. The application consists of four modules.
    
* Restaurant
  * User can search restaurant, and get menu.

* Order
  * User can place order.

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
     
     * POST: Upload a bunch of restaurants

     * GET: Passing  page and size (optional) as parameters and get list of restaurants

     * DELETE: Delete all restaurants
     
   * xxx.com/restaurants/{restaurantName}

     * GET: get details of the restaurant according to the name of restaurant

     * DELETE: delete the restaurant

  * xxx.com/restaurants/{restaurantName}/menu

     * POST: Upload a menus of specifical restaurant

     * GET: Passing page and size (optional) as parameters and get a menu, response is food, price and description

     * DELETE: Delete the menu
     

* Order

   * xxx.com/orders

     * POST: create a list of orders

     * GET: passing page and size (optional) as parameters and get list of orders
     

   * xxx.com/orders/[id]
  
     * GET: get specifical order
     
     * DELETE: delete an order by orderId

   * xxx.com/orders/[id]/paid

     * GET: get if order is paid

     * PUT set order paid

   * xxx.com/orders/[id]/cancelled

     * GET: get if the order is cancelled

     * PUT: set cancelled

 * Payment

   * xxx.com/payment

     * GET: passing page and size (optional) as parameters and get list of payments

     * POST: create a payment

   * xxx.com/payment/[id]

     * GET: Return payment information
   
  Delivery
    * get: get the estimated delivery time


 
