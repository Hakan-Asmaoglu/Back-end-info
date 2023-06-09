<h1>This repo is for shortly informing my team members about our first year school project<h1>

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
    <pre>
        <p>Example:</p>
        <code>
            let jsonString = '{ "name": "apple", "color": "red" }';
        </code>
        <code>
            let jsonObject = JSON.parse(jsonString);
        </code>
        <code>
            console.log(jsonObject.name); // output: "apple"
        </code>
    </pre>
</p>
<br>
<p>
    <b>JSON.parse() method</b>
    <p>Converts a JSON string into a JavaScript object.</p>
    <pre>
        <p>Example:</p>
        <code>
            let jsonObject = { name: "apple", color: "red" };
        </code>
        <code>
            let jsonString = JSON.stringify(jsonObject);
        </code>
        <code>
            console.log(jsonString); // output: '{ "name": "apple", "color": "red" }'
        </code>
    </pre>
</p>
<br>
<b>JSON.parse() with a reviver function:</b>
<br>
<br>
<p>This method allows you to customize how the JSON string is parsed and converted into a JavaScript object. You can pass a reviver function as the second argument to JSON.parse(), and it will be called for each key-value pair in the JSON string. The function can modify the value or even delete it by returning undefined. Here's an example:</p>
<p>
    <pre>
        <p>Example:</p>
        <code>
            let jsonString = '{ "name": "apple", "color": "red" }';
        </code>
        <code>
            let jsonObject = JSON.parse(jsonString, (key, value) => {
                if (key === 'color') {
                    return 'green';
                }
                return value;
            });
        </code>
        <code>
            console.log(jsonObject.color); // output: "green"
        </code>
    </pre>
</p>
<br>
<b>JSON.stringify() with a replacer function:</b>
<br>
<br>
<p>This method allows you to customize how the JavaScript object is converted into a JSON string. You can pass a replacer function as the second argument to JSON.stringify(), and it will be called for each key-value pair in the object. The function can modify the value or even delete it by returning undefined. Here's an example:</p>
<p>
    <pre>
        <p>Example:</p>
        <code>
            let jsonObject = { name: "apple", color: "red" };
        </code>
        <code>
            let jsonString = JSON.stringify(jsonObject, (key, value) => {
                if (key === 'color') {
                    return undefined;
                }
                return value;
            });
        </code>
        <code>
            console.log(jsonString); // output: '{ "name": "apple" }'
        </code>
    </pre>
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
            <li> <b>req.path :</b> A string containing the path part of the request URL.</li>
            <li> <b>req.method :</b> The HTTP method of the request (e.g. GET, POST, etc.).</li>
            <li> <b>req.protocol :</b> The protocol of the request (e.g. HTTP or HTTPS)..</li> 
            <li> <b>req.route :</b> The current route object that was matched by the request.</li> 
            <li>And much more...</li>
        </ul>
        <li> <b>Response object</b>
            <p>The response object is used by the server to send a response back to the client. The response typically contains an HTTP status code, headers, and any data being sent in the response body. The status code indicates whether the request was successful or not, and the data in the response body can contain any information that the server wants to send back to the client.</p>
            <p>Here are common response objects in Express.js</p>
            <ul>
                <li> <b>res.send() :</b> Sends a response of various types, such as a string, object, or array.</li>
                <li> <b>res.json() :</b> Sends a JSON response.</li>
                <li> <b>res.sendFile() :</b> Sends a file as an attachment or a download.</li>
                <li> <b>res.redirect() :</b> Redirects the client to a different URL..</li>
                <li> <b>res.status() :</b> Sets the HTTP status code for the response.</li>
                <li> <b>res.cookie() :</b> Sets a cookie in the response.</li>
                <li> <b>res.clearCookie() :</b> Clears a cookie from the response.</li>
                <li> <b>res.setHeader():</b> Sets an HTTP header for the response.</li>
                <li> <b>res.format() :</b> Formats the response based on the content type requested by the client.</li>
                <li> <b>res.render() :</b> Renders a view template with data and sends the HTML as a response.</li>
                <li>And much more...</li>
</ul>
<br>
<h2>Express sessions</h2>
<br>
<ul>
    <li>
    <p>Express session is a tool used in web applications to store user information. For example, when a user logs into a website, we can use Express session to store the user's identity information (username, password, etc.) and user page settings. This way, as the user navigates through the website, session information is stored and the user's interactions on the website continue. In this way, users do not have to log in again each time they move from one page to another.</p>
    </li>
    <li><p>The info here is limited. I strongly suggest the 9th video to get deeper understanding of Express sessions: <a href="https://www.youtube.com/watch?v=39znK--Yo1o&list=PL_cUvD4qzbkwp6pxx27pqgohrsP8v1Wj2">Express.js tutorial.</a> This tutorial also contains many other things that we will need to use. </p></li>
</ul>
<br>
<h2>Postman desktop app</h2>
<br>
<ul>
    <li>
        <p>Postman is a versatile tool that we can use to improve our shop's functionality, performance, and reliability. By using Postman, we can streamline our testing process and ensure that our shop is running smoothly.</p>
        <ul>
            <li>
                <p><b>What we can do with postman? Here are some examples:</b></p>
                <br>
                <b>With postman we can:</b>
                <p> <b>Test our checkout process:</b> We can simulate the login process by sending test orders to our backend system. This helps us identify any issues or errors in the process and make sure everything is working correctly.</p>
                <p> <b>Monitor our inventory:</b> We can use Postman to check our numbers of items in our inventory. We can do this even periodically, in other words if we would make a real e-commerce shop we could check the amount of items in stock and we would never have the risk of stockouts.</p>
                <p> <b>Integration testing:</b> If we have integrated our e-commerce shop with other systems or APIs, we can use Postman to test the integration and ensure that everything is working correctly.</p>
                <p> <b>Automation testing:</b> We can use Postman to automate our testing process by creating scripts that automatically test different aspects of our shop, such as the search function, shopping cart, etc.</p>
                <p> <b>Load testing:</b> Postman can help us simulate high traffic loads on our e-commerce shop by sending multiple requests simultaneously. So if we would make a real e-commerce shop we would identify any performance issues and optimize our system for high traffic.</p>
            </li>
        </ul>
    </li>
    <li>
        <p>In summary, Postman is a versatile tool that we can use to improve our shop's functionality, performance, and reliability. By using Postman, we can streamline our testing process and ensure that our shop is running smoothly.</p>
        <p>Here is our team <a href="https://app.getpostman.com/join-team?invite_code=543ca6d41d84a23790f96ca479d8703e&target_code=3b48e90c0bdbc094cde86bcc6e82e710">link</a> </p>
    </li>
</ul>
<br>
<h2>JS promises, Async functions, Sync functions, Async Await statement, Try catch statement, Callback hell</h2>
<br>
<p>Just watch <a href="https://www.youtube.com/watch?v=ZYb_ZU8LNxs">this</a> you will have a general understanding of all.</p>
<br>
<h2>Module export in js</h2>
<br>
<ul>
    <li>
        <p>Module export feature allows us to define reusable code in one file and use it in another file. The code you want to make available to other files is exported using the "module.exports" or "exports" object.</p>
        <pre>
            <p>Example:</p>
            <p>The file "myModule.js" that we want to export:</p>
            <code>
                const myModule = () => {
                    console.log("Hello World");
                }
                module.exports = myModule;
            </code>
            <p>The file "index.js" that we want to import the module:</p>
            <code>
                const myModule = require("./myModule");
                myModule(); //output is "Hello,world"
            </code>
        </pre>
    </li>
</ul>
