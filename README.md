# NodeJS and MongoDB Backend

This repository contains the backend structure for a Node.js and MongoDB application. The backend is organized into five main folders: `config`, `controllers`, `middleware`, `models`, and `routes`.

## Setup

### Prerequisites

- [Node.js](https://nodejs.org/)
- [MongoDB](https://www.mongodb.com/try/download/community)

### Installation

1. Clone the repository:

   ```bash
   git clone <repository-url>
   ```

2. Install dependencies:

   ```bash
   cd <repository-folder>
   npm install
   ```

### Configuration

1. Create a `.env` file in the root directory and add the following:

   ```env
   MONGODB_URL=<your-mongodb-url>
   JWT_SECRET=<your-jwt-secret>
   ```

   Replace `<your-mongodb-url>` and `<your-jwt-secret>` with your MongoDB connection URL and a secret key for JWT.

2. Run the server:

   ```bash
   npm start
   ```

   The server will run on the specified port in your `.env` file.

## Folder Structure

1. **config**: Configuration files for connecting to MongoDB.
2. **controllers**: Controllers for handling user and post-related actions.
3. **middleware**: Middleware functions for user validation and cookie handling.
4. **models**: Data models for MongoDB, defining post and user schemas.
5. **routes**: API routes for post and user actions.

## Usage

### Controllers

#### `post.controller.js`

- `createPost(req, res)`: Creates a new post.
- `getPost(req, res)`: Retrieves a specific post.
- `deletePost(req, res)`: Deletes a post.
- `likeUnlikePost(req, res)`: Likes or unlikes a post.
- `replyToPost(req, res)`: Adds a reply to a post.
- `getFeedPosts(req, res)`: Retrieves posts for the user's feed.

#### `user.controller.js`

- `signup(req, res)`: Registers a new user.
- `login(req, res)`: Logs in a user.
- `logout(req, res)`: Logs out a user.
- `followUnfollowUser(req, res)`: Follows or unfollows a user.
- `updateUser(req, res)`: Updates user profile information.
- `getUserProfile(req, res)`: Retrieves a user's profile.

### Middleware

#### `validateCookies.js`

- `ValidateCookies(userId, res)`: Generates and validates JWT cookies for user authentication.

#### `validateUser.js`

- `validateUser(req, res, next)`: Validates user authentication using JWT cookies.

### Models

#### `post.model.js`

Defines the MongoDB schema for posts, including fields such as `postedBy`, `text`, `img`, `likes`, and `replies`.

#### `user.model.js`

Defines the MongoDB schema for users, including fields such as `name`, `username`, `email`, `password`, `profilePic`, `followers`, `following`, and `bio`.

### Routes

#### `post.routes.js`

Defines routes for post-related actions, including creating, getting, deleting, liking, unliking, replying, and getting feed posts.

#### `user.routes.js`

Defines routes for user-related actions, including signing up, logging in, logging out, getting user profile, following, updating user profile, and unfollowing.

## Additional Information

- The main entry file is `index.js`.
- The server runs on the specified port in the `.env` file.
