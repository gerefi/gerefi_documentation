# Hardware

Unified gerEFI firmware runs on a wide array of boards with stm32f4 and stm32f7 microcontrollers.
We also have Kinetis and Cypress prototypes.

As of 2024 we are selling five universal ECUs. See [Mission-Statement](Mission-Statement)

[2024 universal hardware matrix](https://docs.google.com/spreadsheets/d/1HJYltK4RPDa0RIg4GWNU_2hYVAgdOU0GPiVdebtVTzo)

|   | Features | Connectors/Misc. Info | Released in | Maximum recommended engine |
| ----- | -------- | --------------------- | ----------- | ---------------------------|
| [Hellen One Platform](Hellen-One-Platform) | +knock detection<br/>+VR<br/>+Wideband Controller | Not an ECU, but a collection of modules that can be used to design an ECU. | 2020 | Board-specific |
| [Proteus](https://www.shop.gerefi.com/shop/p/spring-blade-cyy7n)| + gerEFI if you have lots of hardware or cylinders<br/>+ 4 layer PCB, 135mm x 82.5mm<br/>+ 16 low-side outputs, limited to 3 amps each (injectors, relays, check engine light, etc)<br/>+ 12x ignition outputs (or general purpose 5v, 100mA push-pull)<br/>+ Dual electronic throttles<br/>+ 4x High-side 12v drivers, 1 amp each<br/>+ 4 thermistor analog inputs (2.7k pull up resistor)<br/>+ 12 General purpose analog inputs<br/>+ Dual VR sensors (crank position, wheel speed)<br/>+knock detection<br/>+ 6 digital inputs (hall cam/crank position, wheel speed, clutch/brake switch, etc) | TE Ampseal connectors: 2x 35 pin, 1x 23 pin<br/>gerEFI's most fully-featured shield<br/>IP68 waterproof case | 2020 | 12 cylinder, dual electronic throttles |
| [microGerEFI](https://www.ebay.com/itm/333532119947) | + Available fully assembled!<br/>+ about 10 analog inputs<br/>+ One VR/Hall input channel for crank sensor<br/>+ One Hall input channel for crank sensor<br/>+ 4 injector output channels<br/>+ 4 logic level coil control channels (external igniters could be needed for some coils) | 48-pin connector<br/>On-board DBW<br/>USB, CAN<br/>open source hardware  | 2019 | 4 cylinder, single electronic throttle |

## Q: How to select a board?

A: History shows that fully assembled boards are the safest way to start. History shows
that 80% of the kits are never assembled. As of May 2022 we have microGerEFI and Proteus [in stock](https://shop.gerefi.com/). New fabrication of the assembled Frankenso board is
currently not planned.

## Q: What else matters?

A: Types and total count of crank and camshaft positions sensors is the next
important question. microGerEFI unfortunately only supports one VR shaft input maximum with two inputs total.

Frankenso supports up to 2 VR or 2 Hall shaft position sensors. Prometheus supports TBD. Proteus supports TBD.

## Q: why stm32?

A: [selecting-open-source-ecu-microcontroller](selecting-open-source-ecu-microcontroller)

## Q: This is all very cool but you guys do not have a Plug&Play for my Trabant. I think I will go and make a new gerEFI board just for my Trabant

A: At gerEFI we love cool new projects, but we are a really small team and only have so much time to work on gerEFI.  
We already have lots of different hardware configurations and we would suggest using one of the existing wire in versions.  
Nobody is stopping you from making your own board, but we cannot guarantee any support for that board or assistance with building it.  
If you proceed then please consider making a P&P adapter board design based on Hellen, [Proteus](https://github.com/mck1117/proteus/), or microGerEFI. See also https://github.com/gerefi/gerefi/wiki/Custom-Firmware

## Q: What EDA are you guys using for your open source hardware?

A: gerEFI preference at the moment is KiCad 7. A few legacy pieces are still using KiCad 4 and 5. While many EDAs have many cool features KiCad gives gerEFI uniformity and consistency.

See also [https://github.com/gerefi/gerefi/tree/master/hardware](https://github.com/gerefi/gerefi/tree/master/hardware)

## Q: What pin do I use for tachometer output?

A: There is no single right answer. It really depends on what kind of electrical signal is your tachometer expecting. Is it low-side driven? +5v logic signal driven? +12v logic signal driven?

## Q: What are these four status LEDs close to main processor?

A: Many gerEFI boards have four status LEDs. All four LEDs blink on start-up just to confirm life.

Blue Communication LED which is expected to blink at 50% duty cycle during normal board operation.
If USB communication cable is connected Blue LED starts to blink faster.

Red CRITICAL (previously known as FATAL) error means you have a CRITICAL error, engine operation is not possible with CRITICAL error.

Green LED on many gerEFI boards is RUNNING. Off if engine is stopped, blinks if engine is cranking, solid if engine is running.

## Q: what about many other LEDs which seem to be blinking in sync with injectors or coils?

A: Following Frankenso tradition, Injector LEDs are RED. Ignition LED are blue, power LED are green.

## Q: Why mini/micro/type C on MRE?

A: USB choice dictated by price and availability. If it changes MRE page will note.

## Q: Exiting, what soldering iron is best?

A: [FAQ Why No Self Assembly](FAQ-Why-No-Self-Assembly)

## Q: Why battery holder?

A: So that log file names could be current time stamp. That functionality is the only reason for battery holder, that functionality is broken for a couple of years now.

## Q: I would like to fabricate and sell on my country

A: See [Royalty](Royalty)
