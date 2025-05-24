# TunerStudio Over CAN

gerEFI TS communication could go over CAN wires. Definitely much slower than USB but should be much more noise tolerant!

As of today TunerStudio does not communicate with CAN dongles directly - so, we have a gerEFI own proxy software with ISO/TP on CAN dongle side, and TCP/IP for TunerStudio .

Step 1: have relevant hardware: PCAN for Windows or SocketCAN for Unix see <https://github.com/gerefi/gerefi/wiki/CAN#hardware-options>

Step 2: in bundle bin folder execute pcan_connector.bat or socketcan_connector.sh

Step 3: connect TS to localhost port 29001

Step 4: report results at <https://gerefi.com/forum/viewtopic.php?f=5&t=2233>
