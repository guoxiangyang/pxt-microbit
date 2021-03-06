# Bluetooth UART Service 

### ~hint
![](/static/bluetooth/Bluetooth_SIG.png)

For another device like a smartphone to use any of the Bluetooth "services" which the micro:bit has, it must first be [paired with the micro:bit](/reference/bluetooth/bluetooth-pairing). Once paired, the other device may connect to the micro:bit and exchange data relating to many of the micro:bit's features.

### ~

The Bluetooth UART service allows another device such as a smartphone to exchange any data it wants to with the micro:bit, in small chunks which are intended to be joined together. [UART[(https://en.wikipedia.org/wiki/Universal_asynchronous_receiver/transmitter) stands for Universal Asynchronous Receiver Transmitter and is one way in which serial data communications can be performed, usually between two devices connected by a physical, wired connection. The Bluetooth UART service emulates the behaviour of a physical UART system and allows the exchange of a maximum of 20 bytes of data at a time in either direction. 

When this service is used, the micro:bit sets up a 60 byte buffer and data it receives will be accumulated in the buffer until it is full. When using the UART service from your micro:bit code, you can indicate a special character which will be used to mean that the entire message in at most three chunks has now been sent by the other, connected device, at which point the micro:bit will release the entire contents of its buffer to any code trying to read it. In other words this special character, known as a 'delimiter' is used by the device connected to the micro:bit to mean "I've sent my whole message, you can now use it".

You could use the UART service for many things. It doesn't care what you put in messages which makes it very flexible. You could create a guessing game, with questions and answers passing between micro:bit and a smartphone or you could connect a camera to the micro:bit and transmit image data obtained from the edge connector, in chunks over Bluetooth to a smartphone. There are a great many possibilities. 

To use the Bluetooth UART service from another device you'll need additional micro:bit code which reads and uses data from the UART buffer and / or writes data to the buffer for transmission over Bluetooth to another device.

```sig
bluetooth.startUartService();
```

### Example: Starting the Bluetooth UART service

The following code shows the Bluetooth UART service being started:

```blocks
bluetooth.startUartService();
```

### Video - UART service guessing game

https://www.youtube.com/watch?v=PgGeWddMAZ0

### Advanced
 
For more advanced information on the micro:bit Bluetooth UART service including information on using a smartphone, see the [Lancaster University micro:bit runtime technical documentation](http://lancaster-university.github.io/microbit-docs/ble/uart-service/)

### See also

[Bluetooth SIG](https://www.bluetooth.com), [Bluetooth on micro:bit resources](http://bluetooth-mdw.blogspot.co.uk/p/bbc-microbit.html)

```package
microbit-bluetooth
```
