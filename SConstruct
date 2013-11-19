# arscons: scons script for the Arduino sketch
# http://github.com/suapapa/arscons
#
# Copyright (C) 2010-2013 by Homin Lee <homin.lee@suapapa.net>
# Copyright (C) 2013 by Christian Fobel <christian@fobel.net>
#
# This program is free software; you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation; either version 3 of the License, or
# (at your option) any later version.
# You'll need the serial module: http://pypi.python.org/pypi/pyserial

# Basic Usage:
# 1. Make a directory which have same name of the sketch (ex. Blink/ for Blink.pde)
#   * Note that, as a convenience, if the sketch does _not_ have the same name
#     as the parent directory, compilation will still be performed if it is the
#     only file in the directory with the extension `.pde` or `.ino`
# 2. Put the sketch, `SConstruct` _(this file)_, and the directory `site_scons`
#   under the sketch directory.
# 3. To make the HEX. do following in the directory.
#     $ scons
# 4. To upload the binary, do following in the directory.
#     $ scons upload

# Thanks to:
# * Ovidiu Predescu <ovidiu@gmail.com> and Lee Pike <leepike@gmail.com>
#     for Mac port and bugfix.
# * Steven Ashley <steven@ashley.net.nz> for Windows port.
# * Kyle Gordon for many patches which including Arduino-1 support
#
# This script tries to determine the port to which you have an Arduino
# attached. If multiple USB serial devices are attached to your
# computer, you'll need to explicitly specify the port to use, like
# this:
#
# $ scons ARDUINO_PORT=/dev/ttyUSB0
#
# To add your own directory containing user libraries, pass EXTRA_LIB
# to scons, like this:
#
# $ scons EXTRA_LIB=<my-extra-library-dir>
from arduino_build import ArduinoBuildContext

context = ArduinoBuildContext(ARGUMENTS)

arduino_hex = context.build(register_upload=True)
