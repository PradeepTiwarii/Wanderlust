# Wanderlust - A Listings and Reviews Web Application

## Overview

This is a full-stack web application built using **Node.js**, **Express**, and **MongoDB**. The app allows users to create, view, edit, and delete listings, as well as add and manage reviews for each listing. The application uses **EJS** as the templating engine for rendering views and is designed to perform common CRUD operations for listings and reviews.

## Features

- **View Listings**: Browse all available listings on the platform.
- **Create Listings**: Add new listings with details such as title, description, price, location, and country.
- **Edit Listings**: Modify the details of an existing listing.
- **Delete Listings**: Remove a listing from the database.
- **Add Reviews**: Users can add reviews to specific listings.
- **Delete Reviews**: Remove a review from a listing.
- **Error Handling**: Provides custom error pages for invalid routes and exceptions.

## Technologies

- **Backend**: Node.js, Express.js
- **Database**: MongoDB (via Mongoose)
- **Frontend**: EJS (Embedded JavaScript templating)
- **Middleware**: 
  - `method-override`: For supporting HTTP verbs such as PUT and DELETE in HTML forms.
  - `ejs-mate`: A layout engine for EJS to enable template inheritance.
  - `express.urlencoded`: Parses incoming request bodies.
- **Validation**: Joi is used to validate data before creating or updating listings and reviews.

## Project Structure

```
.
├── models/                  # Contains Mongoose models for Listing and Review
├── public/                  # Static assets (e.g., CSS, images, etc.)
├── views/                   # EJS templates for rendering web pages
├── utils/                   # Utility functions (e.g., async error handling)
├── schema.js                # Joi validation schemas for Listing and Review
├── app.js                   # Main entry point for the server
└── README.md                # Project documentation
```

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/wanderlust.git
   cd wanderlust
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Set up MongoDB:
   Make sure MongoDB is installed and running locally. By default, the app is configured to connect to:
   ```bash
   mongodb://127.0.0.1:27017/wanderlust
   ```
   You can modify the `MONGO_URL` variable in `app.js` if you are using a different setup.

4. Start the server:
   ```bash
   node app.js
   ```
   The app will be running on `http://localhost:8080`.

## Routes

### Listings

- **GET `/listings`**: Displays all listings.
- **GET `/listings/new`**: Renders a form to create a new listing.
- **POST `/listings`**: Creates a new listing.
- **GET `/listings/:id`**: Displays a specific listing by ID.
- **GET `/listings/:id/edit`**: Renders a form to edit a listing.
- **PUT `/listings/:id`**: Updates a specific listing.
- **DELETE `/listings/:id`**: Deletes a specific listing.

### Reviews

- **POST `/listings/:id/reviews`**: Adds a new review to a listing.
- **DELETE `/listings/:id/reviews/:reviewId`**: Deletes a review from a listing.

## Error Handling

- All undefined routes are handled with a 404 error page.
- Custom error handling middleware is used to handle exceptions and validation errors.

## Contributing

Feel free to submit pull requests or open issues to improve this project.

## License

This project is licensed under the MIT License.

---

