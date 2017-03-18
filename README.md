Firmata for Particle
====================

Firmata for [Particle](https://www.particle.io/)

##Install (Web IDE)
1. Go to [Particle Build Web IDE](https://build.particle.io/build).
2. Open the Libraries sidebar and search for "Firmata".
3. Add a reference to the library itself or use the StandardFirmata.ino example.
4. Click the Flash lightning bolt in the upper left corner.

##Install (Local Dev IDE)
1. Open the [Particle Dev IDE](https://www.particle.io/products/development-tools/particle-desktop-ide).
2. Open the libraries window by clicking on the libraries icon in the left sidebar.
3. Search for "Firmata".
4. Add a reference to the library by clicking "Use" and then "Copy to current project".
5. To install StandardFirmata find **StandardFirmata.ino** under lib/Firmata/examples/StandardFirmata and right-click on it and select **Flash Example OTA**.

##Install (Particle CLI tools)
1. Install the command line tools with `npm install -g particle-cli`.
2. Log in to your Particle account with `particle login`.
3. Create a new project using `particle project create` and follow the prompts.

To use Firmata in your project use `particle library add Firmata`. This will create a reference to the library but not copy the contents locally.

To get StandardFirmata on your device copy it to your project folder by running `particle library copy Firmata` followed by `particle flash [device name] lib/Firmata/examples/StandardFirmata`

##Install (Arm Toolchain - HARD)
* Follow the directions at the Spark github page to get your toolchain set up. https://github.com/spark/core-firmware
* Make sure you can burn their Tinker example successfully.
* From this repo add .h files to your /inc dir and .cpp files to your /src directory
* From this repo copy examples/StandardFirmata/StandardFirmata.ino over your /src/application.cpp file
* Add ```CPPSRC += $(TARGET_SRC_PATH)/Firmata.cpp``` to your /src/build.mk file
* Build just like you learned in the Spark tutorial

##TODO
* Service agnostic examples that tunnel through mqtt, websockets etc like Octoblu https://github.com/jacobrosenthal/core-firmware/tree/skynet-mqtt-firmata/src
