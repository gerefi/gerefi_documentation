# HOWTO Contribute to Firmware

The majority of gerEFI code is written in very plain C++ ("C with classes"),
with gerEFI console and some code generating tools written in java.

Most of the needs are within the C/C++ firmware and automated testing.

A good first contribution could be adding some automated testing into [https://github.com/gerefi/gerefi/tree/master/unit_tests/tests](https://github.com/gerefi/gerefi/tree/master/unit_tests/tests)

For current coverage report see [https://gerefi.com/docs/unit_tests_coverage/](https://gerefi.com/docs/unit_tests_coverage/)

Doxygen source code documentation is found [here.](https://gerefi.com/docs/html/)

Primary tool-chain is GCC+Eclipse but IAR is also supported.

Linux is the preferred build environment, Windows Subsystem for Linux (WSL) works fine.
To setup development environment use [setup_linux_environment.sh](https://github.com/gerefi/gerefi/blob/master/firmware/setup_linux_environment.sh)

Testing coverage open tickets: [https://github.com/gerefi/gerefi/labels/automated_testing](https://github.com/gerefi/gerefi/labels/automated_testing)

All open tickets: [https://github.com/gerefi/gerefi/issues](https://github.com/gerefi/gerefi/issues)

[Click here for a Q&A on source code.](http://gerefi.com/forum/viewtopic.php?f=5&t=10)

[Some random tips](Dev-Tips)
