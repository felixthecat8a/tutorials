# Controlling an LED with SocketIO
<!-- Express & SocketIO -->
## Express & SocketIO
[***Express***](https://expressjs.com/) is a web application framework for Node.js that simplifies the process of defining routes, handling HTTP requests, managing middleware, and serving static files.

[***Socket.IO***](https://socket.io/) is a JavaScript library that enables real-time, bidirectional communication between web clients and servers. It allows for event-based communication, where the server can send data to connected clients and clients can also send data to the server.

This tutorial shows how to control an Arduino's LED in real-time from a browser using Socket.IO and Johnny-Five with Node.js.

## Set Up Your Project

Make a new project directory file:

```ps
mkdir SocketLED
cd SocketLED
yarn init -y
```
> The `-y` flag automatically accepts all default options for package.json.

Create an HTML file, a CSS file and a JavaScript file in a `public` folder for the front-end.
```ps
New-Item -Path .\public -ItemType Directory
New-Item -Path .\public\index.html -ItemType File
New-Item -Path .\public\style.css -ItemType File
New-Item -Path .\public\code.js -ItemType File
```
Create another JavaScript file in a `server` folder for the back-end.
```ps
New-Item -Path .\server -ItemType Directory
New-Item -Path .\server\server.js -ItemType File
```
Then install the required dependencies:

```bash
yarn add express socket.io johnny-five serialport
```
Or with NPM:

```bash
npm install express socket.io johnny-five serialport
```
After setup, your folder structure should look like this:
```
Project/
├── node_modules/
├── public/
│   ├── code.js
│   ├── index.html
│   └── style.css
├── server/
│   └── server.js
├── package.json
└── yarn.lock
or
└── package-lock.json
 ```
### Set Up the HTML Template
The HTML file will serve as the user interface for controlling an LED from a browser using Socket.IO.

#### Insert Boilerplate Code
1. Open index.html in your code editor.
2. Type ! and press Tab (in VS Code) to generate a full HTML boilerplate.

#### Link Your Stylesheet
Inside the `<head>` tag, under the `<title>`, add:
```html
<link rel="stylesheet" href="style.css">
```
> You can also embed styles directly using `<style> `tags inside the `<head>`.
- To add comments in your CSS use:
```css
/* comment */
```

#### Add the LED Control Interface
Inside the `<body>` tag, insert your LED control button and scripts:
- To add comments in HTML use:
```html
<!-- comment -->
```

Include your JavaScript file, code.js, at the bottom of the body.
```html
<script src="code.js"></script>
```


JavaScript supports both `// single-line` and `/* multi-line */` comments.

Add the Socket.IO client library script before your code runs.
```html
<script src="/socket.io/socket.io.js"></script>
```


```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>LED Control</title>

  <!-- Socket.IO Client -->
  <script src="/socket.io/socket.io.js"></script>

  <!-- External CSS -->
  <link rel="stylesheet" href="style.css">

  <style>
    /* Inline CSS styles (optional) */
  </style>
</head>
<body>
  <!-- LED Control UI -->
  <h1>LED Button</h1>
  <button id="buttonLED">LED is OFF</button>

  <!-- External JS -->
  <script src="code.js"></script>

  <script>
    // Inline JavaScript (optional)
  </script>
</body>
</html>
```




