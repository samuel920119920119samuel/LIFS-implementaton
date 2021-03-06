# LDIL-MATLAB
* A low-cost device-free indoor localization tool implemented in MATLAB, mostly based on [LiFS](https://ink.library.smu.edu.sg/cgi/viewcontent.cgi?referer=&httpsredir=1&article=4390&context=sis_research)
* We aim to take better care of elders at home without expensive and complicated devices

## Dependencies
* [linux-80211n-csitool](https://github.com/dhalperi/linux-80211n-csitool/)
* Hostapd, see our wiki - [Hostapd Installation Guide](https://github.com/samuel920119920119samuel/LDIL-MATLAB/wiki/Hostapd-Installation-Guide)
* MATLAB toolbox
    * signal processing toolbox
    * global optimization toolbox
    * optimization toolbox
    * Having problems with MATLAB? See the wiki - [Background Knowledge - MATLAB](https://github.com/samuel920119920119samuel/LDIL-MATLAB/wiki/Background-Knowledge#matlab)

## Parameters
In ``main.m``, you need to change parameters according to the following scenarios:
### single AP & single MP
* ``.dat``: select .dat file collected by Intel 5300 NIC 
* ``baseIndex``,``baseIndex1``: the base packet index for ``csi_trace``
* ``Ci``, ``Cj``: location of AP and MP
* ``noise``:
    * measurement noise
    * Actually it should be optimized by genetic algorithm
* ``At``: 
    * When a target is located exactly on the LoS path, a link suffers large extra signal attenuation absorbed by the target
    * Actually it should be optimized by genetic algorithm
* ``ht``: the distance from the highest point of the target to the wireless link
* ``J``: We couldn't figure out what J is in the essay, therefore we just set this to ``1``
* genetic algorithm opts
### multi-AP & multi-MP
* All of the parameters above, and 
* ``y``: collect all CSIeff and targetLocation
* ``targetLocation``: store all`` targetLocation`` from  ``rough_location_estimate(f0, f, delta, F, O)`` as an array

## Usage
```
>> main
```

## Waiting to complete
* Gradient descent algorithm
    * In the essay, it use ga and then gd to optimize the target locaiton
    * However, in this inplementation, we only use ga.
* Multi-AP & multi-MP scenario
    * Some part of code need to be modified to support multi-AP&MP scenario

## Our Experiment
* check it out on our wiki - [Experiment Result](https://github.com/samuel920119920119samuel/LDIL-MATLAB/wiki/Experiment-Result-(single-AP-&-single-MP))

## More Info about [Indoor Localization, CSI & 802.11](https://github.com/samuel920119920119samuel/LDIL-MATLAB/wiki/Background-Knowledge)

## Contact
* [Jui-An Wang](mailto:samuel9008@g.ncu.edu.tw)
* [Bi-Hong Lai](mailto:youngle@g.ncu.edu.tw)
