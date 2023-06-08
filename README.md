# Jungle

A mini e-commerce application built with Rails 6.1. Updated to include various improvements aimed at enhancing the user experience, such as bug fixes, modifications to the user interface, and the addition of new features.

- Bug fixes:
  - Money formatting: Implemented a consistent money formatting system across the entire website.
  - Missing administrator security: Implemented a requirement for admins to provide their username and password when accessing admin-specific pages.

- UI changes:
  - Empty cart message: Instead of displaying cart details with empty data, now shows a message along with a link to the home page.
  - "Sold Out" badge: Added a badge indicating that items with no inventory are sold out.
  - Order details display: After a successful order placement, now displays the relevant details of the order.

- Features:
  - Admin dashboard: Introduced a new dashboard that provides an overview of the number of products and categories.
  - About page: Added an About page, which can be populated with information about the company.
  - Category creation: Implemented a new page for administrators to create new categories.
  - User login and registration support: Introduced new database tables and pages to support user login and registration. Passwords are now properly hashed using bcrypt, emails must be unique (case-insensitive), and error messages are displayed on the login/signup pages.

- Tests:
  - RSpec tests: Implemented tests using RSpec for product and user models.
  - Cypress tests: Introduced Cypress tests for the home page, product details, add to cart functionality, and user login/signup process.

## Setup

1. Run `bundle install` to install dependencies
2. Create `config/database.yml` by copying `config/database.example.yml`
3. Create `config/secrets.yml` by copying `config/secrets.example.yml`
4. Run `bin/rails db:reset` to create, load and seed db
5. Create .env file based on .env.example
6. Sign up for a Stripe account
7. Put Stripe (test) keys into appropriate .env vars
8. Run `bin/rails s -b 0.0.0.0` to start the server

## Database

If Rails is complaining about authentication to the database, uncomment the user and password fields from `config/database.yml` in the development and test sections, and replace if necessary the user and password `development` to an existing database user.

## Stripe Testing

Use Credit Card # 4111 1111 1111 1111 for testing success scenarios.

More information in their docs: <https://stripe.com/docs/testing#cards>

## Dependencies

- Rails 6.1 [Rails Guide](http://guides.rubyonrails.org/v6.1/)
- Bootstrap 5
- PostgreSQL 9.x
- Stripe
