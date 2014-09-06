spark
=====

Firmata for [Spark](https://www.spark.io/)

##Install (Web IDE)
* Go to Spark Web IDE https://spark.io/build
* Create a new sketch and copy in examples/StandardFirmata/StandardFirmata.ino
* Click the plus button in the upper right corner to add the Firmata.h, Firmata.cpp, and Boards.h
* Click the Flash lightning bolt in the upper left corner.

##Install (Spark CLI tools)
* Download core-firmware.bin from this repo's release folder
* Log in to https://www.spark.io/build
* Click cores in the bottom left corner
* In the white box that slides out, find the name of your spark and click the down arrow to reveal the core id
* Make sure your core is connected and updated and breathing Cyan. See http://docs.spark.io/ for more info
* Install the spark command line tools npm install -g spark-cli
* Login with spark cloud login
* Flash the firmware spark cloud flash YOURCOREIDHERE core-firmware.bin

##Install (Arm Toolchain - HARD)
* Follow the directions at the Spark github page to get your toolchain set up. https://github.com/spark/core-firmware
* Make sure you can burn their Tinker example successfully.
* From this repo add .h files to your /inc dir and .cpp files to your /src directory
* From this repo copy examples/StandardFirmata/StandardFirmata.ino over your /src/application.cpp file
* Add ```CPPSRC += $(TARGET_SRC_PATH)/Firmata.cpp``` to your /src/build.mk file
* Build just like you learned in the Spark tutorial

##TODO
* spark.json support so we're in the Spark Web IDE libraries listing! https://github.com/spark/uber-library-example/issues
* Service agnostic examples that tunnel through mqtt, websockets etc like Octoblu https://github.com/jacobrosenthal/core-firmware/tree/skynet-mqtt-firmata/src

##Gotchas
* Requires Spark 0.3.3 As of this writing, you need to update your core from ARM toolchain, but the fix should be out in a release shortly. https://github.com/spark/core-firmware/compare/feature/release3.3 There are 2 bugs fixed. First, there was a bug in Spark prior to that which swapped input and output enums meaning you have to set input when you mean output, and reverse https://github.com/spark/core-firmware/issues/282 There was another bug which didnt set pins high for values other than 1 (ie setting digitalWrite(pin,2) works in arduino, but previously didnt in spark. Firmata uses this 'feature')  https://github.com/spark/core-firmware/issues/247