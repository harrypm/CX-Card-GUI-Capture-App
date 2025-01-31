## CX Capture App 

EXPERIMENTAL!! ALPHA PHASE!!

A Linux GUI capture application for Connexant cx2338[0/1/2/3] and cx25800 based cards.

## GUI Layout

![Current](https://user-images.githubusercontent.com/56382624/222059131-28a64a03-060f-4b74-8e82-3b28b42c4a84.png)

## Dependencys

* [GNU Radio Companion](https://wiki.gnuradio.org/index.php/InstallingGR)

Ensure your GNU Radio Installation is `3.10.5.0 (Python 3.10.6)` or newer.

* [CXADC](https://github.com/happycube/cxadc-linux3)

## Notes

You will need to install GNU Radio Companion for this to work, and any depndencies it needs. 

You will need a version of the cxadc driver that supports `center_offset value` (Current release has this) 

Use the `center_offset value` to correct for non-centered singals. 

The scale of the graph is +127 to -127, the 100 notations on the amplitude axis do not represent `100%`.

## Installation

You'll need to have granted yourself read access to `/class/cxadc0`

Read/write access to the cxadc sysfs parameters (be in admin group).

CXADC Locations `/sys/class/cxadc` & `/dev/cxadc0`

## Usage 

Open via phython in terminal `./cx_capture_app`

Open via GNU Radio Companion in GUI `cx_capture_app.grc`

## Features

* Capture Start/Stop

* Set Capture File Path

* Gain Level Adjust

* Amplitude Messurement

## Limitations:

* 16 bit mode is not supported. 

* Auto adjustment of level not support (like how cxlvlcavdd does for CAV LaserDiscs). As such, probably not best solution for CAV discs. 

* Can't change vmux from within the program (this would require further updates to cxadc driver to allow real time vmux change). 

* vmux changes won't be recognized while the program is running.

## Modify & Update

You can edit the .GRC file in GNU Radio and then preview with <kbd>F5</kbd> and to export to a working python script press <kbd>F6</kbd>  

## Demos

[YouTube](https://www.youtube.com/watch?v=hENPuOPslAA)

## Notes & Warnings

Still very experimental. 

Not sure if this is the best way to develop a capture app for cxadc, it's just what i could get done quickly. 

I also haven't tested A/B capturing with this and straight `cat /dev/cxadc0`.
