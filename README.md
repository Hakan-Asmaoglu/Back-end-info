<h2>Routing</h2>
<p>Basically used for leading the user to wanted URL</p>
<br>
<p><b>As an example:</b></p>
<p>
  User clicks on "All cards" from the menu. In order to reach "All cards" page, the URL
  adress has to be ../blabla/allcards.html(<b>example</b>). But we
  do not want user to write it to browser. Instead, we route "All cards" in menu
  to that specific url.
</p>
<br>
<p>To do this with node.js, we need a framework such as express.js</p>
<br />
<p>
    First we need to install it via: <br>
    <p> <b>npm install express</b> </p>
</p> <br>
<p>
    Then we we import express to js file: <br>
    <p><b>const express = require("express")</b></p>
    <p><b>const app = express();</b></p>
</p><br>
<p>Then we will write the syntax to reach specific URL. After all URL will automatically change and "All cards" page will display.</p>
<br>
<h2>JSON methods</h2>
<p>JSON methods are important because they allow us to work with data in JSON format, which is a common way of exchanging data between web applications and services. When data is exchanged over the internet, it needs to be in a format that both the sending and receiving systems can understand. JSON is a lightweight and easy-to-read format that is widely supported by different programming languages.</p>
<br>
<p> <b>In our case we will use JSON to:</b>
    <ul>
        <li>Receive request from the user</li>
        <li>Send response to the user</li>
        <li>Receive data from the user</li>
        <li>Transfer data to browser</li>
    </ul>
</p>
<br>
<p><b>Types:
    <ul>
        <li>Object</li>
        <li>Array</li>
        <li>String</li>
        <li>Number</li>
        <li>Boolean</li>
        <li>Null</li>
    </ul>
</b></p>
<br>
<p>
    <b>Examples:</b>
    <p>
        <b>Object:</b> { "name":"John", "age":30, "car":null } <br>
        <b>Array:</b> ["Ford", "BMW", "Fiat"] <br>
        <b>String:</b> "John Doe" <br>
        <b>Number:</b> 123 <br> 
        <b>Boolean:</b> true <br>
        <b>Null:</b> null <br>
    </p>
</p>
<br>
<p>
    <b>JSON.stringfy() method</b>
    <p>Converts a JavaScript object or value to a JSON string.</p>
    <p> <b>Example:</b> </p>
    <p>let jsonString = '{ "name": "apple", "color": "red" }';</p>
    <p>let jsonObject = JSON.parse(jsonString);</p>
    <p><b>console.log(jsonObject.name); // output: "apple"</b></p>
</p>
<br>
<p>
    <b>JSON.parse() method</b>
    <p>Converts a JSON string into a JavaScript object.</p>
    <p> <b>Example:</b> </p>
    <p>let jsonObject = { name: "apple", color: "red" };</p>
    <p>let jsonString = JSON.stringify(jsonObject);</p>
    <p><b>console.log(jsonString); // output: '{ "name": "apple", "color": "red" }'</b></p>
</p>
<br>
<b>JSON.parse() with a reviver function:</b>
<br>
<br>
<p>This method allows you to customize how the JSON string is parsed and converted into a JavaScript object. You can pass a reviver function as the second argument to JSON.parse(), and it will be called for each key-value pair in the JSON string. The function can modify the value or even delete it by returning undefined. Here's an example:</p>
<p>
    <p>let jsonString = '{ "name": "apple", "color": "red" }';
    </p>
    <p>let jsonObject = JSON.parse(jsonString, (key, value) => {
        if (key === 'color') {
            return 'green';
        }
        return value;
    });</p>
    <p>console.log(jsonObject.color); // output: "green"</p>
</p>
<br>
<b>JSON.stringify() with a replacer function:</b>
<br>
<br>
<p>This method allows you to customize how the JavaScript object is converted into a JSON string. You can pass a replacer function as the second argument to JSON.stringify(), and it will be called for each key-value pair in the object. The function can modify the value or even delete it by returning undefined. Here's an example:</p>
<p>
    <p>let jsonObject = { name: "apple", color: "red" };
    </p>
    <p>let jsonString = JSON.stringify(jsonObject, (key, value) => {
        if (key === 'color') {
            return undefined;
        }
        return value;
    });</p>
    <p>console.log(jsonString); // output: '{ "name": "apple" }'</p>
</p>
<br>
<h2>Request and response objects</h2>
<br>
<ul>
    <li> <b>Request object</b> </li>     
        <p>The request object is used by the client (e.g. web browser) to send a request to the web server. The request typically contains information such as the URL being requested, HTTP headers, and any data being sent in the request body. The server then processes the request and generates a response.</p>
        <p>Here are common request objects in Express.js:</p>
        <ul>
            <li> <b>req.params :</b> An object containing properties mapped to the named route “parameters”.</li>
            <li> <b>req.query :</b> An object containing a property for each query string parameter in the route.</li>
            <li> <b>req.body :</b> An object containing a property for each body parameter in the route.</li>
            <li> <b>req.headers :</b> An object containing the request’s HTTP headers.</li>
            <li> <b>req.cookies :</b> An object containing the cookies sent by the request.</li>
            <li> <b>req.signedCookies :</b> An object containing the signed cookies sent by the request, unsigned and ready for use.</li>
            <li> <b>req.ip :</b> A string containing the remote IP address of the request.</li>
            <li> <b>req.ips :</b> An array of strings containing the remote IP addresses of the request.</li>
            <li> <b>req.path :</b> A string containing the path part of the request URL.</li>
            <li> <b>req.host :</b> A string containing the hostname derived from the Host HTTP header.</li>
            <li> <b>req.hostname :</b> A string containing the hostname derived from the Host HTTP header.</li>
            <li> <b>req.fresh :</b> A boolean property, “true” when the request is fresh, otherwise “false”.</li>
            <li> <b>req.stale :</b> A boolean property, “true” when the request is stale, otherwise “false”.</li>
            <li> <b>req.xhr :</b> A boolean property, “true” when the request’s X-Requested-With header field is “XMLHttpRequest”, otherwise “false”.</li>
            <li> <b>req.protocol :</b> A string containing the request protocol string: “http” or “https” when requested with TLS. When the “trust proxy” setting is enabled the “X-Forwarded-Proto” header field will be trusted and used.</li>
            <li> <b>req.secure :</b> A boolean property, “true” when the request is encrypted, otherwise “false”.</li>
            <li> <b>req.subdomains :</b> An array of subdomains.</li>
            <li> <b>req.accepts(types) :</b> Checks if the request’s Accept HTTP header field contains the specified content type(s). Returns the best match, or “false” if no match is found.</li>
            <li>And more</li>
        </ul>
</ul>
