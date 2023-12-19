# techuz-test-fullstack

### Database Tables

#### Users Table
- `id`
- `name`
- `email`
- `password`

#### Products Table
- `id`
- `title`
- `description`
- `createdBy`
- `order`
- `createdAt`

### Backend

1. Set up authentication using JWT, ensuring that authentication is performed using AES-256 keys rather than a random string.
2. Implement a token mechanism with both accessToken and refreshToken.
3. *Token Expiry Logic:*
   - Keep accessToken expiry to 1 minute.
   - Keep refreshToken expiry to 3 minutes.
   - If the accessToken expires and the refreshToken does not, regenerate the tokens and set them for the user.
   - If both tokens are expired, do not allow users to create, update, or delete products.

4. Only authenticated users are allowed to mutate the product.
5. Authenticated or unauthenticated users will have access to the list of products.

### Frontend

1. *Registration Page*
2. *Login Page*
3. *Product Listing Page*
   - Include a filter for "My Products." Selecting that filter should list products created by the currently logged-in user.
4. *Token Handling*
   - Do not pass the token from the header as authorization.

5. *Profile Page*
   - Display a list of logged-in user's created products.
   - Include a button to create a new product.

6. *Update and Delete Operations*
   - Allow users to update and delete products.

7. *Product Shuffling*
   - Allow users to rearrange products from the frontend.
   - Display products in a specific order on the profile and product listing pages.

8. *Product Listing Logic*
   - Order products based on recently created and product order.

   Example:
   - USER1 created u1product1 (order 1) and u1product2 (order 2).
   - After some time, USER2 created 3 products: u2product1 (order 3), u2product2 (order 2), u2product3 (order 1).
   - Product listing should be:
     1. u2product3
     2. u1product1
     3. u2product2
     4. u1product2
     5. u2product1

### Notes

1. Use any ORM for the backend (MySQL or PostgreSQL).
2. Use any React component library.
3. Consider deploying to an open-source platform like render.com (optional but a plus point).
