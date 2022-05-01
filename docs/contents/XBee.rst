===========================================================
XBee/XBee-PRO Series 1
===========================================================

**XBee/XBee-PRO Series 1** devices are small form factor wireless modules based on IEEE 802.15.4-2003 standard for point-to-point and star communications. These are manufactured and marketed by Digi International Inc and the product family consists of several modules suppoting different application profiles such as DigiMesh, ZigBEE etc. This note attempts to explain the **XBee and XBee PRO Series 1 Legacy Devices** operating in 2.4 GHZ ISM band without any application profile and how they can be used as transparent serial communication device. 

.. warning::

	Currently, Series 1 devices have become *obsolete*.

-----------
Part Number
-----------

The series 1 XBee devices come with two different firmwares; 802.15.4 and DigiMesh 2.4. These are differentiated as follows,

+-------------+--------+----------+
|             |     Part Number   |
+-------------+--------+----------+
|  Firmware   | XBee   | XBee PRO | 
+=============+========+==========+
| 802.15.4    | XB24-A | XBP24-A  |
+-------------+--------+----------+
| DigiMesh 2.4| XB24-DM| XBP24-DM*| 
+-------------+--------+----------+

* Not covered here

--------------------------------
Firmware Hardware Compatibility
--------------------------------

Series 1 XBee devices come in two hardware versions; SiP (System in Package) and non-SiP. XBee modules shipped after December 2007, XBee PRO modules shipped after April 2008, Rev. B Module or Modules shipped with firmware version 1084, 10A5, 0r later have SiP Modules. 
	
All 802.15.4 firmware of version 10A5 or later is compatible with both Sip and Non-SiP Hardware vesions.
	
A SiP Module, if using 802.15.4 firmware, requires version 1084, 10A5, or later.
	
DigiMesh 2.4 firmware requires a module with SiP. Even though DigiMesh firmware may load successfully onto a non-SiP Module, it will not function correctly.

-------------
Antenna Types
-------------
Wire antennas offer omnidirectional signal. (When the antenna is straight, the maximum transmission distance is equal in all directions.)
The chip antenna is a flat ceramic chip. It takes up less space than the wire antenna, but the signal is not as omnidirectional as the wire antenna.
The U.FL connector is the smallest of the external antenna connectors. You can use the XBee without attaching an antenna to this connector, but if your project is inside a metal case, you will need to attach an antenna and make sure it pops out. If you don’t, the signal will be attenuated by the metallic case.

=============== ============= ===============
Type              XBee P/N     XBee-Pro P/N
=============== ============= ===============
Wire Antenna 	XB24-AWI-001	XBP24-AWI-001
PCB Antenna     XB24-API-001	XBP24-API-001
RPSMA Connector	XB24-ASI-001	XBP24-ASI-001
U.FL Connector	XB24-AUI-001	XBP24-AUI-001
=============== ============= ===============


Function 				   Command 		 Parameter
PAN ID 						ATID 			3001 (any address from 0 to FFFE will do)
MY Address 					ATMY 			1
Destination Address High 	ATDH 			0 (indicates a 16-bit address)
Destination Address Low 	ATDL 			2

Configuration Parameters
########################

PAN ID (**ID**)
	PAN stands for Personal Area Network. This is a unique identifier for your network. XBees assigned to a particular PAN ID can only communicate with each other. This lets you set up separate networks in the same location.

Source Address (**MY**)
	This is the source address for an XBee which can be arbitrarily set to a 16 bit number. This address is relevet for 16 bit addressing scheme. Each XBee should have unique address in a partcular network.
        
Destination address (**DH** & **DL**))
	This represents the address of the XBee that we want to talk to. There are two addressing modes; 16-Bit addressing and 64 Bit Addressing.
	
	**16 Bit addressing** : **DH** should be set to 0 and **DL** should match to the source address (**MY**) of the	
	destination XBee. When DH is set to zero, it is understood that the XBE operates in 16 bit Mode.  
	
	**64 Bit addressing** : Each XBee radio has a 64-bit unique serial number, which is used in 64-bit addressing. The **DH** & **DL** of each XBee should match with the **SH** and **SL** of the other XBee module.


Type in each command followed by its parameter and hit enter.
You can verify the setting by typing the command without a parameter.
Your settings aren’t saved yet! Type ATWR to save the settings.
Here’s how the terminal session will look, starting with the “+++” to enter command mode.

 .. code-block:: bash
 
	+++             OK
	ATID 3001       OK
	ATMY 1          OK
	ATDH 0          OK
	ATDL 2          OK
	ATID 3001		
	ATMY 1
	ATDH 0
	ATDL 2
	ATWR            OK
	+++             OK
	ATID 3001       OK
	ATMY 2	        OK
	ATDH 0	        OK
	ATDL 1	        OK
	ATID 3001       
	ATMY 2          
	ATDH 0          
	ATDL 1          
	ATWR 	        OK


.. note::

	You should get an OK response after issuing each command to set parameters, and another OK response when you write the changes to firmware. If you don’t get an OK response, most likely you took more than ten seconds to issue the command and you’ve dropped out of command mode. This can happen quite frequently when you’re starting out, but you’ll get better at it as you go along. The other common mistake is not issuing the ATWR command to save your changes, then losing your configuration when the radio is powered down. 

Function 	Command 	Parameter
PAN ID 	ATID 	3001 (any address from 0 to FFFE will do)
MY Address 	ATMY 	2
Destination address high 	ATDH 	0 (indicates a 16-bit address)
Destination address low 	ATDL 	1

    Remember to type ATWR and press enter to save the settings.

Here's what your terminal session might look like:




XBeePro 1   MASTER     1
XBeePro 2   CPGPod      2


.. note::

	Ensure that "Force the module to maintain its current configuration" option is **not selected** before downloading a new firmware. This helps to load the default settings in lieu of old settings after firmware update. 

Product Family 	: XBP24

Function Set	: XBEE PRO 802.15.4 and XBEE PRO 802.15.4 RS232 ADAPTER

Firmware		: 10ec, 10ef, 11e8 and someother versions may also work
				  
Working Configurations :
========================

Default settings
    ================================= ========== ==========
    Parameters                        **XBEE-1** **XBEE-2**
    ================================= ========== ==========
    Channel (**CH**)                  C          C
    PAN Identifier (**ID**)           3332       3332
    Destination Address High (**DH**) 0          0
    Destination Address Low (**DL**)  0          0
    Source Address (**MY**)           0          0
    Coordinator Enable (**CE**)       DON'TCARE  DON'TCARE 
    Serial number High (**SH**)       13A200     13A200
    Serial number Low  (**SL**)       40A08B8E   40988F8E
    Node Identifier	(**NI**)          NODE-1     NODE-2
    ================================= ========== ==========

16 Bit Addressing
    ================================= ========== ==========
    Parameters                        **XBEE-1** **XBEE-2**
    ================================= ========== ==========
    Channel (**CH**)                  C          C
    PAN Identifier (**ID**)           3332       3332
    Destination Address High (**DH**) 0          0
    Destination Address Low (**DL**)  1234       ABCD
    Source Address (**MY**)           ABCD       1234
    Coordinator Enable (**CE**)       DON'T CARE DON'T CARE 
    Serial number High (**SH**)       13A200     13A200
    Serial number Low  (**SL**)       40A08B8E   40988F8E
    Node Identifier	(**NI**)          NODE-1     NODE-2
    ================================= ========== ==========

64 Bit Addressing
    ================================= ========== ==========
    Parameters                        **XBEE-1** **XBEE-2**
    ================================= ========== ==========
    Channel (**CH**)                  C          C
    PAN Identifier (**ID**)           3332       3332
    Destination Address High (**DH**) 13A200     13A200
    Destination Address Low (**DL**)  40988F8E   40A08B8E
    Source Address (**MY**)           FFFF       FFFF
    Coordinator Enable (**CE**)       DON'T CARE DON'T CARE
    Serial number High (**SH**)       13A200     13A200
    Serial number Low  (**SL**)       40A08B8E   40988F8E
    Node Identifier	(**NI**)          NODE-1     NODE-2
    ================================= ========== ==========

