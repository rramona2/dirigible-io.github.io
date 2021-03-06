---
layout: api
title: HTTP Request
icon: fa-ellipsis-h
---

{{ page.title }}
===

HTTP Request object provided to the scripting services implementation. It contains the headers and parameters coming as input from the HTTP call.

- Module: **net/http/request**
- Definition: [/core_api/issues/4](https://github.com/dirigiblelabs/core_api/issues/4)
- Source: [/net/http/request.js](https://github.com/dirigiblelabs/core_api/blob/master/core_api/ScriptingServices/net/http/request.js)
- Status: **beta**

Basic Usage
---

```javascript
/* globals $ */
/* eslint-env node, dirigible */

var request = require('net/http/request');
var response = require('net/http/response');

var method = request.getMethod();

response.println("[Method]: " + method);
response.flush();
response.close();
```



Definition
---

### Functions

---

Function     | Description | Returns
------------ | ----------- | --------
**getMethod()**   | Returns the HTTP request method - GET, POST, PUT, DELETE | *string*
**getParameter(name)**   | Returns the value of the parameter by name, if any | *string*
**getParameterNames()**   | Returns the names of all the parameters | *array of string*
**getParameters()**   | Returns the all the parameters - name and value pairs | *array of pair*
**getAttribute(name)**   | Returns the value of the attribute by name, if any | *string*
**setAttribute(name,value)**   | Sets the value of the attribute by name | -
**getAttributeNames()**   | Returns the names of all the attribute | *array of string*
**getHeader(name)**   | Returns the value of the header by name, if any | *string*
**getHeaderNames()**   | Returns the names of all the headers | *array of string*
**getCookies()**   | Returns all the cookies from the request | *array of HttpCookie*
**isUserInRole(role)**   | Returns true if the user has the given role and false otherwise | *string*
**getInfo()**   | Returns the information about the request | *HttpRequestInfo*
**readInput()**   | Returns a byte array of the data from the request | *array of byte*
**readInputText()**   | Returns a string representation of the data from the request | *string*




### Objects

---

#### HttpCookie


Function     | Description | Returns
------------ | ----------- | --------
**name**   | The HttpCookie name | *string*
**value**   | The HttpCookie value | *string*
**comment**   | The HttpCookie comment section | *string*
**maxAge**   | The HttpCookie maximum age | *int*
**path**   | The URI path to which the client should return the HttpCookie | *string*
**domain**   | The domain name set to this HttpCookie | *string*
**secure**   | Returns true if the client is sending HttpCookie only over a secure protocol | *string*
**version**   | Returns the version of the protocol this cookie complies with | *0*
**httpOnly**   | The HttpCookie will not be exposed to the client-side scripting code if true | *boolean*


#### HttpRequestInfo


Function     | Description | Returns
------------ | ----------- | --------
**contextPath**   | Returns the context path from the URI | *string*
**pathInfo**   | Returns any extra path information from the URL | *string*
**protocol**   | Returns the protocol from the URL | *string*
**queryString**   | Returns the query string from the URL | *string*
**scheme**   | Returns the scheme from the URL | *string*
**serverName**   | Returns the server name from the URL | *string*
**serverPort**   | Returns the server port from the URL | *string*




Compatibility
---

Rhino | Nashorn | V8
----- | ------- | --------
 ✅  | ✅  | ❌


