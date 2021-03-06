---
layout: samples
title: Http Request Cookies
icon: fa-caret-right
group: simple
---

Http Request Cookies
===

Develop
--

1. Create a new project and name it **request_cookies_basic**.
2. Select the *ScriptingServices* sub-folder of the project and open the pop-up menu.
3. Choose *New* -> *Scripting Service*.
4. Choose **Server-Side JavaScript Service** from the list of available templates.
5. Give it a meaningful name (e.g **request_cookies_basic.js**).
6. Replace the generated code in **request_cookies_basic.js** with the following:

```javascript

	/* globals $ */
	/* eslint-env node, dirigible */

	var request = require('net/http/request');
	var response = require('net/http/response');

	var cookies = request.getCookies();

	response.println("[Cookies]: " + JSON.stringify(cookies));
	response.flush();
	response.close();
	
```

<div class="btn-toolbar pull-right">
	<a class="btn btn-warning" href="http://dirigible.eclipse.org/services/ui/anonymous.html?git=https://github.com/dirigiblelabs/sample_net_http_request_cookies_basic.git">Run</a>
	<a class="btn btn-info" href="http://www.dirigible.io/api/http_request.html">API</a>
</div>

Discover
--
To discover all available services, you can go to the [Registry](../help/registry.html).

1. From the main menu, choose **Window** -> **Show Perspective** -> **Registry**.
2. The **Registry** perspective represents a view to the enabled runtime content. From its menu, choose **Discover** -> **JavaScript** to open the currently available server-side JavaScript service endpoints.
3. You can see the list of available endpoints, where you can find yours by naming convention: **{project}/{service path}**
