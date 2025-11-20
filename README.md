# PawFam 🐾 - Pet Care Platform

## Table of Contents
1. [Project Overview](#project-overview)
2. [Features](#features)
3. [Tech Stack](#tech-stack)
4. [Project Structure](#project-structure)
5. [Modules & Components](#modules--components)
6. [MongoDB Queries](#mongodb-queries)
7. [API Endpoints](#api-endpoints)
8. [Installation & Setup](#installation--setup)
9. [Use Cases](#use-cases)
10. [References](#references)
11. [Conclusion](#conclusion)

---

## Project Overview

**PawFam** is a comprehensive pet care platform that bridges the gap between pet owners and service providers. The platform offers three core services:
- **Daycare Services**: Book temporary care for pets at registered daycare centers
- **Pet Accessories**: E-commerce for pet products with cart and checkout functionality
- **Pet Adoption**: Connect with shelters and vendors for pet adoption

The platform supports two user roles:
- **Customers**: Pet owners who need services
- **Vendors**: Service providers who offer daycare, accessories, and adoption services

### Key Highlights
- Dual authentication system (Customer & Vendor)
- Real-time booking management
- Shopping cart with checkout
- Profile and pet management
- Analytics dashboards
- Search and filter capabilities
- Image upload support (Base64)

---

## Features

### Customer Features
**Authentication**
- Secure registration and login
- Password reset with OTP verification
- Profile management with personal details

**Pet Management**
- Add multiple pets with breed selection
- Track pet details (name, age, breed, category)
- Search and sort pet listings

**Daycare Services**
- Browse daycare centers
- Book daycare with date selection
- Auto-fill from registered pets
- View and manage bookings
- Edit/cancel bookings

**Accessories Shopping**
- Browse product catalog
- Search and filter products
- Shopping cart functionality
- Checkout with address validation
- Order tracking and management
- Payment method selection (Card/UPI/COD)

**Pet Adoption**
- Browse available pets
- Submit adoption applications
- Schedule shelter visits
- Track application status
- Edit/revoke applications

**Dashboard & Analytics**
- Visual analytics with charts (Recharts)
- Booking history
- Order statistics
- Spending analysis

### Vendor Features
**Vendor Dashboard**
- Overview of all requests
- Status management
- Analytics with multiple chart types
- Request filtering by type and status

**Daycare Management**
- Create/edit daycare centers
- Set pricing and capacity
- Manage operating hours
- Image uploads for centers
- Track bookings

**Adoption Management**
- List pets for adoption
- Manage pet details and health info
- Track adoption applications
- Update application status

**Accessories Management**
- Add/edit products
- Inventory management
- Order fulfillment
- Pricing and discount management

---

## Tech Stack

### Frontend
- **React.js** (v18+) - UI Framework
- **React Router** - Client-side routing
- **Context API** - State management (Cart)
- **Axios** - HTTP client
- **Recharts** - Data visualization
- **CSS3** - Styling

### Backend
- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **MongoDB** - NoSQL database
- **Mongoose** - ODM for MongoDB
- **JWT** - Authentication
- **Bcrypt** - Password hashing

### Additional Libraries
- **React Portal** - Modal rendering
- **FileReader API** - Image handling

---

## Project Structure

```
pawfam/
├── public/
├── src/
│   ├── components/
│   │   ├── Header/
│   │   │   ├── Header.js
│   │   │   └── Header.css
│   │   ├── Modal/
│   │   │   ├── Modal.js
│   │   │   └── Modal.css
│   │   └── pages/
│   │       ├── LandingPage/
│   │       ├── LoginPage/
│   │       ├── SignUpPage/
│   │       ├── VendorLoginPage/
│   │       ├── VendorSignUpPage/
│   │       ├── ForgotPasswordPage/
│   │       ├── ProfilePage/
│   │       ├── VendorProfilePage/
│   │       ├── PetServicesPage/
│   │       ├── AccessoriesPage/
│   │       ├── AdoptionPage/
│   │       ├── BookingsPage/
│   │       ├── CustomerDashboard/
│   │       ├── VendorDashboard/
│   │       ├── VendorDaycarePage/
│   │       ├── VendorAdoptionPage/
│   │       └── VendorAccessoriesPage/
│   ├── context/
│   │   └── CartContext.js
│   ├── services/
│   │   └── api.js
│   ├── App.js
│   ├── App.css
│   └── index.js
└── package.json
```

---

## Modules & Components

### 1. **Authentication Module**
**Files**: `LoginPage.js`, `SignUpPage.js`, `VendorLoginPage.js`, `VendorSignUpPage.js`, `ForgotPasswordPage.js`

**Functionality**:
- User registration with password validation
- Login with JWT token generation
- Separate vendor authentication
- Password reset with OTP
- Email validation
- Form validation with real-time feedback

**Key Features**:
- Password strength checker (8+ chars, uppercase, lowercase, number, special char)
- Prevent double submission
- Error handling with user-friendly messages
- Auto-redirect after successful auth

---

### 2. **Profile Management Module**
**Files**: `ProfilePage.js`, `VendorProfilePage.js`

**Customer Profile Functionality**:
- Personal details (name, gender, mobile, address)
- Pet management (add, edit, delete pets)
- Pet search and sorting
- Breed selection by category (Dog/Cat)
- Profile CRUD operations

**Vendor Profile Functionality**:
- Business details
- Communication address
- Mobile number validation
- Profile CRUD operations

**Key Features**:
- Mobile number validation (10 digits, starts with 6-9)
- Address validation (min 10 characters)
- Gender selection with radio buttons
- Confirmation modals for deletion

---

### 3. **Daycare Services Module**
**Files**: `PetServicesPage.js`, `VendorDaycarePage.js`

**Customer Features**:
- Browse daycare centers
- Search functionality
- View center details (pricing, capacity, services, hours)
- Two booking modes:
  - Select from registered pets
  - Manual pet entry
- Date range selection
- Special instructions field
- Email and mobile validation

**Vendor Features**:
- Create/edit daycare centers
- Upload center images (Base64)
- Set operating hours
- Define services (Day Care, Overnight, Grooming, etc.)
- Accept multiple pet types
- Capacity management
- Location details with state selection

**Key Features**:
- Image upload with preview (max 5MB)
- Auto-fill from user profile
- Form validation for all fields
- Price calculation based on days

---

### 4. **Accessories/Shopping Module**
**Files**: `AccessoriesPage.js`, `VendorAccessoriesPage.js`, `CartContext.js`

**Customer Features**:
- Product catalog with grid layout
- Search and filter
- Sort by name, price, rating
- Shopping cart with:
  - Add/remove items
  - Quantity adjustment
  - Real-time total calculation
- Checkout process:
  - Shipping address form
  - Payment method selection (Card/UPI/COD)
  - Delivery preferences
  - Order summary
- Toast notifications for cart actions

**Vendor Features**:
- Product management
- Inventory tracking
- Pricing and discounts
- Image uploads
- Category management
- Shipping settings (free shipping, delivery time)
- Featured products

**Key Features**:
- Cart persistence with Context API
- Indian address validation (6-digit ZIP)
- Payment validation (card: 14-16 digits, UPI format, CVV: 3 digits)
- Delivery date/time selection (evening 5-7 PM)
- Order extras (gift wrap, receipt)

---

### 5. **Adoption Module**
**Files**: `AdoptionPage.js`, `VendorAdoptionPage.js`

**Customer Features**:
- Browse available pets
- Search functionality
- Filter by type, size, age
- View pet details (breed, temperament, health, shelter info)
- Adoption application form:
  - Personal information
  - Pet experience
  - Visit scheduling
  - Other pets disclosure
  - Adoption reason
- Terms acceptance checkboxes

**Vendor Features**:
- List pets for adoption
- Detailed pet profiles:
  - Basic info (type, breed, age, gender, size, color)
  - Health status (vaccinated, neutered)
  - Temperament selection
  - Special needs
  - Good with (kids, dogs, cats)
- Shelter information
- Adoption fee setting
- Image uploads

**Key Features**:
- Auto-fill from user profile
- Visit time slot selection
- Phone validation (10 digits)
- Email validation
- Comprehensive pet health tracking

---

### 6. **Bookings Management Module**
**Files**: `BookingsPage.js`

**Functionality**:
- Three tabs: Daycare, Accessories, Adoption
- Search functionality for daycare bookings
- Sort options (date, amount)
- View booking details
- Edit booking information
- Cancel/revoke bookings
- Delete bookings
- Status badges with color coding
- Edit shipping address for orders

**Key Features**:
- Search with debouncing
- Real-time filtering
- Status-based actions
- Comprehensive booking details
- Modal forms for editing
- Validation for all updates

---

### 7. **Dashboard & Analytics Module**
**Files**: `CustomerDashboard.js`, `VendorDashboard.js`

**Customer Dashboard**:
- Statistics cards (total bookings, orders, applications, spending)
- Multiple chart types:
  - Activity distribution (Pie Chart)
  - Amount by daycare center (Pie Chart)
  - Bookings by center (Bar Chart)
  - Orders by vendor (Pie & Bar Charts)
  - Adoption by shelter (Bar Chart)
- Week-over-week comparisons

**Vendor Dashboard**:
- Request statistics
- Service-wise breakdown
- Status distribution charts
- Trend analysis
- Request management:
  - Filter by service type
  - Filter by status
  - Update request status
  - View detailed information
- Color-coded status badges

**Key Features**:
- Recharts integration
- Responsive chart layouts
- Real-time data updates
- Status update modals

---

### 8. **Header & Navigation**
**Files**: `Header.js`

**Functionality**:
- Logo and brand name
- Responsive mobile menu
- Role-based navigation:
  - Customer: Centers, Accessories, Adoption, Dashboard, Bookings, Profile
  - Vendor: Dashboard, Daycare, Adoption, Accessories, Profile
- Authentication dropdown
- Logout functionality

**Key Features**:
- Mobile-responsive hamburger menu
- Conditional rendering based on role
- Active state management

---

### 9. **Cart Context (State Management)**
**Files**: `CartContext.js`

**Functionality**:
- Global cart state management
- Add to cart
- Remove from cart
- Update quantity
- Calculate total
- Get item count
- Clear cart
- Toast notifications

**Key Features**:
- Context API for state sharing
- Auto-hide toast (3 seconds)
- Cart persistence during session

---

### 10. **API Service Layer**
**Files**: `api.js`

**Functionality**:
- Centralized API calls
- Axios instance configuration
- Request/response interceptors
- Token management
- Error handling
- Automatic logout on 401

**API Groups**:
- Auth API (register, login, password reset)
- Daycare API (bookings CRUD)
- Products API (orders CRUD)
- Adoption API (applications CRUD)
- Vendor APIs (daycare, adoption, accessories)
- Profile APIs (customer & vendor)
- Pets API (pet management)

---

## MongoDB Queries

### Authentication Collection (`users`)
```javascript
// User Registration
db.users.insertOne({
  username: String,
  email: String,
  password: String (hashed),
  role: String (customer/vendor),
  createdAt: Date
})

// User Login
db.users.findOne({ email: String })

// Get Current User
db.users.findById(userId)
```

### Customer Profile Collection (`customerprofiles`)
```javascript
// Create Profile
db.customerprofiles.insertOne({
  userId: ObjectId,
  name: String,
  gender: String,
  mobileNumber: String,
  residentialAddress: String,
  createdAt: Date
})

// Get Profile
db.customerprofiles.findOne({ userId: ObjectId })

// Update Profile
db.customerprofiles.updateOne(
  { userId: ObjectId },
  { $set: { name, gender, mobileNumber, residentialAddress } }
)

// Delete Profile
db.customerprofiles.deleteOne({ userId: ObjectId })
```

### Vendor Profile Collection (`vendorprofiles`)
```javascript
// Similar structure with communicationAddress instead of residentialAddress
```

### Pets Collection (`pets`)
```javascript
// Create Pet
db.pets.insertOne({
  userId: ObjectId,
  category: String,
  breed: String,
  name: String,
  age: Number,
  createdAt: Date
})

// Get User Pets
db.pets.find({ userId: ObjectId }).sort({ category: 1, age: -1 })

// Update Pet
db.pets.updateOne(
  { _id: ObjectId, userId: ObjectId },
  { $set: { category, breed, name, age } }
)

// Delete Pet
db.pets.deleteOne({ _id: ObjectId, userId: ObjectId })
```

### Daycare Bookings Collection (`daycarebookings`)
```javascript
// Create Booking
db.daycarebookings.insertOne({
  userId: ObjectId,
  daycareCenterId: ObjectId,
  daycareCenter: {
    name: String,
    location: String,
    pricePerDay: Number
  },
  petName: String,
  petType: String,
  petAge: Number,
  email: String,
  mobileNumber: String,
  startDate: Date,
  endDate: Date,
  specialInstructions: String,
  totalAmount: Number,
  status: String (pending/confirmed/completed/cancelled),
  createdAt: Date
})

// Get User Bookings with Search
db.daycarebookings.find({
  userId: ObjectId,
  $or: [
    { petName: { $regex: keyword, $options: 'i' } },
    { petType: { $regex: keyword, $options: 'i' } },
    { 'daycareCenter.name': { $regex: keyword, $options: 'i' } },
    { status: { $regex: keyword, $options: 'i' } }
  ]
}).sort({ createdAt: -1 })

// Update Booking
db.daycarebookings.updateOne(
  { _id: ObjectId, userId: ObjectId },
  { $set: { petName, petType, petAge, email, mobileNumber, startDate, endDate, specialInstructions } }
)

// Cancel Booking
db.daycarebookings.updateOne(
  { _id: ObjectId, userId: ObjectId },
  { $set: { status: 'cancelled' } }
)

// Delete Booking
db.daycarebookings.deleteOne({ _id: ObjectId, userId: ObjectId })
```

### Daycare Centers Collection (`daycarecenters`)
```javascript
// Create Center (Vendor)
db.daycarecenters.insertOne({
  vendorId: ObjectId,
  name: String,
  location: String,
  address: String,
  city: String,
  state: String,
  zipCode: String,
  phone: String,
  email: String,
  pricePerDay: Number,
  services: [String],
  petTypes: [String],
  facilities: [String],
  capacity: Number,
  description: String,
  operatingHours: {
    openTime: String,
    closeTime: String
  },
  images: [String],
  rating: Number,
  createdAt: Date
})

// Get All Centers
db.daycarecenters.find({}).sort({ createdAt: -1 })

// Get Vendor Centers
db.daycarecenters.find({ vendorId: ObjectId })

// Update Center
db.daycarecenters.updateOne(
  { _id: ObjectId, vendorId: ObjectId },
  { $set: { ...centerData } }
)

// Delete Center
db.daycarecenters.deleteOne({ _id: ObjectId, vendorId: ObjectId })
```

### Product Orders Collection (`productorders`)
```javascript
// Create Order
db.productorders.insertOne({
  userId: ObjectId,
  items: [{
    productId: String,
    name: String,
    price: Number,
    quantity: Number,
    image: String
  }],
  shippingAddress: {
    fullName: String,
    email: String,
    address: String,
    city: String,
    state: String,
    zipCode: String
  },
  deliveryPreferences: {
    date: Date,
    time: String,
    extras: {
      giftWrap: Boolean,
      includeReceipt: Boolean
    },
    priorityDelivery: Boolean
  },
  paymentInfo: {
    method: String,
    cardNumber: String (masked),
    expiryDate: String,
    cvv: String (not stored),
    upiId: String
  },
  totalAmount: Number,
  status: String (pending/processing/shipped/delivered/cancelled),
  createdAt: Date
})

// Get User Orders
db.productorders.find({ userId: ObjectId }).sort({ createdAt: -1 })

// Update Order Address
db.productorders.updateOne(
  { _id: ObjectId, userId: ObjectId },
  { $set: { shippingAddress: {...} } }
)

// Cancel Order
db.productorders.updateOne(
  { _id: ObjectId, userId: ObjectId },
  { $set: { status: 'cancelled' } }
)

// Update Order Status (Vendor)
db.productorders.updateOne(
  { _id: ObjectId },
  { $set: { status: String } }
)
```

### Products Collection (`products`)
```javascript
// Create Product (Vendor)
db.products.insertOne({
  vendorId: ObjectId,
  name: String,
  category: String,
  petType: String,
  description: String,
  price: Number,
  discountPrice: Number,
  stock: Number,
  brand: String,
  weight: String,
  tags: [String],
  shippingInfo: {
    freeShipping: Boolean,
    deliveryTime: String
  },
  isFeatured: Boolean,
  images: [String],
  rating: Number,
  createdAt: Date
})

// Get All Products
db.products.find({}).sort({ createdAt: -1 })

// Get Vendor Products
db.products.find({ vendorId: ObjectId })

// Update Product
db.products.updateOne(
  { _id: ObjectId, vendorId: ObjectId },
  { $set: { ...productData } }
)

// Delete Product
db.products.deleteOne({ _id: ObjectId, vendorId: ObjectId })
```

### Adoption Applications Collection (`adoptionapplications`)
```javascript
// Create Application
db.adoptionapplications.insertOne({
  userId: ObjectId,
  pet: {
    id: String,
    name: String,
    type: String,
    breed: String,
    age: String,
    shelter: String
  },
  personalInfo: {
    fullName: String,
    email: String,
    phone: String,
    address: String
  },
  experience: {
    level: String,
    details: String,
    otherPets: String,
    otherPetsDetails: String
  },
  visitSchedule: {
    date: Date,
    time: String
  },
  adoptionReason: String,
  status: String (pending/under_review/approved/rejected/scheduled),
  createdAt: Date
})

// Get User Applications
db.adoptionapplications.find({ userId: ObjectId }).sort({ createdAt: -1 })

// Update Application
db.adoptionapplications.updateOne(
  { _id: ObjectId, userId: ObjectId },
  { $set: { personalInfo, experience, visitSchedule, adoptionReason } }
)

// Revoke Application
db.adoptionapplications.updateOne(
  { _id: ObjectId, userId: ObjectId },
  { $set: { status: 'cancelled' } }
)

// Update Application Status (Vendor)
db.adoptionapplications.updateOne(
  { _id: ObjectId },
  { $set: { status: String } }
)
```

### Adoption Pets Collection (`adoptionpets`)
```javascript
// Create Pet Listing (Vendor)
db.adoptionpets.insertOne({
  vendorId: ObjectId,
  name: String,
  type: String,
  breed: String,
  age: String,
  gender: String,
  size: String,
  color: String,
  description: String,
  temperament: [String],
  healthStatus: {
    vaccinated: Boolean,
    neutered: Boolean,
    healthConditions: String
  },
  shelter: {
    name: String,
    location: String,
    address: String,
    phone: String,
    email: String
  },
  adoptionFee: Number,
  specialNeeds: String,
  goodWith: {
    kids: Boolean,
    dogs: Boolean,
    cats: Boolean
  },
  images: [String],
  status: String (Available/Adopted),
  createdAt: Date
})

// Get All Available Pets
db.adoptionpets.find({ status: 'Available' })

// Get Vendor Pets
db.adoptionpets.find({ vendorId: ObjectId })

// Update Pet
db.adoptionpets.updateOne(
  { _id: ObjectId, vendorId: ObjectId },
  { $set: { ...petData } }
)

// Delete Pet
db.adoptionpets.deleteOne({ _id: ObjectId, vendorId: ObjectId })
```

### Dashboard Analytics Queries

**Customer Dashboard**:
```javascript
// Get all bookings for analytics
db.daycarebookings.aggregate([
  { $match: { userId: ObjectId } },
  { $group: {
    _id: '$daycareCenter.name',
    count: { $sum: 1 },
    totalAmount: { $sum: '$totalAmount' }
  }}
])

// Get orders grouped by vendor
db.productorders.aggregate([
  { $match: { userId: ObjectId } },
  { $unwind: '$items' },
  { $group: {
    _id: '$items.vendor.name',
    count: { $sum: 1 },
    totalAmount: { $sum: { $multiply: ['$items.price', '$items.quantity'] } }
  }}
])

// Get weekly statistics
db.daycarebookings.aggregate([
  { $match: {
    userId: ObjectId,
    createdAt: { $gte: oneWeekAgo }
  }},
  { $count: 'weeklyCount' }
])
```

**Vendor Dashboard**:
```javascript
// Get all daycare bookings for vendor's centers
db.daycarebookings.aggregate([
  {
    $lookup: {
      from: 'daycarecenters',
      localField: 'daycareCenterId',
      foreignField: '_id',
      as: 'center'
    }
  },
  { $match: { 'center.vendorId': ObjectId } }
])

// Get orders for vendor's products
db.productorders.aggregate([
  { $unwind: '$items' },
  {
    $lookup: {
      from: 'products',
      localField: 'items.productId',
      foreignField: '_id',
      as: 'product'
    }
  },
  { $match: { 'product.vendorId': ObjectId } }
])

// Get adoption applications for vendor's pets
db.adoptionapplications.aggregate([
  {
    $lookup: {
      from: 'adoptionpets',
      localField: 'pet.id',
      foreignField: '_id',
      as: 'petDetails'
    }
  },
  { $match: { 'petDetails.vendorId': ObjectId } }
])

// Status distribution
db.daycarebookings.aggregate([
  {
    $lookup: {
      from: 'daycarecenters',
      localField: 'daycareCenterId',
      foreignField: '_id',
      as: 'center'
    }
  },
  { $match: { 'center.vendorId': ObjectId } },
  { $group: {
    _id: '$status',
    count: { $sum: 1 }
  }}
])
```

---

## API Endpoints

### Authentication
- `POST /api/auth/register` - Customer registration
- `POST /api/auth/login` - Customer login
- `POST /api/auth/vendor/register` - Vendor registration
- `POST /api/auth/vendor/login` - Vendor login
- `POST /api/auth/send-reset-otp` - Send password reset OTP
- `POST /api/auth/verify-reset-otp` - Verify OTP
- `POST /api/auth/reset-password` - Reset password
- `GET /api/auth/me` - Get current user

### Profile Management
- `GET /api/profile` - Get customer profile
- `POST /api/profile` - Create customer profile
- `PUT /api/profile` - Update customer profile
- `DELETE /api/profile` - Delete customer profile
- `GET /api/vendor-profile` - Get vendor profile
- `POST /api/vendor-profile` - Create vendor profile
- `PUT /api/vendor-profile` - Update vendor profile
- `DELETE /api/vendor-profile` - Delete vendor profile

### Pet Management
- `GET /api/pets` - Get user's pets
- `POST /api/pets` - Create pet
- `PUT /api/pets/:id` - Update pet
- `DELETE /api/pets/:id` - Delete pet
- `GET /api/pets/breeds/:category` - Get breeds by category

### Daycare Services
- `GET /api/vendor/daycare/centers` - Get all centers
- `GET /api/vendor/daycare/my-centers` - Get vendor's centers
- `POST /api/vendor/daycare/centers` - Create center
- `PUT /api/vendor/daycare/centers/:id` - Update center
- `DELETE /api/vendor/daycare/centers/:id` - Delete center
- `GET /api/daycare/bookings` - Get customer bookings
- `POST /api/daycare/bookings` - Create booking
- `PUT /api/daycare/bookings/:id` - Update booking
- `PATCH /api/daycare/bookings/:id/cancel` - Cancel booking
- `DELETE /api/daycare/bookings/:id` - Delete booking
- `PATCH /api/daycare/bookings/:id/status` - Update booking status

### Accessories/Products
- `GET /api/vendor/accessories/products` - Get all products
- `GET /api/vendor/accessories/my-products` - Get vendor's products
- `POST /api/vendor/accessories/products` - Create product
- `PUT /api/vendor/accessories/products/:id` - Update product
- `DELETE /api/vendor/accessories/products/:id` - Delete product
- `GET /api/products/orders` - Get customer orders
- `POST /api/products/orders` - Create order
- `PUT /api/products/orders/:id/address` - Update order address
- `PATCH /api/products/orders/:id/cancel` - Cancel order
- `DELETE /api/products/orders/:id` - Delete order
- `GET /api/vendor/accessories/orders` - Get vendor's orders
- `PATCH /api/products/orders/:id/status` - Update order status

### Adoption
- `GET /api/vendor/adoption/pets` - Get all adoption pets
- `GET /api/vendor/adoption/my-pets` - Get vendor's pets
- `POST /api/vendor/adoption/pets` - Create pet listing
- `PUT /api/vendor/adoption/pets/:id` - Update pet
- `DELETE /api/vendor/adoption/pets/:id` - Delete pet
- `GET /api/adoption/applications` - Get customer applications
- `POST /api/adoption/applications` - Create application
- `PUT /api/adoption/applications/:id` - Update application
- `PATCH /api/adoption/applications/:id/revoke` - Revoke application
- `DELETE /api/adoption/applications/:id` - Delete application
- `GET /api/vendor/adoption/applications` - Get vendor's applications
- `PATCH /api/adoption/applications/:id/status` - Update application status

---

## Installation & Setup

### Prerequisites
- Node.js (v14+)
- MongoDB (v4.4+)
- npm or yarn

### Frontend Setup
```bash
# Clone the repository
git clone <repository-url>
cd pawfam

# Install dependencies
npm install

# Start development server
npm start

# Build for production
npm run build
```
