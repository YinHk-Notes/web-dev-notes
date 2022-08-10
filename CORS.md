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


## 

HTTP response headers[#](https://www.keycdn.com/support/cors#http-response-headers)

The domain who's resources are being requested can respond to the first domain with the following HTTP response headers based on what configuration options are set.

-   `Access-Control-Allow-Origin`
-   `Access-Control-Allow-Credentials`
-   `Access-Control-Expose-Headers`
-   `Access-Control-Max-Age`
-   `Access-Control-Allow-Methods`
-   `Access-Control-Allow-Headers`

## 

Simple CORS example[#](https://www.keycdn.com/support/cors#simple-cors-example)

Here is a simple CORS example of when a browser requests a resource from another domain. Let's say `domainx.com` makes a request to `domainy.com` for a particular resource. CORS uses HTTP headers to determine whether or not `domainx.com` should have access to that resource. The browser automatically sends a request header to `domainy.com` with

```none
Origin: http://domainx.com
```

`domainy.com` receives that request and will respond back with either:

1.  `Access-Control-Allow-Origin: http://domainx.com`
2.  `Access-Control-Allow-Origin: *` (meaning all domains are allowed)
3.  An error if the cross-origin requests are not allowed
