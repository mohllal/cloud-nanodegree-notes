# Section 5: Authentication

- A server-side cookie is a type of cookie that is set by an HTTP server, but its value will not be available to JavaScript code running in a browser. A value of a server-side cookie is only available to a browser, and it will automatically send with requests as a normal cookie. Since a cookie is not available to JavaScript code running in a browser it cannot be accessed by any malicious code. If a JWT token is stored in a server-side cookie it can be used for authentication in a more secure fashion.
