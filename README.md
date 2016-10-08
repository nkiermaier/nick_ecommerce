## This is an general E-Commerce API for developers

### Goal
* Managing a Stripe and Mongo store requires managing several asynchronous calls and state.
* Without this libary to  create a customer involves:
  1. Creating a customer in Stripe
  2. Creating a customer in Mongo
  3. Setting the associated Stripe id in the Mongo model
  4. Handling errors and rollback in case any one of the chain of asynchronous calls fails

* With this library you just call: ` create_customer("user@here.com", callback) `
* The Stripe account will be created, an entry in Mongo is created, and the associated Stripe Id is populated in the  mongo model. Also any failures will stop execution and rollback idempotently.

### Requirements:
* A Stripe account and secret key
* A running Mongo database

### To use
* In index.js you just put your Stripe account and Secret Key information where it's indicated.
* Thats it, it should work!(?)
* oh also, `npm install`

### Key points
* The username is used to uniquely identify a user. It has enforced uniqueness in the database.It's a parameter in most of the function calls to identify the user to perform the operation on. Not bad idea to make this a user's email.

* (Please note: These docs are minimal because I'm not expecting anyone but myself to use this.
If you want better docs please let me know: `NickKiermaier@gmail.com` .  I can also answer any questions or help troubleshoot. Also, if you see any issues that can improve on please let me know or if you want to contribute, I would love help on this.  There doesn't appear to be many/any open source e-commerce APIs for node. There's a lot of SDK's and full apps for ecommerce.)




