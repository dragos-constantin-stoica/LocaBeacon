# LocaBeacon
Indoor Localization Beacon --- FUNDING NEEDED!!!

Most solutions proposed on the market for indoor localization based on iBeacons or Smart Bluetooth/Bluetooth Low Energy supose a precalibration phase. In this phase the received power form the beacons is memorized and saved together with the room map. Beacons are configured to emit at a single value of power, usually maximum. The main drawback is that this inital calibration is done in certain conditions that may drastically change over time, leading to a strong bias and making localization imprecise and in some cases impossible.

Our approach is to skip intial calibration and to use continuous beacon emitting power sweep, i.e. to varry continuously the emmiting power of all beacons in the room. We know in advance the plan of the room, physical dimensions, and the precise location of localization beacons. Our client will use the mobile phone and an application to receive those signal, process them and display the current position.  Because we use only current available information we are able to cover a wide range of situations.

Our solution consists of:
* hardware - LocaBeacon, based on Nordic Semiconductor's nRF51X
* software running on the LocaBeacon
* mobile application for Indoor Localization running on client's mobile phone
* web application allowing the desing and management of maps - accesible only to administrators

## Project status

We are looking for funding. Please contact us if you are interested to invest in this project.  
We have a Proof Of Concept (POC) for software running on LocaBeacon. We have an application running on Android and a web application allowing you the manage the design of interior maps.


We need funding for 6-8 months in order to produce a MVP: hardware+software and the application platform.


## Hints about software running on the LocaBeacon
Here is the pseudo code for the LocaBeacon software:
```
Configure LocaBeacon (before installing) via Admin mode
[Physically install the LocaBeacon]

while(true){
  Enable external service
    TimeClient
    BatteryStatus
    Secure DFU
    Admin
  Cycle power from minPower to maxPower
    Emmit with power for a couple of data frames
}

Admin{
  Configure UUID, Major, minor, BeaconName, BeaconType
}

Secure DFU{
  Authenticate
  Upload new software/firmware
}
```
Another feature of the LocaBeacon will be the ability to talk with other LocaBeacon via mesh protocol, allowing to manage the network, propagate software/firmaware updates and get alerts.
