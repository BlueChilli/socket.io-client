# socket.io-client

## Install

### This library uses lstdc++!!
To compile you have to add a reference to the linker. 
To do so edit platform.txt in $ARDUINO_IDE/hardware/esp8266com/esp8266 and add '-lstdc++' to the line 
```
compiler.c.elf.libs= ...
```
(see http://stackoverflow.com/questions/33450946/esp8266-for-arduino-ide-xtensa-lx106-elf-gcc-and-stdmap-linking-error)

Best thing is to use the Arduino Library Manager.
* Go to Sketch > Include Library > Manage Libraries.
* Install WebSockets by Markus Sattler
* Install SocketIoClient
* Select Sketch > Include Library > SocketIoClient

## Functions

### SocketIoClient#begin
open connection to socket.io server.
##### Example
```c
socket.begin("my.socket-io.server")
```

### SocketIoClient#on
binds a function to an event. Function signature must be
```c
void (uint8_t * payload, size_t length)
```
##### Example
```c
void event(uint8_t * payload, size_t length) {
	//do stuff
}
socket.on("event", event)
```

##  Example
see [Example](examples/BasicExample/BasicExample.ino)

## contribution
Based on the great work of [Links2004 / arduinoWebSockets](https://github.com/Links2004/arduinoWebSockets).
