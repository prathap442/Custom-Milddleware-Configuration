# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

# Normally configure the Rails Application 
  * rails_5.1.1 new virtuso -d postgresql --api
  * this generates an api based application
  ```
    rails db:create && rails db:migrate && rails s
  ```
  * Now the database is configured and then in app folder section create a new folder called "middlewares"
  * Under the middlewares folder section create a new middleware class called as MyMiddleware.rb. Inside which we have two methods namely 
    ** initialize
    ** call
  * Now in the config/application.rb we need to add a line for middleware usage sake 

  ```
    Dir['./app/middlewares/*.rb'].each do |file|
      require file
    end
    config.middleware.use MyMiddleware
  ```
  * Now that the middleware is setup we need to restart the server to see the things that happen.