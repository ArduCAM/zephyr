.. zephyr:code-sample:: video-mega_full-featured
   :name: Arducam mega camera full-featured sample

   Capture the video frames and transmit them to the PC software through
   the serial port.

Description
***********

This sample application caputre frames from a Arducam Mega camera and
transmits them over the UART to the connected PC software, enabling camera
control through the PC software.

Requirements
************

This samples requires a Arducam Mega camera and uart support.

- :ref:`rpi_pico`
- `Arducam Mega camera module`_

Wiring
******

On :ref:`rpi_pico`, The Arducam Mega camera module should be connected SPI0.
The PC should be connected to UART0 using a USB cable.

   .. note:: Be careful during connection!
    Use separate wires to connect SPI pins with pins on the rpi_pico board.
    Wiring connection is described in the table below.

    +-----------------+----------------+
    | Arducam Mega    | rpi_pico board |
    | camera Connector| SPI Connector  |
    +=================+================+
    |      VCC        |      VCC       |
    +-----------------+----------------+
    |      GND        |      GND       |
    +-----------------+----------------+
    |      SCK        |      P18       |
    +-----------------+----------------+
    |      MISO       |      P16       |
    +-----------------+----------------+
    |      MOSI       |      P19       |
    +-----------------+----------------+
    |      CS         |      P17       |
    +-----------------+----------------+

    For USB to UART cable, connect the rpi_pico board as below:

    +-------------+----------------+
    | USB to UART | rpi_pico board |
    | cable       | UART Connector |
    +=============+================+
    |     RX      |       P0       |
    +-------------+----------------+
    |     TX      |       P1       |
    +-------------+----------------+
    |     GND     |       GND      |
    +-------------+----------------+

Building and Running
********************

For :ref:`rpi_pico`, build this sample application with the following commands:

.. zephyr-app-commands::
   :zephyr-app: samples/subsys/video/mega_full-featured
   :board: pico
   :goals: build
   :compact:

Using UF2
---------

You can flash the Raspberry Pi Pico with a UF2 file. By default, building
an app for this board will generate a `build/zephyr/zephyr.uf2` file.
If the Pico is powered on with the `BOOTSEL` button pressed, it will appear
on the host as a mass storage device. The UF2 file should be drag-and-dropped
to the device, which will flash the Pico.

Sample Run
=============

You can refer to the `Arducam Mega camera module`_ website to install and use
the PC software to experience all the functions of the mega camera.

References
**********

.. _Arducam Mega camera module: https://www.arducam.com/camera-for-any-microcontroller/
.. _Arducam Mega GUI Guide: https://www.arducam.com/docs/arducam-mega/arducam-mega-getting-started/packs/GuiTool.html