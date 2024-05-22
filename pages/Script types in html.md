# Script types in html #Javascript 
heading:: 1

Created: February 7, 2024 11:09 AM
Updated: February 7, 2024 11:13 AM

While the **script** tag in HTML primarily serves to embed JavaScript code, it can also handle several other scripting languages with the help of the **type** attribute. Here's an overview of common script types you can use:
- **type="text/javascript"** (default): This is the most commonly used type and the default behavior if you omit the **type** attribute. It embeds JavaScript code, which will be executed by the browser's JavaScript engine.
- **type="module"**: This type is used for modern JavaScript modules, introduced in ECMAScript 6 (ES6). Modules provide better code organization, encapsulation, and scoping compared to traditional script tags. Module scripts must be served with the correct MIME type (application/javascript; charset=utf-8).
- **type="text/babel"** (not standard): This type is not part of the HTML standard but is used by tools like Babel to transpile modern JavaScript code to versions compatible with older browsers. It allows you to write modern JavaScript while ensuring it works across supported browsers.
- **type="text/vbscript"** (deprecated): This type is used for VBScript, an older scripting language primarily used in Internet Explorer. Due to security concerns and limited support, its use is strongly discouraged.
- **type="text/template"** (non-standard): This type is not part of the HTML standard but used by templating engines like Handlebars or Mustache. It allows you to embed dynamic content within your HTML using template syntax.
  
  ---