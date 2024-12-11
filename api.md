# API: Application Programming Interfaces

## Define
An Application Programming Interface (API) is a contract that allows code to talk to other code.

---

## Types of APIs

### Hardware APIs
- **Description:** Interface for software to talk to hardware.
- **Example:** How your phone's camera communicates with the operating system.

### Software Library APIs
- **Description:** Interface for directly consuming code from another code base.
- **Example:** Using methods from a library imported into your application.

### Web APIs
- **Description:** Interface for communicating across code bases over a network.
- **Example:** Fetching current stock prices from a finance API over the internet.

### Legacy APIs
- Older systems or methods still in use.

---

## API Architecture

APIs can be built using various architectures, including:
- **REST (Representational State Transfer)**
- **GraphQL**
- **WebSockets**
- **Webhooks**
- **SOAP (Simple Object Access Protocol)**
- **gRPC (Google Remote Procedure Call)**
- **MQTT (MQ Telemetry Transport)**

---

## REST APIs

### Key Traits
- Stateless: Does not store session state between requests.
- Cacheable.
- Supports various data types (e.g., JSON, XML).

### Advantages
- Operations utilize HTTP methods like `GET`, `POST`, `PUT`, `DELETE`, `OPTIONS`, and `PATCH`.
- Client and server are decoupled.
- Cache-friendly.
- Supports multiple data formats.
- Flexible for public-facing APIs.

### Disadvantages
- Large payloads due to rich metadata.
- Potential over- or under-fetching issues.
- No binding contract for message structure.
- Implementation can lead to back-and-forth negotiations.

---

## API Access Types

- **Public APIs (Open APIs):** Accessible by anyone.
- **Private APIs:** Used within an organization and not public.
- **Partner APIs:** Shared between organizations with established relationships.

---

## HTTP Request Methods

| Method       | Operation          |
|--------------|--------------------|
| `GET`        | Retrieve data (Read) |
| `POST`       | Send data (Create)   |
| `PUT`/`PATCH`| Update data (Update) |
| `DELETE`     | Delete data (Delete) |

- **`PUT`** usually replaces an entire resource.
- **`PATCH`** is used for partial updates.

---

## API URL Structure

A request URL consists of:
- **Protocol:** `http` or `https`
- **Host:** e.g., `library-api.postman.com`
- **Path:** e.g., `/books`

**Example:**
```
http://library-api.postman.com/books
```
Paths and complete URLs are also referred to as API endpoints.

---

## Response Status Codes

| Code Range  | Meaning             | Examples                  |
|-------------|---------------------|---------------------------|
| `2xx`       | Success             | `200 OK`, `201 Created`  |
| `3xx`       | Redirection         | `301 Moved Permanently`  |
| `4xx`       | Client Error        | `400 Bad Request`, `404 Not Found` |
| `5xx`       | Server Error        | `500 Internal Server Error` |

---

## Query Parameters

### Syntax
Query parameters refine a request. They start with `?`, followed by key-value pairs separated by `&`.

**Example:**
```
GET https://some-api.com/photos?orientation=landscape&size=500x400
```

---

## Post Method Example

- Add API key and value in the header portion.
- Required for authorized endpoints.
- Example: Use `POST` to delete data.

---

## Scripting in Postman

### Key Features
- Add automation and dynamic behavior to requests.
- Scripts execute during two events:
  1. **Pre-request script:** Before a request is sent.
  2. **Post-response script:** After a response is received.

### The `pm` Object
Postman provides the `pm` object to interact with:
- Environment
- Requests
- Responses
- Variables

#### Examples
- Access JSON response:
  ```javascript
  pm.response.json();
  ```

- Get a collection variable:
  ```javascript
  pm.collectionVariables.get("baseUrl");
  ```

- Set a collection variable:
  ```javascript
  pm.collectionVariables.set("myVar", "foo");
  ```

---
