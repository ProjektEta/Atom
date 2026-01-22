# Atom

A Heartbeat based Client Sided Anti-Exploit.

## How does it work?

Every 6 Seconds; using Pseudo random number generator, the Server and Client generate 2 numbers; The Server number is kept on the server, while the client is sent to the server to verify.

During this, if at any point the numbers are different it will Kick the player for trying to spoof the heartbeat.

The Heartbeat has a timelimit, if the client fails to send any data within 5 seconds; They are automatically kicked.

This makes sure that the RemoteFunction cant be hooked; and makes sure the Exploiter cant just delete the LocalScript.

There is a second feature to this though; The Client and Server will get connected to an object (in this demo its the Humanoid).

Whenever a change is detected client sided only; The Client will then generate a number, then invoke the server with the Instance, Name of the property and the value it was changed to; to the server.

The Server will then generate a number, if the Property on the Instance is different on the server, it will kick the player for exploiting; it will also send back its code.

This will also update a timer, that could be used on the server to detect if the player has disabled the properties change detector.

On the client if the two codes are different; the player will fire a wrong heartbeat.

The Server will also be connected to the same object, whenever anything changes server side; the Server will wait 2 seconds. if the Client has not sent a check in that timeframe, they get kicked for spoofing.
