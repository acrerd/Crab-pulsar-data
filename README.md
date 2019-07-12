# Crab-pulsar-data
Crab pulsar data format
=======================

These files contain data on the Crab pulsar taken from the one
Mile Radio Telescope in Cambridge at 408 MHz.

The telescope was pointed at the Crab pulsar, and its output was
the power received within a bandwidth of 4 MHz, centred on 408
MHz.  This signal was filtered to remove power at frequencies
lower than 10 Hz and higher than about 50 Hz (the Crab signal is
at about 30 Hz). and then digitised at a sampling frequency of
exactly 100 Hz, locked to a very stable time reference.

This data stream was then multiplied by exp(iwt) in a computer,
where w (=2pi f) is an angular frequency very close to that of the
Crab pulsar. This shifts the incoming signal down in frequency by
an amount f, so that is is now at a much lower frequency (a small
fraction of a hertz) and can be averaged for longer. The time
series is now complex, because we have multiplied it by a complex
number.

Every 1024 samples (10.24 seconds) the computer wrote the average
of the real and imaginary parts of this signal out to a file with
the extension .CPX.  These are the files in this directory.

The format is as follows:

 line 1: Julian date of the start of the observation
 line 2: frequency of the multiplying function (f)
 line 3: time interval between samples (always 10.24 s)
 lines 4 to end: real and imaginary parts of the sampled data

 The data are not calibrated, so you can't determine the flux
 density of the Crab pulsar, but you can determine its (mean)
 apparent frequency during the observation period. 

