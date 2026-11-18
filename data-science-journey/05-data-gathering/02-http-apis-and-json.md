# Data Gathering: HTTP APIs and JSON

## 1. Introduction and definition
An API exposes a documented interface for requesting or submitting data. HTTP methods express operations and JSON is a common response format.

## 2. Why we need this
APIs provide repeatable access to live or regularly updated data.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| `GET` | Retrieve a resource. |
| `POST` | Submit data or request creation/action. |
| `PUT/PATCH` | Replace a resource or partially update it. |
| `DELETE` | Request deletion. |
| `Status codes` | 2xx success, 4xx client issue, 5xx server issue. |
| ``requests.get/post`` | Send HTTP requests. |
| ``.raise_for_status`` | Raise for unsuccessful HTTP status. |
| ``.json`` | Decode a JSON response. |
| `Timeouts` | Bound how long a request waits. |
| `Pagination/rate limits` | Retrieve results in pages and respect service limits. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
import requests
response = requests.get("https://api.github.com", timeout=15)
response.raise_for_status()
payload = response.json()
print(response.status_code, isinstance(payload, dict))
```

## 5. Advanced examples
```python
# Robust pattern for an endpoint you are authorized to use
def fetch_json(url):
    response = requests.get(url, timeout=(5, 20))
    response.raise_for_status()
    return response.json()
```

## 6. Practical real-world applications
Collect weather, exchange-rate, public statistics or product information from documented APIs.

## 7. Common mistakes
Hard-coding API keys; omitting timeouts; retrying non-idempotent requests blindly; ignoring pagination, rate limits and terms of service.

## 8. Practice questions
Fetch a public endpoint; handle 404 and 500 responses; flatten nested JSON into a DataFrame; implement pagination.

## 9. Interview questions
What is REST? Difference between PUT and PATCH? Why use timeouts? What is pagination?

## 10. Related functions and concepts
JSON, requests, authentication, data provenance and error handling.
