# Build Server and Automation

Github Actions is currently in charge of:

* Firmware Builds: continuous integration publishing at [https://gerefi.com/build_server/](https://gerefi.com/build_server/)
* Console Builds
* Simulator Builds
* Android App Builds
* TS Plugin Builds
* Generating configs
* Running Unit Tests
* Generating Coverity code coverage pages
* Generating Doxygen documentation
* Generating iBOMs for hardware
* Uploading .ini files into gerEFI Online database using GEREFI_SSH_USER
* Generating Hardware PCB visual diffs
* Updating date stamps for builds
* Synchronizing between gerefi/gerefi/wiki to gerefi_documentation repo
  * TL,DR see https://github.com/gerefi/gerefi/tree/master/.github/workflows

## Self-hosted runners

https://github.com/gerefi/gerefi/wiki/Dev-Quality-Control#hardware-continuous-integration

See also [Software-Development-Life-Cycle](Process-Software-Development-Life-Cycle-SDLC)

[Build-Server-and-Automation-Legacy-Jenkins-notes](Build-Server-and-Automation-Legacy-Jenkins-notes)
