# Oapprd - HTTP Proxy Server

A simple HTTP proxy server built with Node.js that forwards requests to specified target URLs.

## Features

- Forward HTTP requests to any target URL
- Simple configuration via headers or query parameters
- Error handling and logging
- Lightweight and fast

## Installation

```bash
npm install
```

## Usage

### Start the proxy server

```bash
npm start
```

The server will run on `http://localhost:3000`

### Making requests through the proxy

#### Method 1: Using X-Proxy-Target header (recommended)

```bash
curl -H "X-Proxy-Target: https://api.example.com/endpoint" http://localhost:3000/
```

#### Method 2: Using URL path

```bash
curl http://localhost:3000/https://api.example.com/endpoint
```

### Examples

```bash
# Proxy a request to Google
curl -H "X-Proxy-Target: https://www.google.com" http://localhost:3000/

# Proxy an API request
curl -H "X-Proxy-Target: https://jsonplaceholder.typicode.com/posts/1" http://localhost:3000/

# Proxy with custom headers
curl -H "X-Proxy-Target: https://api.example.com" \
     -H "Authorization: Bearer token123" \
     http://localhost:3000/
```

## Development

Run with auto-reload on file changes:

```bash
npm run dev
```

## Configuration

Set the `PORT` environment variable to change the port:

```bash
PORT=8080 npm start
```

## Error Handling

The proxy returns proper error responses:

- **400 Bad Request**: Missing or invalid target URL
- **500 Internal Server Error**: Proxy error occurred

## License

MIT
