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
<h2>Json</h2>
<p>Json is a format for storing and transporting data. It is often used when data is sent from a server to a web page.</p>
<br>
<p> <b>In our case we will use it to:</b>
    <ol>
        <li>Receive request from the user</li>
        <li>Send response to the user</li>
        <li>Receive data from the user</li>
        <li>Transfer data to browser</li>
    </ol>
</p>
<br>
<p><b>Types:
    <ol>
        <li>Object</li>
        <li>Array</li>
        <li>String</li>
        <li>Number</li>
        <li>Boolean</li>
        <li>Null</li>
    </ol>
</b></p>
<br>
<p>
    <b>Example:</b>
    <p>
        <b>Object:</b> { "name":"John", "age":30, "car":null } <br>
        <b>Array:</b> ["Ford", "BMW", "Fiat"] <br>
        <b>String:</b> "John Doe" <br>
        <b>Number:</b> 123 <br>
        <b>Boolean:</b> true <br>
        <b>Null:</b> null <br>
    </p>
</p>
