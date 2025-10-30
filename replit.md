# Site de Vendas de Açaí - Açaí Prime

## Overview
Açaí Prime is an e-commerce platform designed for selling Açaí products, featuring integrated payment systems via PIX (Pagou.ai) and Credit Card (Mercado Pago). The project aims to provide a robust, scalable, and user-friendly online store with a comprehensive administrative panel for product, order, and review management, alongside real-time analytics. This project serves as a development and testing environment for point-of-sale processing, with specific considerations for handling card data internally.

## User Preferences
I prefer detailed explanations. Ask before making major changes. I want iterative development. I like to see the overall architecture and then drill down into specific components.

## System Architecture

### UI/UX Decisions
- **Color Scheme**: Primary (Purple): `hsl(280 50% 45%)`, Accent (Yellow): `hsl(45 100% 62%)`.
- **Font**: Poppins (Google Fonts).
- **Branding**: Professional AI-generated logo featuring an açaí bowl.
- **Key Components**:
    - **Geolocation Modal**: Automatically detects user's city via IP, allows manual selection, and saves preferences.
    - **Dynamic Promotion Banner**: Animated gradient banner displaying "Free Delivery for [CITY]!"
    - **Redesigned Header**: Centralized logo, "OPEN" badge, essential business info (min. order, delivery time, location, rating), social icons, and shopping cart.
    - **Reviews Section**: Displays customer reviews with photos, names, ratings, and comments.
    - **Product Cards**: Feature hover effects for enhanced interaction.
    - **Slide-in Cart**: Seamless shopping cart experience.

### Technical Implementations
- **Frontend**: React with TypeScript, utilizing Vite for development.
- **Backend**: Express.js with MySQL database.
- **Database ORM**: Drizzle ORM for database interactions.
- **Validation**: Zod and React Hook Form for robust form validation.
- **Styling**: Shadcn/ui and Tailwind CSS for modern and responsive UI.
- **Payment Processing**: Pagou.ai for PIX and Mercado Pago for credit card payments.
- **Admin Panel**: Secure authentication (bcrypt, express-mysql-session, rate limiting), product management (CRUD, image upload), order management, review management, transaction viewing, and real-time analytics.
- **Geolocation**: Uses ip-api.com for IP-based location detection with caching.
- **Axios**: Used for HTTP requests, ensuring compatibility across environments.
- **Environment**: Configured for Replit development and Autoscale deployment.

### Feature Specifications
- **Product Management**: Add, edit, delete, activate/deactivate, stock control, promotions, highlight order, image uploads.
- **Order Management**: View all orders, full details, payment status, customer data.
- **Review Management**: Add, edit, approve/reject, moderate reviews.
- **Transaction Management**: View all transactions, including masked card data (last 4 digits).
- **Analytics Dashboard**: Page views, total orders, PIX generated, card payments, total revenue, conversion rate, recent orders.
- **Customization Page**: Allows users to customize açaí with free fruits, toppings, and extras with visual counters and validation.
- **Checkout Process**: Displays selected toppings, handles customer data, and payment selection.
- **Confirmation Page**: Shows PIX QR code or card payment status.

### System Design Choices
- **Authentication**: Bcrypt for password hashing, `express-mysql-session` for persistent sessions in MySQL, rate limiting for security, HttpOnly and SameSite=lax cookies.
- **Database Schema**: `products`, `orders` (with JSON `toppings` column), `transactions`, `toppings`, `admin_users`, `analytics_events`, `reviews`, and `sessions` tables.
- **API Endpoints**: Comprehensive set of public and authenticated admin endpoints for all core functionalities.
- **Deployment**: Configured for Replit Autoscale and recommended Render.com deployment with a detailed guide.

## External Dependencies

- **MySQL**: Database solution, specifically tested with Hostinger MySQL.
- **Pagou.ai**: Primary PIX payment gateway (`PAGOUAI_API_KEY`).
- **Mercado Pago**: Credit card payment processing (requires `MERCADO_PAGO_ACCESS_TOKEN` and `VITE_MERCADO_PAGO_PUBLIC_KEY`).
- **ip-api.com**: Geolocation API for IP-based location detection.
- **Drizzle ORM**: Used for database interactions with MySQL.
- **React**: Frontend library.
- **Express.js**: Backend web framework.
- **Vite**: Frontend build tool.
- **Axios**: HTTP client for API requests.
- **bcrypt**: For password hashing.
- **express-mysql-session**: For storing session data in MySQL.
- **Zod**: Schema validation library.
- **React Hook Form**: For form management.
- **Shadcn/ui & Tailwind CSS**: UI component library and CSS framework.
- **qrcode library**: For generating QR codes.