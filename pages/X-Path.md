- XPath (XML Path Language) is a query language for selecting nodes from an XML document. When working with web pages in HTML, XPath can be used to find elements based on various attributes.
- #X-path #Automation #Testing
- [[draws/2024-05-18-21-42-45.excalidraw]]
- By Id:
	- ```html
	   <div id="content">This is the content</div>
	  ```
	- ```
	  //*[@id='content']
	  ```
- By Unique Name:
	- ```htmlembedded
	  <div name="content">This is the content</div>
	  ```
	- ```
	  //*[@name='content']
	  ```
- By Unique Value:
	- ```htmlembedded
	  <div uniquevalue="content">This is the content</div>
	  ```
	- ```
	  //*[@uniquevalue='content']
	  ```
- By combining two attributes
	- ```htmlembedded
	  <div id="content" uniquevalue="content">This is the content</div>
	  ```
	- ```
	  //*[@id='content' and @uniquevalue='content']
	  ```
- Find By text:
	- ```htmlembedded
	  <div>This is the content</div>
	  ```
	- ```
	  //div[text()='This is the content']
	  			or
	  //div[contains(text(), 'content')]
	  ```
- Find By Child:
	- ```htmlembedded
	  <section id="parent">
	          <article class="child">Child 1</article>
	          <article class="child">Child 2</article>
	          <article class="child">Child 3</article>
	  </section>
	  ```
	- ```
	  //article[@class='child']/..
	  		or
	  //section[article[@class='child']]
	  ```
- Find By parent
	- ```htmlembedded
	  <ul id="menu">
	          <li class="item">Item 1</li>
	          <li class="item">Item 2</li>
	          <li class="item">Item 3</li>
	  </ul>
	  ```
	- ```
	  //ul[@id='menu']/li[@class='item']
	  		or
	  //ul[@id='menu']/*
	  ```
- Starts-with:
	- ```htmlembedded
	  <div id="section1">Section 1</div>
	  <div id="section2">Section 2</div>
	  <div id="section3">Section 3</div>
	  ```
	- ```
	  //div[starts-with(@id, 'section')]
	  ```
- Last:
	- ```htmlembedded
	  <ul>
	          <li>Item 1</li>
	          <li>Item 2</li>
	          <li>Item 3</li>
	  </ul>
	  ```
	- ```
	  //ul/li[last()]
	  ```
- Count
	- ```htmlembedded
	  <ul>
	          <li>Item 1</li>
	          <li>Item 2</li>
	          <li>Item 3</li>
	   </ul>
	  ```
	- ```
	  count(//ul/li)
	  ```
- normalize-space
	- ```htmlembedded
	  <div class="text">
	          <p>   This is    a  sample    paragraph.   </p>
	          <p>   This is another   paragraph.   </p>
	  </div>
	  ```
	- ```
	  count(//div[@class='text']/p[normalize-space()])
	  ```
- **translate**
	- ```htmlembedded
	   <p>This is an example paragraph with some characters to be replaced.</p>
	  ```
	- ```
	  translate(//p/text(), 'e', 'E')
	  This XPath expression will replace all occurrences of the letter "e" with "E" in the text content of the paragraph.
	  ```
- string-length
	- ```htmlembedded
	  <p>This is an example paragraph with some text.</p>
	  ```
	- ```
	  string-length(//p/text())
	  ```
- round/floor
	- ```htmlembedded
	  <div id="numbers">
	          <span class="value">3.7</span>
	          <span class="value">5.2</span>
	          <span class="value">9.8</span>
	  </div>
	  ```
	- ```
	  //span[@class='value']/round(text())
	  		or
	  //span[@class='value']/floor(text())
	  
	  ```
- Not:
	- ```htmlembedded
	  <input type="checkbox" id="checkbox1" checked="checked">
	  <input type="checkbox" id="checkbox2">
	  ```
	- ```
	  //input[not(@checked)]
	  ```
- substring-after/substring-before
	- ```htmlembedded
	   <p>This is an example paragraph with some text.</p>
	  ```
	- ```
	  substring-before(//p/text(), ' example')
	  			or
	  substring-after(//p/text(), 'example ')
	  //This XPath expression will return the substring before/after the phrase " example" in the text content of the paragraph.
	  ```
	-