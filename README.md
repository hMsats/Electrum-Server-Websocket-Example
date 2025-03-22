# Electrum-Server-Websocket-Example
Connect to a public electrum server via websockets.

&nbsp;

Info:

**Electrum server:** Fulcrum

**Coin:** bitcoin

**System:** Ubuntu linux

**Application:** nodejs

&nbsp;

Install:

    sudo apt install nodejs
    sudo apt install npm
    npm i ws

&nbsp;

Run:

    node websocket.js                       

If successful this will output: "Connection opened".

&nbsp;

The connection will show up on the (Fulcrum) server side as:

```
ID       IP:PORT                Typ  UAgent       ProtocolVer  Subs  HdrSub?  ReqRcv  RespSent  RecvBytes  SentBytes  TxsSent  Notifs  ErrorCt  Elapsed
4462488  <ip1>:49322        SSL  electrum/4.5.4   1.4          0     Y        5649    5649      418821     514796     0        118     0        22.44 hours
5535723  <ip2>:6653         SSL  electrum/4.5.3   1.4          0     Y        232     232       16934      11707      0        3       0        59.5 mins
5591372  <client ip>:33482  WSS  Unknown          1.4          0     N        0       0         0          0          0        0       0        52.1 secs
```
