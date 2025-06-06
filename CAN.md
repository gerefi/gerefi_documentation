# Overview of CAN usage and IDs used by gerEFI

Note: We support OBD2 pretty much exclusively for gauges/dashes/apps/etc, not real diagnosis!

* gerEFI WBO two way communication [0xEF50000](https://github.com/mck1117/wideband/blob/master/for_gerefi/wideband_can.h) 0x190
* gerEFI WBO bootloader
* gerEFI gauge broadcast 0x200 default base see [DBC](https://github.com/gerefi/gerefi/blob/master/firmware/controllers/can/gerEFI_CAN_verbose.dbc)
* gerEFI vehicle specific communication
* gerEFI ECU bootloader OpenBLT TX 667h, RX 7E1h
* gerEFI CAN GPIO
* gerEFI [TS over CAN](TS-over-CAN) 0x100 0x102
* gerEFI GDI comms [0xBB20 0xBB30](https://github.com/gerefi/libfirmware/blob/master/can/can_common.h)
* gerEFI bench test protocol 0x770000 base address

## 3rd party dashboards

![image](https://github.com/gerefi/gerefi/assets/48498823/65b93709-d959-473e-b406-a9dcbde64b3a)

![image](https://github.com/gerefi/gerefi/assets/48498823/56fba35f-44a1-4982-9242-762ee98e3590)

## OpenBLT

USB

``BootCommander.exe -s=xcp -t=xcp_rs232 -d=COM15 -b=19200 gerefi_update.srec``

PCAN

``BootCommander.exe -t=xcp_can -d=peak_pcanusb -c=0 -b=500000 -tid=1667h -rid=17E1h gerefi_update.srec``

## Software

[Man-in-the-middle](Man-in-the-middle)

## Hardware options

[PCAN-USB](https://www.peak-system.com/PCAN-USB.199.0.html?&L=1) with some cable [PCAN-Cable OBD-2](https://www.peak-system.com/PCAN-Cable-OBD-2.273.0.html?&L=1) or [PCAN-Cable 3](https://www.peak-system.com/PCAN-Cable-3.290.0.html?&L=1)

[fake looking like Vasya](https://gerefi.com/forum/viewtopic.php?f=13&t=2243)

[custom China](https://gerefi.com/forum/viewtopic.php?f=13&t=2209)

[Korlan instructions](https://gerefi.com/forum/viewtopic.php?p=43654#p43654)

FW images & legacy PCAN driver see <https://github.com/gerefi/gerefi_external_utils/tree/master/CAN>
