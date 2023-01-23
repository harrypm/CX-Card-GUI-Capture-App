## CX Capture App 

EXPERIMENTAL!! ALPHA PHASE!!

A Linux GUI capture application for Connexant cx2338[0/1/2/3] and cx25800 based cards.

## GUI Layout

![Current](https://user-images.githubusercontent.com/56382624/214147114-b8e9ed60-855c-4a3b-b853-93f7b15c8fd3.png)

## Dependencys

* [GNU Radio Companion](https://wiki.gnuradio.org/index.php/InstallingGR)

* [CXADC](https://github.com/happycube/cxadc-linux3)

## Notes

You will need to install GNU Radio Companion for this to work, and any depndencies it needs. 

You will need a version of the cxadc driver that supports `center_offset value` (Current release has this) 

Use the `center_offset value` to correct for non-centered singals. 

The scale of the graph is +127 to -127, the 100 notations on the amplitude axis do not represent `100%`.

You'll need to have granted yourself read access to /dev/cxadc0 and read/write access to the cxadc sysfs parameters (be in admin group).

## Features & Usage

* Capture Start/Stop

* Capture File Path (Output)

* Gain Level Adjust

* Amplitude Messurement

## Limitations:

* 16 bit mode is not supported. 

* Auto adjustment of level not support (like how cxlvlcavdd does for CAV LaserDiscs). As such, probably not best solution for CAV discs. 

* Can't change vmux from within the program (this would require further updates to cxadc driver to allow real time vmux change). 

* vmux changes won't be recognized while the program is running.

## Demos

[YouTube](https://www.youtube.com/watch?v=hENPuOPslAA)

## WARNING!!!

Still very experimental. 

Not sure if this is the best way to develop a capture app for cxadc, it's just what i could get done quickly. 

I also haven't tested A/B capturing with this and straight `cat /dev/cxadc0`.
