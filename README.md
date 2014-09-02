spark
=====

Firmata for [Spark](https://www.spark.io/)

To do: Update the following files to be Spark compatible:

- examples/StandardFirmata/StandardFirmata.ino
- Boards.h
- Firmata.cpp
- Firmata.h

Update this README file to describe the process of installing Firmata for spark-core.

Add any additional examples as necessary.


Other things to consider if supported by Spark:

- Increase serial buffer (currently 64 bytes)
- User a faster baud rate
- Remove Boards.h (unless it's anticipated that Spark may expand beyond a single board)
- Remove any functionality from StandardFirmata that is not supported by Spark
