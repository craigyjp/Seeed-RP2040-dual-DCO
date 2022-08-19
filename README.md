# Seeed-RP2040-dual-DCO
A single voice dual DCO with the Seeed XIAO RP2040

Carrying on the excellent work by Jan Knipper.

https://github.com/polykit/pico-dco

I ported his Polykit Pico DCO to the Seeed XIAO RP2040, not much of a feat I know, but I made a single voice dual DCO with the available pins. 
I modded the detune so only the second DCO actually detuned down from the first. 
I also added the FM input and control input both +/-5v input range. Gate output 0-3.3v as before, could be level shifted if needed.

The stack has gone as it’s now a permanent 2 DCO voice. Each wave has its own VCA so it can be mixed by voltage control or a control knob. 
There is an octave select for -1/0/+1 octave adjustment. input is by Din MIDI or USBmidi as before. 
Really a Pico could have been used, but I bought half a dozen of these modules and wanted to try to use them.

Dual DCO
Sawtooth wave 10v pp
Pulse wave 10v pp
PW adjust pot
PW modulation input
Detune DCO 2
FM input +/-5v 
Control input +/-5v
Gate out 0-3.3v
Midi input
USB midi input
Octave switch 32, 16 and 8' modes
Portamento over MID,  time and on/off
Pitchbend over MIDI 
