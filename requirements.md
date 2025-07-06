# 🏡 Airbnb Clone: Functional & Technical Requirements

## 1. User Management

### ✅ Functional Requirements
- Users can register as **Guest** or **Host**
- Users can log in via **email/password** or **OAuth (Google, Facebook)**
- Users can update their profile info (name, photo, contact, preferences)

### ⚙️ Technical Requirements
- Use **JWT (JSON Web Tokens)** for authentication
- Store hashed passwords using **bcrypt**
- OAuth handled via **OAuth 2.0 / Passport.js**
- Users stored in **Users DB** with roles (Guest, Host)
- Validate input using server-side libraries (e.g., Joi, Zod)

---

## 2. Property Listings Management

### ✅ Functional Requirements
- Hosts can create listings with title, description, location, price, availability, and amenities
- Hosts can edit and delete their own listings
- Listings are viewable by Guests

### ⚙️ Technical Requirements
- Store listings in **Listings DB** with references to Host ID
- Use CRUD APIs: `POST /listings`, `PUT /listings/:id`, `DELETE /listings/:id`, `GET /listings`
- Implement authorization: only the listing owner (host) can edit/delete
- Use geolocation fields for map-based searches

---

## 3. Search and Filtering

### ✅ Functional Requirements
- Guests can search for listings by location, price, number of guests, and amenities
- Results should be paginated for performance

### ⚙️ Technical Requirements
- Backend search using dynamic query filtering (`/search?location=...&priceMin=...`)
- Index database fields like location and price for efficient querying
- Use **pagination** with limit/offset or cursor-based technique
- Optionally integrate **full-text search** or **ElasticSearch**

---

## 4. Booking Management

### ✅ Functional Requirements
- Guests can book properties for specific dates
- Prevent double bookings (overlapping dates)
- Hosts/Guests can cancel bookings based on policy
- Booking statuses: pending, confirmed, canceled, completed

### ⚙️ Technical Requirements
- Store bookings in **Bookings DB** with user and listing references
- Implement date validation before booking (availability check)
- Use transactions to ensure atomic booking creation
- Include booking status field with enum values

---

## 5. Payment Integration

### ✅ Functional Requirements
- Guests pay at the time of booking
- Hosts receive automatic payouts after booking completion
- System supports multiple currencies

### ⚙️ Technical Requirements
- Integrate **Stripe or PayPal** SDKs
- Securely handle card/tokenization (PCI compliant)
- Convert amounts using exchange rate APIs if needed
- Store payment records in **Payments DB** with status tracking

---

## 6. Reviews and Ratings

### ✅ Functional Requirements
- Guests can leave reviews/ratings after stay
- Hosts can respond to reviews
- Only users with completed bookings can leave reviews

### ⚙️ Technical Requirements
- Reviews linked to **Booking ID** and **Listing ID**
- Implement constraints to ensure 1 review per booking
- Use moderation tools (admin flagging, profanity filter)

---

## 7. Notifications System

### ✅ Functional Requirements
- Users receive email or in-app notifications for:
  - Booking confirmations
  - Cancellations
  - Payment status

### ⚙️ Technical Requirements
- Use **NodeMailer**, **SendGrid**, or similar for emails
- Use **WebSockets** or **Push Notifications** for real-time in-app alerts
- Store notifications in a **Notifications DB**

---

## 8. Admin Dashboard

### ✅ Functional Requirements
- Admin can view and manage:
  - All users (block, delete)
  - Listings (flag, remove)
  - Bookings (view details)
  - Payments (view history/status)

### ⚙️ Technical Requirements
- Build protected routes (`/admin/*`) with admin-only access
- Use **RBAC (Role-Based Access Control)**
- Dashboard UI built with a frontend framework (e.g., React + Tailwind)
- Backend queries aggregate data for statistics and overview

