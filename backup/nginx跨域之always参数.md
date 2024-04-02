nginx配置了Access-Control-Allow-Origin，服务端响应码200时，前端无跨域问题，响应非200时出现跨域问题。

原因：
Nginx只会在成功的响应（如200状态码）中添加额外的头信息，对于错误响应（如401、403等），这些头信息可能不会被添加。

要在所有响应中添加所需的跨域头，可以通过在Nginx的配置文件中使用always参数来实现，always参数确保无论响应代码如何，头信息都会被添加。如下：
```
location / {
    add_header 'Access-Control-Allow-Origin' '*' always;
    add_header 'Access-Control-Allow-Methods' 'GET, POST, OPTIONS' always;
    add_header 'Access-Control-Allow-Headers' 'DNT,X-CustomHeader,Keep-Alive,User-Agent,X-Requested-With,If-Modified-Since,Cache-Control,Content-Type,Authorization' always;
    if ($request_method = 'OPTIONS') {
        return 204;
    }
}
```

另外，要特别注意，使用\*作为Access-Control-Allow-Origin的值时，不能与Access-Control-Allow-Credentials为true一起使用，因为这违反了CORS策略。如果需要携带凭证（如Cookies），则必须指定明确的域名而不是\*。