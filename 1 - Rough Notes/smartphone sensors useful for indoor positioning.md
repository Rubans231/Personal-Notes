
2025-08-14 16:36

Status:

Tags: [[technology]] [[hardware]]  [[mobile]]


# smartphone sensors

In particular, we identify five properties that are most relevant for our purpose.

- _Temporal variation_. This is the sensor's ability to produce consistent measures over time, under the same environmental setting (e.g. in the same location).
    
- _Spatial difference_. For indoor positioning, it is critical that distinct locations have distinguishable sensor signatures, which are useful for pattern matching algorithms.
    
- _Battery consumption_. The lower the energy consumption, the longer the positioning app may continue running.
    
- _User permission_. Some sensors such as inertial ones can be queried at any moment, without a consent request, which enables a smoother user experience. Others require special attention from the user in the form of a pop-up window to grant access (e.g., WiFi, Bluetooth, GNSS).
    
- _Sampling rate_. This metric determines how frequently the sensor updates its measure. A high sampling rate sensor is critical for tracking fast moving users and objects.


TABLE 2. Comparison of the characteristics of 14 most common smartphones sensors, in alphabetical order, for the indoor positioning purpose

| Sensor type                                                                                                             | Temporal variation | Location accuracy | Battery consumption | User permission | Max. frequency | Description                                                                        |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------ | ----------------- | ------------------- | --------------- | -------------- | ---------------------------------------------------------------------------------- |
| Accelerometer                                                                                                           | Low                | Various           | Low                 | None            | 196 Hz         | Measuring the changing rate of the device acceleration                             |
| Ambient light                                                                                                           | Low                | Low               | Low                 | None            | 4 Hz           | Measuring the ambient visible light's intensity                                    |
| Barometer                                                                                                               | High               | Low               | Low                 | None            | 90 Hz          | Measuring the atmospheric pressure                                                 |
| Bluetooth                                                                                                               | High               | Medium            | Low                 | Yes             | Various        | Communicating with nearby Bluetooth beacons or other Bluetooth-enabled devices     |
| Camera[a](https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/csy2.12004#csy212004-note-0006_13 "Link to note")     | Various            | High              | High                | Yes             | 60 Hz          | Capturing the scenery via the front or back lenses                                 |
| Cellular                                                                                                                | Low                | Low               | High                | Yes             | 20 Hz          | Communicating with nearby cell towers                                              |
| FM[b](https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/csy2.12004#csy212004-note-0007_14 "Link to note")         | Low                | Low               | High                | Yes             | N/A            | Receiving information from nearby radio towers                                     |
| GNSS                                                                                                                    | Low                | Various           | High                | Yes             | 10 Hz          | Receiving the satellite signals to compute the latitude and longitude of the phone |
| Gyroscope                                                                                                               | Low                | Low               | Low                 | None            | 198 Hz         | Measuring the changing rate of the device's tilting angle                          |
| Magnetometer                                                                                                            | Low                | Various           | Low                 | None            | 49 Hz          | Measuring the ambient magnetic field strength                                      |
| Microphone[a](https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/csy2.12004#csy212004-note-0006_15 "Link to note") | High               | Medium            | High                | Yes             | 48 Hz          | Capturing the ambient acoustic noise                                               |
| NFC                                                                                                                     | Various            | Various           | High                | Yes             | 1 Hz           | Communicating with nearby RFID tags                                                |
| Proximity                                                                                                               | Low                | Various           | Low                 | None            | 4 Hz           | Measuring distance to the nearest object within 10 cm                              |
| WiFi                                                                                                                    | High               | Medium            | High                | Yes             | 0.03 Hz        | Communicating with nearby access points or other WiFi-enabled devices              |

![[Pasted image 20250814164225.png]]

## we categorize these sensors into four groups based on their functioning mechanism

- _[[Electromagnetic-based]]_. These sensors operate on the electromagnetic spectrum, through the invisible waves of wireless signals.
    
- _Visible light-based_. These sensors rely on visible natural lights to function.
    
- _Inertia-based_. These sensors use motions to estimate the phone's position.
    
- _Others_. This group includes the microphone, fingerprint, barometer, proximity, and magnetometer, which do not directly fit in the above groups.
![[Pasted image 20250814164516.png]]


# References
https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/csy2.12004