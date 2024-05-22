# What is async and defer? #Javascript 
heading:: 1

Created: February 7, 2024 12:29 AM
Updated: February 7, 2024 12:30 AM
- **async:** When you include the async attribute in a script tag (), it means that the script will be executed asynchronously. Asynchronous scripts do not block the parsing of the HTML document. The script will be fetched in the background while the HTML parsing continues, and once the script is downloaded, it will be executed. This is useful when the script does not depend on the order of execution or when the script can be executed independently of the HTML structure.
- **defer:** When you include the defer attribute in a script tag (), it means that the script will be executed in order, after the HTML document has been fully parsed. Deferred scripts do not block the HTML parsing. They will be downloaded in the background, and execution will be delayed until the HTML parsing is complete. This is useful when the script depends on the order of elements in the HTML document, and you want to ensure that the script runs after the document is fully parsed.