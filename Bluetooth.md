# Obviously gerEFI supports Bluetooth

gerEFI console has commands for Bluetooth module initialization (see below), at the moment we do not have TunerStudio interface for Bluetooth module initialization.

## Reference Design

https://github.com/gerefi/alphax-4chan is the most popular open source board with on-board bluetooth.

## Isn't HC-06 Dead?

That's an open question see https://github.com/gerefi/gerefi/issues/6197

JDY-33 seems to be the way to go Bluetooth in 2023. Yes, gerEFI supports JDY-33 initialization. Yes, 4chan comes with JDY-33. 2024 update https://github.com/gerefi/gerefi/issues/5918 what a mess

## HC-06 Bluetooth Module serial RS232 TTL

On start, HC-06 accepts AT commands @ 9600.

the default pin is 1234

## JDY

``bluetooth_jdy 115200 alphax 1234``

Which is just one the possibilities

```
	// Usage:   "bluetooth_hc06 <baud> <name> <pincode>"
	// Example: "bluetooth_hc06 38400 gerefi 1234"

bluetooth_hc05 bluetooth_hc06 bluetooth_bk bluetooth_jdy

```

https://gerefi.com/forum/viewtopic.php?f=13&t=1999

## BluetoothView

A cool relevant Windows utility http://www.nirsoft.net
