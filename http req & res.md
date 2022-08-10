## Http Request & response

**HTTP requests, and responses, share similar structure and are composed of:**

1. A ***start-line*** describing the requests to be implemented, or its status of whether successful or a failure. This start-line is always a single line.
2. An optional set of ***HTTP headers*** specifying the request, or describing the body included in the message.
3. A blank line indicating all meta-information for the request has been sent.
4. An optional ***body*** containing data associated with the request (like content of an HTML form), or the document associated with a response. The presence of the body and its size is specified by the start-line and HTTP headers.

> The **start-line** and **HTTP headers** of the HTTP message are collectively known as the ***head of the requests***, whereas its ***payload is known as the body***.


**HTTP Request Method:**

- **GET**
- **POST**
- **PUT**
- **HEAD**
- **DELETE**
- **PATCH**
- **OPTIONS**

最常見的 Method 為 Get 及Post。

### GET method

**GET is used to request data from a specified resource.** 

- 單純的跟 server 要一個連結或圖片，通常網頁都是 Get 的 request 比較多
- 最常使用的 Method
- 例如：要去某個網址、看某張圖片
- 傳送的資料會以 Query String 的方式加在 url 上
- GET requests can be cached
- GET requests remain in the browser history
- GET requests can be bookmarked
- GET requests should never be used when dealing with sensitive data
- GET requests have length restrictions
- GET requests are only used to request data (not modify)

### POST method

**POST is used to send data to a server to create/update a resource.**

- 例如：登入會員、送出表單
- 獲取「指定的」資訊，放在 request body(Form data）裡面
- POST requests are never cached
- POST requests do not remain in the browser history
- POST requests cannot be bookmarked
- POST requests have no restrictions on data length
- POST is **NOT idempotent**. So if we retry the request N times, we will end up having N resources with N different URIs created on the server.

> Client 端發出 request ；Server 端回傳 response,  網頁常用到的 http method 為 GET 及 POST 兩者差異在於，GET 偏向單純要東西，POST 會執行。
> 

### PUT method

Replace掉整個 request, **used to send data to a server to update a resource**

The difference between POST and PUT is that PUT requests are idempotent. **That is, calling the same PUT request multiple times will always produce the same result**. In contrast, **calling a POST request repeatedly have side effects of creating the same resource multiple times.**

`PUT` method is **[idempotent](https://restfulapi.net/idempotent-rest-apis/)**. So if we retry a request multiple times, that should be equivalent to a single request invocation.

PUT 比較正確的定義是 Replace (Create or Update)，例如`PUT item`
的意思是替換`item`
，如果已經存在就替換，沒有就新增。PUT 必須包含`item`
的所有屬性資料。

### PUT vs POST

****Idempotent REST APIs****

[](https://restfulapi.net/idempotent-rest-apis/)

In the context of REST APIs, when making multiple identical requests has the same effect as making a single request – then that REST API is called **idempotent**.

***Only `POST` APIs will not be idempotent*.**

1. `POST` is NOT idempotent.
2. `GET`, `PUT`, `DELETE`, `HEAD`, `OPTIONS` and `TRACE` are idempotent.

### HEAD method

HEAD is almost identical to GET, but without the response body. 只要獲取 request 的 header，不要 body。

- HEAD requests can be cached
- HEAD requests should never be used when dealing with sensitive data
- HEAD method is defined as idempotent, which means that multiple identical HEAD requests should have the same effect as a single request.
- HEAD requests are **useful for checking what a GET request will return before actually making a GET request** - like before downloading a large file or response body.
- HEAD request is used to check the **availability, size, and last modification date of a resource without downloading it** (as indicated by the Content-Length and Last-Modified headers). Example:
    
    > we can send a GET request to check if a PDF file is available for download. The server will return a 200 status code if the file is available and a 404 status code if the file is no longer available. The server will also return the PDF file contents in the response body. If the PDF file size is several megabytes, then we will get unnecessary traffic of several megabytes. In the case of a HEAD request, we will still get the 200 and 404 status codes, but without the extra few megabytes of traffic.
    > 

### HEAD vs GET

- HEAD method is much faster than the GET method because much less data is transferred in HEAD requests.
- Browsers use the HEAD method to update information about cached resources to check if the resource has been modified
- Difference between HEAD and GET requests is that for HEAD, the server only returns headers without body.

### **DELETE method**

DELETE method deletes the specified **resource. 刪除資源**

- Unlike [GET](https://reqbin.com/Article/HttpGet) and [HEAD](https://reqbin.com/Article/HttpHead) requests, the DELETE requests may change the server state.
- Sending a message body on a DELETE request might cause some servers to reject the request.
- DELETE method is defined to be **idempotent**, which means that **sending the same HTTP DELETE request multiple times will have the same effect on the server and will not additionally affect the state or cause additional side effects**.
- A successful response **MUST be**
    - **200 (OK)** if the server response includes a message body,
    - **202 (Accepted)** if the DELETE action has not yet been performed, or ****
    - **204 (No content)** if the DELETE action has been completed but the response does not have a message body.

### OPTIONS method

OPTIONS method describes the communication options for the target resource. 了解 server 提供哪些溝通方法.

**HTTP Verbs 就是對應 CRUD：**

- POST = 新增
- GET = 讀取
- PUT = 更新
- DELETE = 刪除

### Http response

[HTTP responses](https://www.ibm.com/docs/en/cics-ts/5.3?topic=protocol-http-responses)

### **Http response code**

[HTTP response status codes - HTTP | MDN](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status)

**1xx ：稍等**

- 100 Continue：Server 成功接收、但 Client 還要進行一些處理。

**2xx：成功**

- 200 OK：成功
- 204 No Content：成功但沒有回傳的內容（當你發出 Delete 的 request）

**3xx：重新導向，用戶端瀏覽器必須採取更多動作才能完成要求。**

- 301 Moved Permanently：資源「永久」移到其他位置，再下一次發出 request 時，瀏覽器直接到新位置。
- 302 Found（Moved Temporarily）：資源「暫時」移到其他位置。
- 304 Not Modified：東西跟之前長一樣，可以從快取拿就好。

**4xx：Client 端錯誤**

- 400 Bad Request：請求語法錯誤、或資源太大…等等。
- 401 Unauthorized：未認證，可能需要登入或 Token。
- 403 Forbidden：沒有權限。
- 404 Not Found：找不到資源。

**5xx：Service 端錯誤**

- 500 Internal Server Error：伺服器出錯，搶票時很可能發生。
- 501 Not Implemented
- 502 Bad Gateway：通常是伺服器的某個服務沒有正確執行。

### **header**

- 大部分會包含：
    1. IP 位置
    2. Http Request Method 狀態碼
    3. Http status code 請求方法
- 其他額外資訊也會放在這裡，例如：Client-ID、User-Agent、Authorization 等。＃在 API 串接時會使用到。

### **body**

- 主要傳遞的內容，但也有可以沒有內容。
