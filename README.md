# http1-server

This repository provides a simple implementation of an HTTP/1.1 server using TCP connections.

The core implementation is located in the `internal` folder, while the `cmd/httpserver` directory contains a basic usage example.

The main TCP connection data reading implementation resides in the `internal` folder, which includes:

- `server` package - for server creation
- `request` package - for reading incoming requests
- `headers` package - handles request header parsing logic (used by both request and response packages)
- `response` package - manages server response logic

The response writer package also includes support for:

- A simplified version of chunked encoding
- HTTP trailers

### How to run it

Clone the repo

```bash
git clone https://github.com/lealre/http1-server.git
```

Access the project folder

```bash
cd http1-server
```

Start the server

```bash
go run ./cmd/httpserver
```

This will start the server at `localhost:42069`.

You can access the following endpoints in your browser:

- `/bad` - Simple HTML example
- `/error` - Simple HTML example
- `/httpbin/` - A proxy to [httpbin](https://httpbin.org/#/) endpoints for testing chunked encoding
- `/video` - A simple example of responding with binary data instead of text

---

This project is an extension of [this repository](https://github.com/lealre/httpfromtcp), created to better understand how HTTP works.
