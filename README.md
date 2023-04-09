<h2>Routing</h2>
<hr>
<p>Basically used for leading the user to wanted URL</p>
<br>
<p><b>As an example:</b></p>
<p>
  User clicks on All cards from the menu. In order to reach All cards, the URL
  adress has to be ../Frames/allcards.html(<b>example</b>) in our case. But we
  do not want user to write it to browser Instead, we route "All cards" in menu
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
