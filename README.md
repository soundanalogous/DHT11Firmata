DHT11Firmata
============

This library is a test for a proposal to implement device-specific Firmata
features outside of the main Firmata repository. See [issue #132](https://github.com/firmata/arduino/issues/132) on github for
info on the reason for this proposal.

*Note this repo will be deleted in the future so don't rely on it. It's only
for testing purposes until the proposal for Firmata device support is finalized
and a location for Firmata device libraries is decided upon.*

To run this example perform the following:

1. Update your core Firmata library to the `configurable` version. Clone Firmata and checkout the `configurable` branch or download one of the zip files for your verion of the Arduino IDE here: https://github.com/soundanalogous/DHT11Firmata/releases.
Follow the instructions for updating Firmata here: https://github.com/firmata/arduino#updating-firmata-in-the-arduino-ide.
2. Clone or download DHT11Firmata it into your Arduino/libraries/ directory (this is the libraries folder in your Arduino sketch directory, not the same library folder you copied Firmata into in step 1 above).

Then open either examples/DHT11Firmata or examples/ConfigurableFirmata.

Ideally you should copy ConfigurableFirmata into your Arduino sketch directory
and run it there since this is how ConfigurableFirmata is intended to be used (you would actually configure it for your needs then rename it).

One change I propose to make is moving all of the files that depend on Firmata
in the utility directory of firmata/arduino to the src directory (you only see
src if you run the release.sh script). This will prevent firmata device library
developers from needing to specificy the utility directory (`<utility/filename.h>`).
Only dependencies that do not reference Firmata will remain in utility (eg. Encoder, OneWire, StepperFirmata, etc).
