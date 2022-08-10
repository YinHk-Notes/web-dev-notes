## Cross-Origin Resource Sharing (CORS)

***CORS (Cross-origin resource sharing)*** allows a webpage to request additional resources into browser from other domains e.g. fonts, CSS or static images from CDN. CORS helps in serving web content from multiple domains into browsers who usually have the same-origin security policy.

***Cross-Origin Resource Sharing (CORS)*** is an HTTP-header based mechanism that allows a server to indicate any origins (domain, scheme, or port) other than its own from which a browser should permit loading resources. 


**Cross-origin resource sharing (CORS)** is a mechanism that allows restricted resources on a web page to be requested from another domain outside the domain from which the first resource was served.

| Attribute | Description |
| --- | --- |
| origins | List of allowed origins. It’s value is placed in the Access-Control-Allow-Origin header of both the pre-flight response and the actual response."*" – means that all origins are allowed. If undefined, all origins are allowed. |
| allowedHeaders | List of request headers that can be used during the actual request. Value is used in preflight’s response header Access-Control-Allow-Headers."*" – means that all headers requested by the client are allowed. If undefined, all requested headers are allowed. |
| methods | List of supported HTTP request methods. If undefined, methods defined by RequestMapping annotation are used. |
| exposedHeaders | List of response headers that the browser will allow the client to access. Value is set in actual response header Access-Control-Expose-Headers. If undefined, an empty exposed header list is used. |
| allowCredentials | It determine whether browser should include any cookies associated with the request.false – cookies should not included." " (empty string) – means undefined.true – pre-flight response will include the header Access-Control-Allow-Credentials with value set to true.If undefined, credentials are allowed. |
| maxAge | Maximum age (in seconds) of the cache duration for pre-flight responses. Value is set in header Access-Control-Max-Age.If undefined, max age is set to 1800 seconds (30 minutes). |
