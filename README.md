# NE6 Coding Exercise

## Introduction

Your task is to create a basic checkout system for an online shop. The system will allow an admin to add products to the system, and allow a customer to add products to their basket and "checkout" with their order. You do **not** need to handle any payment methods for the purpose of this exercise.

The system should be a REST API built in Laravel and it should be possible to complete the given scenario by **only** hitting endpoints within the Laravel app unless explicitly mentioned in the following scenario section.

## The Scenario

The scenario to achieve is as follows:

### Admin

1. Add an admin user to the database. This doesn't need to be (and shouldn't be) done through an endpoint, this can be done directly through a Factory or by using a custom Artisan command.
2. Log the admin in to the system. It is recommended to use [Sanctum](https://laravel.com/docs/8.x/sanctum) for authentication, and using API Tokens will be sufficient for this exercise.
3. The admin adds the following products to the database:
   * Bag of Tynemouth Coffee 
      * SKU: 000102 
      * Price: £8.50
   * 200g of Northumberland Cheese
      * SKU: 000101
      * Price: £4.30
   * Block of Acomb Farm Butter
      * SKU: X00419
      * Price: £2.00

### Customer
1. The customer registers on the system. The following details should be stored in the database when registering:
   * Name
   * Email Address
   * Password
   * Address
2. The customer receives an email with a link to confirm their account. The customer should not be able to log in to their account before they click this link.
3. After confirming their email address, the customer logs in to their account.
4. The customer adds the following products to their basket:
   * 4 Bags of Tynemouth Coffee
   * 200g of Northumberland Cheese
   * 3 Blocks of Acomb Farm Butter
5. The customer receives a total price for their order after discounts. The following discounts are applied:
   * 20% off all bags of Tynemouth Coffee when more than 2 bags are ordered
   * 2 for 1 on Blocks of Acomb Farm Butter
6. The customer checks out their order. The following will happen at this stage:
   * An order is created in the database that stores the products ordered, the quantities of each product, the order total, the customer and the customer's address
   * A confirmation email is sent to the customer with the details of their order
   * A confirmation email is sent to the admin with the details of the order
   * The customer's basket is cleared

***

A customer can view their orders when logged into their account and an admin can view all orders when logged in to their account.

It is preferred (but not necessary) to create a test that will execute this scenario. Alternatively, you can create a text file that details how to execute this scenario using your endpoints.