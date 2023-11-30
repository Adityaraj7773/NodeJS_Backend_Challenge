# NodeJS and MongoDB Backend Documentation

This documentation provides a comprehensive guide for setting up and using a Node.js and MongoDB backend system. The backend structure includes folders for configuration, controllers, middleware, models, and routes.

## Table of Contents

1. [Setup](#setup)
   - [1.1. Prerequisites](#prerequisites)
   - [1.2. Installation](#installation)
   - [1.3. Configuration](#configuration)
2. [Folder Structure](#folder-structure)
3. [Usage](#usage)
   - [3.1. Controllers](#controllers)
   - [3.2. Middleware](#middleware)
   - [3.3. Models](#models)
   - [3.4. Routes](#routes)
4. [Additional Information](#additional-information)

## 1. Setup <a name="setup"></a>

### 1.1. Prerequisites <a name="prerequisites"></a>

- [Node.js](https://nodejs.org/)
- [MongoDB](https://www.mongodb.com/try/download/community)

### 1.2. Installation <a name="installation"></a>

1. Clone the repository:

   ```bash
   git clone <repository-url>
   ```

2. Install dependencies:

   ```bash
   cd <repository-folder>
   npm install
   ```

### 1.3. Configuration <a name="configuration"></a>

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

## 2. Folder Structure <a name="folder-structure"></a>

The backend is organized into five main folders:

1. **config**: Contains configuration files, such as `db.js`, responsible for connecting to MongoDB.
2. **controllers**: Includes controllers for handling different aspects of the application, such as user and post-related actions.
3. **middleware**: Contains middleware functions, such as user validation and cookie handling.
4. **models**: Defines the data models for MongoDB, such as `post.model.js` and `user.model.js`.
5. **routes**: Defines the routes for different API endpoints, such as `post.routes.js` and `user.routes.js`.

## 3. Usage <a name="usage"></a>

### 3.1. Controllers <a name="controllers"></a>

#### 3.1.1. post.controller.js

- `createPost(req, res)`: Creates a new post.
- `getPost(req, res)`: Retrieves a specific post.
- `deletePost(req, res)`: Deletes a post.
- `likeUnlikePost(req, res)`: Likes or unlikes a post.
- `replyToPost(req, res)`: Adds a reply to a post.
- `getFeedPosts(req, res)`: Retrieves posts for the user's feed.

#### 3.1.2. user.controller.js

- `signup(req, res)`: Registers a new user.
- `login(req, res)`: Logs in a user.
- `logout(req, res)`: Logs out a user.
- `followUnfollowUser(req, res)`: Follows or unfollows a user.
- `updateUser(req, res)`: Updates user profile information.
- `getUserProfile(req, res)`: Retrieves a user's profile.

### 3.2. Middleware <a name="middleware"></a>

#### 3.2.1. validateCookies.js

- `ValidateCookies(userId, res)`: Generates and validates JWT cookies for user authentication.

#### 3.2.2. validateUser.js

- `validateUser(req, res, next)`: Validates user authentication using JWT cookies.

### 3.3. Models <a name="models"></a>

#### 3.3.1. post.model.js

Defines the MongoDB schema for posts, including fields such as `postedBy`, `text`, `img`, `likes`, and `replies`.

#### 3.3.2. user.model.js

Defines the MongoDB schema for users, including fields such as `name`, `username`, `email`, `password`, `profilePic`, `followers`, `following`, and `bio`.

### 3.4. Routes <a name="routes"></a>

#### 3.4.1. post.routes.js

Defines routes for post-related actions, including creating, getting, deleting, liking, unliking, replying, and getting feed posts.

#### 3.4.2. user.routes.js

Defines routes for user-related actions, including signing up, logging in, logging out, getting user profile, following, updating user profile, and unfollowing.

## 4. Additional Information <a name="additional-information"></a>

- The main entry file is `index.js`.
- The server runs on the specified port in the `.env` file.
