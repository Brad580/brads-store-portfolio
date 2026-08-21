# Brad's Store

[Live demo](https://teal-vacherin-1fb265.netlify.app/) | [Portfolio repository](https://github.com/Brad580/brads-store-portfolio)

Brad's Store is a responsive full-stack commerce portfolio project. The frontend provides a complete catalog-to-checkout experience, while the companion Express/MongoDB API demonstrates authentication, product, user, and cart workflows.

## What I built

I extended the original FakeStoreAPI codebase with 17 commits under my GitHub identities. My work includes:

- A React/Vite storefront with category filtering, search, sorting, loading states, and error handling
- Persistent cart state, quantity controls, shipping calculations, demo checkout, and order confirmation
- Browser-only demonstration accounts that do not store payment information
- Express 5 API hardening with explicit CORS configuration, payload limits, environment-based secrets, and disabled framework headers
- Password hashing, JWT authentication, product CRUD, and normalized cart operations
- A distinct responsive catalog visual system and accessible form controls
- Five automated tests across the React cart/authentication flows and API health behavior

## Verified project evidence

- 24 application routes plus a health endpoint
- Three MongoDB models: users, products, and carts
- Five automated tests using Vitest, React Testing Library, and Supertest
- 20 catalog products in the public demonstration dataset
- 17 commits attributable to Brad Travers / Brad580 in the current history

## Architecture

```text
React / Vite storefront
        |
        | catalog requests and demo UI state
        v
Fake Store API or configured compatible API

Express API
        |
        | Mongoose
        v
MongoDB
```

The deployed portfolio frontend uses a public demonstration catalog. The backend remains independently runnable to demonstrate REST API, authentication, and MongoDB implementation.

## Run the storefront

```bash
cd client
cp .env.example .env
npm install
npm run dev
```

Production verification:

```bash
npm test
npm run build
```

## Run the API

```bash
cp .env.example .env
npm install
npm test
npm start
```

Set a private `DATABASE_URL`, a long random `JWT_SECRET`, and the permitted `CLIENT_ORIGIN` in `.env`. Environment files are excluded from Git.

## Attribution and ownership

This project began as a fork of [keikaavousi/fake-store-api](https://github.com/keikaavousi/fake-store-api). The upstream project supplied the original API foundation and sample data. The storefront experience, portfolio-focused frontend, tests, checkout flow, API safety improvements, and current visual system are Brad Travers's additions.

For the clearest portfolio presentation, publish this version in a clean repository while retaining the attribution above. That separates Brad's authored work from the inherited commit history without concealing the original source.

## Safety

The checkout is a portfolio demonstration. It does not request, transmit, or store payment-card information. Never commit `.env` files or production database credentials.
