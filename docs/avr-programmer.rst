=====================
AVRDUDE + AVRISP mkII
=====================

Traditionally, AVRISP mkII hardware is used with ATMEL studio to program the ATMEL microcontrollers. But, the ATMEL studio software is hefty, and runs into around 800MB. If we are using avr-gcc with Code::blocks IDE, installing a hefty software like this is not justifiable. Hence, the procedure, described here, attempts to use the AVRISP mkII hardware with a light weight open source AVRDUDE software.

==================== ======================
Operating System     Windows 10 Home x64
-------------------- ----------------------
Programming Hardware AVRISP mkII (Obsolete)
-------------------- ----------------------
Programming Software `AVRDUDE <http://savannah.nongnu.org/projects/avrdude>`_
-------------------- ----------------------
Interface            USB 
==================== ======================

AVRDUDE (*software*)
####################
AVRDUDE utility supports programming of AVR devices using a wide range of hardwares (including AVR ISP mkII) through in-system programming (ISP). It's command line driven interface enables aumation by including it in makefiles.

AVRISP mkII (*Hardware*)
########################
.. warning::

	The AVRISP mkII hardware is obsolete now.

AVRISP mkII progammer, from ATMEL, can program a range of ATMEL microcontrollers and it has USB interface for programming.

USB Drivers
###########
.. warning::

  - `Libusb-Win32 driver <https://boseji.com/post/installing-avrisp-mkii-with-libusb-win32-on-windows10/>`_
  - `Zadig <https://www.avrfreaks.net/forum/unable-connect-avrisp-mkii-avrdude>`_

  The above two drivers are found to be **not working** in Windows 10 x64.

The first challenge is to find and install a suitable USB driver for **AVRISP mkII** to be able to be used with the AVRDUDE. If the USB drivers are installed but not recognized by avrdude, then the following error message appears.

.. code-block:: batch

   `avrdude: usbdev_open(): did not find any USB device "usb" (0x03eb:0x2104)`

Working Solution
################
1) Install the olimex Driver

  - Download `olimex driver <https://www.olimex.com/Products/AVR/Programmers/AVR-ISP-MK2/resources/DRIVER-MK2-AS-6-7-W10.zip>`_.
  - Extract the zip file
  
2) Manually uninstall any existing AVR ISP Drivers and update to the new driver.
    
Basic Command Ref : (https://www.ladyada.net/learn/avr/avrdude.html)

Basic commands
##############

.. code-block:: bash

   avrdude -c <programmer> -p <partnumber> -P <interface> -U <memtype>:r|w|v:<filename>[:format]

=========== =====================================
programmer 	Specifies the programmer
----------- -------------------------------------
partnumber  AVR Partnumber
----------- -------------------------------------
interface   Programmer communication interface 
----------- -------------------------------------
memtype     flash, eeprom, hfuse, lfuse, or efuse
----------- -------------------------------------
r|w|v       Read/Write/Verify
----------- -------------------------------------
filename    name of the input or output file
----------- -------------------------------------
format      file format i for Intel Hex 
=========== =====================================

So the skeleton command becomes

.. code-block:: bash

   avrdude -c avrispmkII -p m2560 -P usb 

Terminal mode

.. code-block:: bash

    avrdude -c avrispmkII -p m2560 -P usb -t

Program **firmware.hex** to **flash memory**

.. code-block:: bash

    avrdude -c avrispmkII -p m2560 -P usb -U flash:w:firmware.hex:i

Program **memory.eep** to **EEPROM**

.. code-block:: batch

    avrdude -c avrispmkII -p m2560 -P usb -U eeprom:w:memory.eep
