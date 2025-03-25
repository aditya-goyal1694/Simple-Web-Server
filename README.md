# Basic Web Server in Go

This is a simple web server written in Go. It serves static files from a directory and provides basic HTTP handlers for a form and a hello endpoint.

## Features
- Serves static files from the `./static` directory.
- Handles `GET /hello` requests.
- Handles `POST /form` requests and processes form data.
- Runs on port `8080`.

## Prerequisites
- Install [Go](https://golang.org/dl/) (version 1.21 or later recommended)

## Installation
1. Clone the repository:
   ```sh
   git clone https://github.com/yourusername/go-web-server.git
   cd go-web-server
   ```
2. Initialize a Go module (if not already initialized):
   ```sh
   go mod init go-web-server
   ```
3. Build the application:
   ```sh
   go build
   ```

## Usage
### Running the Server
Execute the following command:
```sh
go run main.go
```
The server will start on `http://localhost:8080/`.

### Endpoints
#### 1. Static File Server
- The server serves files from the `./static` directory.
- Place your static files (HTML, CSS, JS, etc.) inside this directory.
- Access them via `http://localhost:8080/filename`.

#### 2. `GET /hello`
Returns a simple "Hello!" message.
```sh
curl http://localhost:8080/hello
```
Response:
```
Hello!
```

#### 3. `POST /form`
Handles form submissions.
```sh
curl -X POST -d "name=John&address=NewYork" http://localhost:8080/form
```
Response:
```
POST request successful
Name = John
Address = NewYork
```

## Error Handling
- If an unsupported path is requested, the server returns `404 not found`.
- If `POST /form` is called without proper form data, an error message is returned.

