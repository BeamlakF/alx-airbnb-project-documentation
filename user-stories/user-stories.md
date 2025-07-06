## User Story: User Registration

**As a** new user,  
I want to sign up as a guest or host using my email or third-party services (Google, Facebook),  So that I can access the platform securely and choose my role.

### Acceptance Criteria
- User can choose to register as a guest or a host
- Email and password registration is supported
- OAuth registration is available (Google, Facebook)
- JWT is used for secure authentication
- Registration returns a success message or error if failed

## Create and Manage Property Listings

As **a **host**,  
**I want to** create, update, or delete listings with detailed information (e.g., location, price, amenities), So that I can manage my rental properties on the platform.

## Acceptance Criteria
- Host can create a listing with title, description, location, price, availability, and amenities
- Host can update details of an existing listing
- Host can delete their listings
- Listings are saved in the database and retrievable by other users

## Admin Monitoring
As **an **admin**,
I want to monitor and manage users, listings, bookings, and payments through a dashboard,
So that I can ensure smooth operation of the platform.

## Handle Payments Securely
As **a **guest**,
I want to make secure payments using methods like Stripe or PayPal and see charges in my currency,
So that I can confidently complete bookings.

## Cancel a Booking
As **a guest **or **host**,
I want to cancel bookings according to a defined cancellation policy,
So that I can manage changes to my travel or hosting plans.