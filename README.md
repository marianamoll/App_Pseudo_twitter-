# App_Pseudo_twitter

## Project Overview

This project is a **client-side X (Twitter) clone** built as a single-page web application.

Users can create an account, log in and out, view published messages, and publish their own messages on the feed. All communication between the client and server is performed asynchronously using the **Fetch API and GET/POST requests**.

## Architecture

The application follows a client-server architecture:

* **Frontend:** JavaScript, HTML and CSS, with dynamic DOM-based rendering.
* **Backend:** Node.js server exposing a REST/JSON API.
* **Database:** SQL database used to store users and messages.
* **Authentication:** A custom **session manager implemented on the web server**, rather than storing sessions in the database. The client stores a session identifier and sends it with authenticated requests.
* **Communication:** All client-server interactions are performed through asynchronous `fetch()` requests.

## Main Features

* User registration and authentication
* Login and logout system
* Session-based authentication
* Message creation and display
* Chronological message feed
* Automatic feed refresh every **5 seconds**
* Fully asynchronous communication using the Fetch API
* Dynamic client-side interface without server-side rendering
* **HTTPS** enabled on the Node.js server

## Session Management

Instead of storing usernames and passwords in the browser's local storage, we implemented a **custom session manager**.

After a successful login, the server generates a unique session identifier. This identifier is stored by the client and used to authenticate subsequent requests, such as publishing a message.

Sessions are managed **in memory on the web server**, rather than being stored in the database. This keeps session information separate from the SQL database and provides a lightweight session management mechanism.

## Automatic Updates

The message feed is automatically refreshed every **5 seconds**, allowing newly published messages to appear without requiring the user to manually reload the page.

## Security

The application is served over **HTTPS**, ensuring encrypted communication between the client and the server.

Authentication is handled through session identifiers rather than sending the user's password with every request.

Additional security measures were implemented:

* Login is **blocked after more than 5 consecutive failed password attempts**.
* Passwords must contain **at least 5 characters** and **at least one number**.
* User passwords are not stored in the browser's local storage.
* Session identifiers are used to authenticate requests after login.

## Technologies

* **JavaScript**
* **Node.js**
* **SQL**
* **HTML / CSS**
* **REST API**
* **Fetch API**
* **HTTPS**
* **Session-based authentication**
