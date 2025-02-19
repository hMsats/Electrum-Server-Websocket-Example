# Electrum-Server-Websocket-Example
Example of how to connect to an public Bitcoin Electrum Server (Fulcrum) via Websockets (wss):

```

// For the client:
// sudo apt install nodejs
// sudo apt install npm
// npm i ws
// Run on client as:
// node websocket.js

// For the server:
// sudo ufw allow 50003
// sudo ufw allow 50004
// On the modem:
// open port 50003
// open port 50004

const WebSocket = require('ws');
const socket = new WebSocket("wss://bitcoinserver.nl:50004");
//const socket = new WebSocket("ws://bitcoinserver.nl:50003");

// Connection opened
socket.addEventListener("open", () => {
  console.log("Connection opened");
});

socket.addEventListener("close", () => {
  console.log("Connection closed");
});

socket.addEventListener("error", e => {
  console.log("Error\n\n", e);
});

socket.addEventListener("message", function(event) {
  console.log("Message from server ", event.data);
});
```                                                    
