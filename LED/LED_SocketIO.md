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




