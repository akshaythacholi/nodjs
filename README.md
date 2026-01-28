# Simple Node.js API

A simple REST API built with Node.js and Express for deployment to AWS EKS.

## Features

- RESTful API endpoints
- User management (CRUD operations)
- Health check endpoint
- Dockerized application
- Ready for Kubernetes deployment

## API Endpoints

- `GET /` - Welcome message and API info
- `GET /health` - Health check
- `GET /api/users` - Get all users
- `GET /api/users/:id` - Get user by ID
- `POST /api/users` - Create new user
- `PUT /api/users/:id` - Update user
- `DELETE /api/users/:id` - Delete user

## Running Locally

### Prerequisites
- Node.js 18 or higher
- npm

### Installation

1. Install dependencies:
```bash
npm install
```

2. Start the server:
```bash
npm start
```

3. For development with auto-reload:
```bash
npm run dev
```

The server will start on `http://localhost:3000`

## Testing the API

### Get all users:
```bash
curl http://localhost:3000/api/users
```

### Create a new user:
```bash
curl -X POST http://localhost:3000/api/users \
  -H "Content-Type: application/json" \
  -d '{"name":"Alice Brown","email":"alice@example.com"}'
```

### Get user by ID:
```bash
curl http://localhost:3000/api/users/1
```

### Update user:
```bash
curl -X PUT http://localhost:3000/api/users/1 \
  -H "Content-Type: application/json" \
  -d '{"name":"John Updated","email":"john.updated@example.com"}'
```

### Delete user:
```bash
curl -X DELETE http://localhost:3000/api/users/1
```

## Running with Docker

### Build the image:
```bash
docker build -t simple-nodejs-api .
```

### Run the container:
```bash
docker run -p 3000:3000 simple-nodejs-api
```

## Deployment to EKS

See the GitHub Actions workflow in `.github/workflows/deploy.yml` for automated deployment to AWS EKS.

## Environment Variables

- `PORT` - Server port (default: 3000)
- `NODE_ENV` - Environment mode (development/production)

## License

MIT
.
