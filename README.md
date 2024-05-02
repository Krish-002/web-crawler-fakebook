# Web Crawler for Fakebook

## Description

This project implements a web crawler that gathers data from a fake social networking website called Fakebook. The crawler is designed to navigate through the site, logging in with provided credentials, and traversing various pages to collect secret flags hidden within the HTML.

## Approach

The crawler is built in Python and uses a combination of socket programming and regular expressions to interact with the HTTP protocol and parse HTML content. The main components of the crawler include:

- HTTP GET and POST request handling
- Cookie management for session persistence
- URL parsing and validation
- HTML content parsing to extract URLs and secret flags

The crawler maintains a frontier of URLs to visit and a set of visited URLs to avoid loops. It starts from the homepage and recursively visits linked pages, collecting secret flags along the way.

## Challenges

- **CSRF Token Handling:** Extracting and integrating the CSRF token into the login request was a challenge, as it required parsing the login page's HTML content to find the token value.
- **Avoiding Loops:** Ensuring the crawler did not revisit the same pages or enter infinite loops required careful management of the frontier and visited URLs.
- **HTTP Status Code Handling:** Properly handling various HTTP status codes like 302 (Found), 403 (Forbidden), and 503 (Service Unavailable) was crucial for the crawler's robustness.

## Testing

Testing was done incrementally, starting with basic HTTP requests and gradually integrating more complex features like login, cookie handling, and HTML parsing. Each component was tested individually before being integrated into the main crawler logic. The crawler was then tested on the Fakebook site to ensure it could successfully navigate the site, handle various scenarios, and collect all secret flags.

## Usage

To run the crawler, use the following command:

```bash
./3700crawler -s <server> -p <port> <username> <password>
