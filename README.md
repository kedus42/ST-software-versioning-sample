# Version 0.3

**Predecessor** 

*The version of the crawler software from which this version is derived*

Version 0.2

**Supported electrical components**

*A list of the electrical components this version can succesfully interface with*

| Used in delivered crawler system | Possible exchanges |
| ----------- | ----------- |
| PNI prime digital compass (communication over serial port) |  NA    |
| CAN/USB adapter   | Any other adapter giving the compute module access to the CAN bus    |
| Micontrol motor controllers | Most other motor controllers from Micontrol which host the same object dictionary as |

**Differences from predecessor** 

*Changes made necessary by different hardware or features desired in the target crawler*

ic_driver no longer communicates to the motor controlers and compass through the Hofbauer ISM controller. Serial and TCP connections for this purpose have been removed.

ic_controller introduced to handle communications with motor controllers and compass.

ic_instr now toggles the motor relays based on input from the autonomy inhibit switch.

CANopendLinux used to start a service that receives commands from ic_controller and edits the object dictionary of the Micontrol microcontrollers.

**Introduced feature/quality updates**

*Updates that add features or improve the quality of the software functionality. All changes in this category must be introduced into all other affected versions*

| Update | Affected versions |
| ----------- | ----------- |
| Map frame added to all odometry info published from ic_driver |  0.1, 0.2    |

**Adopted feature/quality updates**

*Updates that add features or improve the quality of the software functionality. All feature/quality updates adopted from other versions belong here*

**Introduced security and safety updates**

*Updates added to patch security or safety issues. All changes in this category must be introduced into all other affected versions*

**Adopted security and safety updates**

*Updates added to patch security or safety issues. All security and safety updates adopted from other versions belong here*

