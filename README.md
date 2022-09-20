# Version 0.3

**Predecessor** 

*The version of the crawler software from which this version is derived*

Version 0.2

**Supported electrical components**

*A list of the electrical components this version can succesfully interface with*

| Used in delivered crawler system | Possible alternatives |
| ----------- | ----------- |
| Conga PA-7 | Conga PA-5 |
| Micontrol mcDSA-E40 motor controllers | Other motor controllers from Micontrol which host the same object dictionary as the mcDSA-E40s |
| CPC-USB/embedded CAN adapter | Any other adapter giving the compute module access to the CAN bus |
| Labjack U12 | NA |
| PNI prime digital magnetic compass (serial connection) |  NA    |
| MS5837-30BA pressure sensor | NA |
| Falmouth OEM Scientific OEM CT sensor | NA |
| SCC30-DB humidity and temperature sensor | NA |
| PCF8574 Remote 8-Bit I/O Expander | NA |
| Subsea Li-Ion 50.4V PowerPack | All SubCtech batteries abiding by the SubCtech NMEA-0183 Data Protocol |

**Differences from predecessor** 

*Changes made necessary by different hardware or features desired in the target crawler*

ic_driver no longer communicates to the motor controlers and compass through the Hofbauer ISM controller. Serial and TCP connections for this purpose have been removed.

ic_controller introduced to replace the Hofbauer ISM controller and handle communications with motor controllers and compass.

ic_instr now toggles the motor relays based on input from the autonomy inhibit switch.

CANopendLinux used to start a service that receives commands from ic_controller and edits the object dictionary of the Micontrol motor controllers.

ic_lights node removed in favor of communicating the desired brightness level through analog signals between the labjack and the arduino. Signal now sent from ic_instr.

Track base, wheel radius and gearbox ratio used in converting m/s to rpms and vice versa changed to fit the host crawler.

Bus couplers, previously controlled by sending messages to the ISM, now controlled directly from ic_instr. Bus coupler state information published from ic_instr.

Hardware armed/disarmed state read directly from the Labjack by ic_instr.

CSDS (Crawler Sensor Data Stream) messages, NMEA format messages sent over TCP introduced to ic_driver. The messages contain sensor data previously only published as ROS2 messages and are now published on port 4000.

ROS2 subscriptions added to ic_driver in order to aquire sensor data from ic_instr before sending the data in NMEA format.

**Introduced feature/quality updates**

*Updates that add features or improve the quality of the software functionality. All changes in this category must be introduced into all other affected versions*

| Update | Affected versions |
| ----------- | ----------- |
| Ros2 transforms from map frame to odom frame added to ic_driver |  0.1, 0.2  |
| ic_driver blocked from attempting to send commands to motor controllers while the crawler is hardware disarmed | 0.2 |
| ic_controller now enables sending the motor controllers current setpoint via the /craler/curr_cmd topic | 0.2 |
| Battery percentage and presence fields in battery message now populated by ic_driver | 0.1 |

**Adopted feature/quality updates**

*Updates that add features or improve the quality of the software functionality. All feature/quality updates adopted from other versions belong here*

**Introduced security and safety updates**

*Updates added to patch security or safety issues. All changes in this category must be introduced into all other affected versions*

**Adopted security and safety updates**

*Updates added to patch security or safety issues. All security and safety updates adopted from other versions belong here*

