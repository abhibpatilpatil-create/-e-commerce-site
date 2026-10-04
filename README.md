# AURELIA --- Luxury E-Commerce Suite

AURELIA is a responsive luxury e-commerce storefront designed around a
premium fashion and lifestyle shopping experience. The project presents
luxury timepieces, jewelry, leather goods, and fragrances with a dark
black-and-gold visual theme.

The current implementation is a **frontend-only single-page web
application** contained in one HTML file. It uses JavaScript for
routing, product rendering, authentication simulation, shopping-cart
management, checkout flow, search, and order history.

## ✨ Features

-   Premium luxury-themed responsive UI
-   Sticky navigation header
-   Mobile navigation drawer
-   Home page with:
    -   Hero section
    -   Featured masterworks
    -   Brand/service pillars
    -   Fragrance editorial section
-   Product catalog
-   Product categories:
    -   Timepieces
    -   Jewelry
    -   Leather
    -   Fragrance
-   Category filtering
-   Product detail pages
-   Product image gallery
-   Product specifications and descriptions
-   Product ratings and review counts
-   Quick add-to-cart functionality
-   Shopping cart drawer
-   Increase/decrease cart quantity
-   Remove products from cart
-   Automatic subtotal and total calculation
-   Search modal with live product search
-   Client registration
-   Client sign-in simulation
-   Client profile page
-   Sign-out functionality
-   Order checkout form
-   Order confirmation screen
-   Order history
-   Newsletter subscription UI
-   Toast notifications
-   Responsive design for desktop and mobile
-   Persistent cart, user, and order data using browser `localStorage`

## 🛠️ Technologies Used

### Frontend

-   HTML5
-   CSS3
-   JavaScript (Vanilla JS)
-   Tailwind CSS
-   Font Awesome 6.4.0
-   Google Fonts:
    -   Cormorant Garamond
    -   Plus Jakarta Sans

### Browser Storage

The application uses `localStorage` to persist:

-   `aurelia_cart` --- shopping cart
-   `aurelia_user` --- current client profile
-   `aurelia_orders` --- order history

### External Assets

The project loads visual assets from external image URLs and imports
Tailwind CSS, Google Fonts, and Font Awesome through CDN resources.

## 📁 Project Structure

The current project is intentionally implemented as a single HTML file:

``` text
AURELIA-Luxury-Ecommerce/
│
├── luxury_e_commerce_suite.html
└── README.md
```

### Main HTML File

`luxury_e_commerce_suite.html`

This file contains:

-   HTML layout
-   Tailwind configuration
-   Custom CSS
-   Product data
-   Application state
-   Client-side router
-   Home page rendering
-   Shop rendering
-   Product details
-   Cart management
-   Checkout
-   Authentication
-   Account/order history
-   Search
-   Mobile menu
-   Notifications

## 🛍️ Product Categories

The application currently contains four product categories:

### Timepieces

Examples include:

-   Le Chronographe Impérial
-   Tourbillon Souverain Royale

### Jewelry

Examples include:

-   Collier Cascade de Diamants
-   Bague Solitaire Éternité

### Leather Goods

Examples include:

-   Sac Malletier Alligator Noir
-   Porte-Documents Diplomate

### Fragrance

Examples include:

-   Extrait de Parfum "Nuit d'Or"
-   Bougie Parfumée "Palais de Versailles"

## 🧭 Application Navigation

The application uses a lightweight JavaScript router instead of multiple
HTML pages.

Available views include:

``` text
home
shop
product
checkout
account
```

Navigation is handled through the `router.navigate()` function.

Example:

``` javascript
router.navigate('shop');
router.navigate('product', { id: 'aur-001' });
router.navigate('checkout');
router.navigate('account');
```

## 🛒 Shopping Cart Flow

The shopping process works as follows:

``` text
Browse Products
      ↓
View Product Details
      ↓
Add to Shopping Bag
      ↓
Open Cart
      ↓
Update Quantity / Remove Item
      ↓
Proceed to Checkout
      ↓
Enter Shipping & Payment Information
      ↓
Submit Order
      ↓
Order Confirmation
      ↓
Order Saved to Order History
```

Cart data is stored in browser `localStorage`, allowing the cart to
remain available after refreshing the page.

## 👤 Authentication Flow

AURELIA provides a client authentication interface with:

-   Sign In
-   Create Account
-   Sign Out
-   Client Profile
-   Order History

The current implementation is a **frontend authentication simulation**.
User information is stored in browser `localStorage`; there is no
backend authentication server.

## 📦 Checkout and Orders

The checkout page contains sections for:

### Shipping Information

-   First Name
-   Last Name
-   Street Address
-   City
-   Postal Code
-   Country

### Payment Information

-   Card Number
-   Expiration Date
-   Security Code

After checkout submission, an order is generated with:

-   Unique order ID
-   Order date
-   Ordered items
-   Total amount
-   Order status

Example order ID format:

``` text
AUR-123456
```

The order is then stored in:

``` text
localStorage → aurelia_orders
```

## 🔎 Search

The search feature provides live product matching.

Search can match against:

-   Product name
-   Category
-   Product description

For example:

``` text
watch
jewelry
fragrance
leather
```

Matching products are displayed dynamically in the search modal.

## 🎨 UI / Design

The visual design follows a luxury aesthetic using:

-   Black background
-   Dark gray surfaces
-   Gold accents
-   Serif typography for luxury headings
-   Sans-serif typography for interface elements
-   Rounded cards
-   Subtle borders
-   Hover animations
-   Responsive grids
-   Backdrop blur effects
-   Toast notifications

Custom luxury colors are defined in the Tailwind configuration:

``` text
Background: #0a0a0a
Surface:    #141414
Card:       #1a1a1a
Border:     #2a2a2a
Gold:       #d4af37
Gold Light: #f3e5ab
Gold Dark:  #aa8c2c
```

## 🚀 How to Run the Project

### Method 1 --- Directly in Browser

1.  Download or clone the project.
2.  Open `luxury_e_commerce_suite.html`.
3.  Open the file in a modern web browser.
4.  The AURELIA storefront will load.

### Method 2 --- Using VS Code

1.  Open the project folder in Visual Studio Code.
2.  Install the **Live Server** extension if needed.
3.  Right-click `luxury_e_commerce_suite.html`.
4.  Select **Open with Live Server**.
5.  The application will open in your browser.

## 💻 Recommended Browser

Use a modern browser such as:

-   Google Chrome
-   Microsoft Edge
-   Mozilla Firefox
-   Safari

An internet connection is recommended because the project loads CDN
resources, Google Fonts, and external product images.

## ⚙️ Application State

The application maintains its state using a JavaScript object:

``` javascript
let state = {
    cart: [],
    user: null,
    currentView: 'home',
    viewParams: {},
    orders: []
};
```

State is synchronized with browser storage through:

``` javascript
localStorage
```

## 🔐 Important Security Note

This project is currently a **frontend demonstration/prototype**.

It should not be used as a real production e-commerce payment or
authentication system without a secure backend.

In particular:

-   Passwords are not securely stored or hashed.
-   Authentication is simulated on the client side.
-   Payment information is only represented by frontend form fields.
-   No real payment gateway is connected.
-   No backend database is connected.
-   Product data is stored directly in JavaScript.
-   Orders are stored in browser `localStorage`.
-   External images are loaded from remote URLs.

For a production system, implement a secure backend, encrypted
authentication, server-side validation, a real database, and a
PCI-compliant payment provider.

## 🔮 Future Enhancements

Possible improvements include:

-   Build a Django or Express.js backend
-   Add MySQL/PostgreSQL/MongoDB database
-   Implement real user authentication
-   Hash passwords securely
-   Add JWT/session-based authentication
-   Add admin dashboard
-   Add product management
-   Add real inventory management
-   Add payment gateway integration
-   Add real order tracking
-   Add product reviews and ratings
-   Add wishlist functionality
-   Add coupon/discount system
-   Add shipping API integration
-   Add email order confirmations
-   Add REST API
-   Add backend validation
-   Add automated testing
-   Deploy frontend and backend separately
-   Add CI/CD pipeline
-   Add proper environment-variable management

## 📚 Learning Outcomes

This project demonstrates practical concepts including:

-   Responsive web design
-   Tailwind CSS
-   Vanilla JavaScript
-   DOM manipulation
-   Client-side routing
-   Dynamic HTML rendering
-   Event handling
-   Browser localStorage
-   E-commerce cart logic
-   Search and filtering
-   Form handling
-   Authentication UI
-   Checkout workflow
-   Order management
-   Responsive navigation
-   UI/UX design

## 📸 Project Highlights

The main application includes:

1.  Luxury landing page
2.  Collection/shop page
3.  Category filters
4.  Product detail page
5.  Shopping bag
6.  Search interface
7.  Sign-in/register modal
8.  Checkout page
9.  Order confirmation
10. Client profile and order history

## 👨‍💻 Project Information

**Project Name:** AURELIA --- Maison de Luxe\
**Project Type:** Frontend E-Commerce Web Application\
**Domain:** E-Commerce / Web Development\
**Frontend:** HTML5, CSS3, JavaScript, Tailwind CSS\
**Storage:** Browser localStorage\
**Design:** Luxury black-and-gold theme

## 📄 License

This project is intended for educational and demonstration purposes.
Review the licenses and usage terms of third-party fonts, libraries,
images, and CDN resources before using the project commercially.

------------------------------------------------------------------------

## ⭐ AURELIA

> The Art of Timeless Elegance

A premium frontend e-commerce experience for showcasing luxury products
with a modern, responsive, and interactive interface.
