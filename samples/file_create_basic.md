---
layout: samples
title: File Create
icon: fa-caret-right
group: simple
---

File Create
===

Develop
--

1. Create a new project and name it **file_create_basic**.
2. Select the *ScriptingServices* sub-folder of the project and open the pop-up menu.
3. Choose *New* -> *Scripting Service*.
4. Choose **Server-Side JavaScript Service** from the list of available templates.
5. Give it a meaningful name (e.g **file_create_basic.js**).
6. Replace the generated code in **file_create_basic .js** with the following:

```javascript

	/* globals $ */
	/* eslint-env node, dirigible */

	var files = require('io/files');
	var response = require('net/http/response');

	files.createDirectory("../temp/test1");
	var file = files.get("../temp/test1");
	response.println("[File Exists?]: " + file.exists());
	response.println("[File Is Directory?]: " + file.isDirectory());

	files.createFile("../temp/test1/test1.txt");
	file = files.get("../temp/test1/test1.txt");
	response.println("[File Exists?]: " + file.exists());
	response.println("[File Is File?]: " + file.isFile());

	response.flush();
	response.close();

```

<div class="btn-toolbar pull-right">
	<a class="btn btn-warning" href="http://dirigible.eclipse.org/services/ui/anonymous.html?git=https://github.com/dirigiblelabs/sample_io_file_create_basic.git">Run</a>
	<a class="btn btn-info" href="http://www.dirigible.io/api/file.html">API</a>
</div>

Discover
--
To discover all available services, you can go to the [Registry](../help/registry.html).

1. From the main menu, choose **Window** -> **Show Perspective** -> **Registry**.
2. The **Registry** perspective represents a view to the enabled runtime content. From its menu, choose **Discover** -> **JavaScript** to open the currently available server-side JavaScript service endpoints.
3. You can see the list of available endpoints, where you can find yours by naming convention: **{project}/{service path}**
