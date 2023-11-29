Note
~~~~

wiringPi for Python
===================

wiringPi: An implementation of most of the Arduino Wiring functions for
the Banana Pi.

Supported boards
===================
tested on:
``Banana Pi M4 Berry``
``Banana Pi M4 Zero``

Manual Build
============

Get/setup repo
--------------

.. code:: bash

    git clone --recursive https://github.com/BigQubot/wiringPi-Python.git
    cd wiringPi-Python

Don't forget the --recursive; it is required to also pull in the WiringPi C code from its own repository.

Prerequisites
-------------

To rebuild the bindings you **must** first have installed ``swig``,
``python3-dev``, and ``python3-setuptools``. wiringPi should also be installed system-wide for access
to the ``gpio`` tool.

.. code:: bash

    sudo apt-get install swig python3-dev python3-setuptools

Build & install with
--------------------

``python3 generate-bindings.py > bindings.i``

``sudo python3 setup.py install``

Usage
=====

.. code:: python

    import wiringpi

    # One of the following MUST be called before using IO functions:
    wiringpi.wiringPiSetup()      # For sequential pin numbering

**General IO:**

.. code:: python

    wiringpi.pinMode(6, 1)       # Set pin 6 to 1 ( OUTPUT )
    wiringpi.digitalWrite(6, 1)  # Write 1 ( HIGH ) to pin 6
    wiringpi.digitalRead(6)      # Read pin 6
