## Node.js/Express CRUD API Starter

A minimal backend starter for building RESTful CRUD APIs with Express and MongoDB (Atlas). This repository contains only the server-side code extracted from a MERN stack app, prepared as a clean starting point under your own Git history.

### Features
- Express server with CORS and JSON middleware
- MongoDB connection via official driver
- Example CRUD routes under `/record`
- Environment-based configuration using `dotenv`

### Tech Stack
- Node.js + Express
- MongoDB (Atlas) using `mongodb` driver
- Optional: Mongoose is installed but not required by the current routes

### Endpoints
- `GET /record` — List all records
- `GET /record/:id` — Get a record by ID
- `POST /record` — Create a record `{ name, position, level }`
- `PATCH /record/:id` — Update a record `{ name, position, level }`
- `DELETE /record/:id` — Delete a record

### Getting Started
1. Clone the repository and install dependencies:
   ```bash
   cd server
   npm install
   ```

2. Create an `.env` file in `server/` with your MongoDB Atlas URI:
   ```bash
   ATLAS_URI=mongodb+srv://<user>:<password>@<cluster-url>/?appName=<AppName>
   ```
   Note: If your password contains special characters like `@`, URL-encode them (e.g., `@` -> `%40`).

3. Start the API server:
   ```bash
   node server.js
   ```
   The server runs on `http://localhost:5050` by default.

### Project Structure
```
server/
  db/
    connection.js     # MongoDB connection (reads ATLAS_URI)
  routes/
    record.js         # CRUD endpoints
  server.js           # Express app entry point
``` 

### Configuration
- `PORT` (optional): Port for the Express server. Defaults to `5050`.
- `ATLAS_URI` (required): MongoDB connection string.

### Example Request
```bash
curl -X POST http://localhost:5050/record \
  -H "Content-Type: application/json" \
  -d '{"name":"Alice","position":"Engineer","level":"Senior"}'
```

### Notes
- The original frontend has been removed to keep this a backend-only starter.
- Consider adding a `.gitignore` that excludes `node_modules/`.

### License
MIT or your preferred license.

