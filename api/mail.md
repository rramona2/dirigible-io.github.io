---
layout: api
title: Mail
icon: fa-check
---

Mail
===

Mail object is used to send e-mails through the mail service.

- Module: **api/mail**
- Definition: [/core_api/issues/12](https://github.com/dirigiblelabs/core_api/issues/12)
- Source: [/api/mail.js](https://github.com/dirigiblelabs/core_api/blob/master/core_api/ScriptingServices/api/mail.js)
- Status: **stable**

Basic Usage
---

```javascript
/* globals $ */
/* eslint-env node, dirigible */

var mail = require('api/mail');
var response = require('api/http/response');

var from = "dirigiblelabs@eclipse.org";
var to = "example@gmail.com";
var subject = "Subject";
var content = "Content";

mail.send(from, to, subject, content);

response.println("Mail sent");
response.flush();
response.close();
```