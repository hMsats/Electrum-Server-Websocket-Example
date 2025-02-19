# Electrum-Server-Websocket-Example
Example of how to connect to a public Bitcoin Electrum Server (Fulcrum) via Websockets (wss).

websocket.js:

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

It will output: "Connection opened" and show up on the Fulcrum server side as:

```
ID       IP:PORT                Typ  UAgent       ProtocolVer  Subs  HdrSub?  ReqRcv  RespSent  RecvBytes  SentBytes  TxsSent  Notifs  ErrorCt  Elapsed
4462488  <ip1>:49322        SSL  electrum/4.5.4   1.4          0     Y        5649    5649      418821     514796     0        118     0        22.44 hours
5535723  <ip2>:6653         SSL  electrum/4.5.3   1.4          0     Y        232     232       16934      11707      0        3       0        59.5 mins
5591372  <client ip>:33482  WSS  Unknown          1.4          0     N        0       0         0          0          0        0       0        52.1 secs
```
