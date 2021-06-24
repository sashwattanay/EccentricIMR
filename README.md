# EccentricIMR

## About

A Mathematica package for generating gravitational waveforms for
nonspinning eccentric binary black hole mergers.

Requirements: Mathematica v10 (Jul 2014) or later

EccentricIMR was written by Ian Hinder and is distributed under the terms of the GNU General Public Licence (GPL) version 2.

Copyright (C) Ian Hinder, 2017.

See [Hinder, Kidder and Pfeiffer - An eccentric binary black hole inspiral-merger-ringdown gravitational waveform model from numerical relativity and post-Newtonian theory, 2017](http://arxiv.org/abs/1709.02007) for details of the construction of the waveform.

## Installation

You can install EccentricIMR by downloading a zip file.

- Download [master.zip](https://github.com/sashwattanay/EccentricIMR/archive/master.zip),
- Extract the zip file
- There is a directory 'EccentricIMR' in '4PN_IMR_package' (plots the full IMR; does not work for large eccentricities) and also in '4PN_Inspiral_only_package' (plots only the inspiral part; works for large eccentricities too).
- Move the 'EccentricIMR' directory (from either the '4PN_IMR_package' directory or the '4PN_Inspiral_only_package' directory) into your Mathematica applications directory
(~/Library/Mathematica/Applications on Mac OS,
~/.Mathematica/Applications on Linux)
- The file 'How to run the packages.nb' has commands that will run the packages and plot the waveforms.
- The file 'Lengthy_expressions.nb' contains some lengthy expressions which we did not present in the paper for the sake of brevity. 


## Documentation

### EccentricIMRWaveform[_parameters_, {_t1_, _t2_}]

Generate an eccentric inspiral-merger-ringdown waveform with the parameters given in the time range {t1,t2}.  

_parameters_ is an Association with the following entries:

Parameter | Meaning
--------- | ---
q         | Mass ratio of the binary (q=m1/m2)
t0        | _Reference time_ at which the remaining parameters are quoted
x0        | Dimensionless frequency parameter (x = (M om_orb)^(2/3)) evaluated at the reference time
e0		   | Eccentricity at the reference time
l0		   | Mean anomaly at the reference time
phi0	   | Orbital phase at the reference time

See [arXiv:0806.1037](http://arxiv.org/abs/arXiv:0806.1037) for full details about the meaning of the parameters.

The returned waveform is expressed as a list of {t, h22} pairs, where t is the retarted time coordinate and h22 is the l=2, m=2 spin-weighted spherical harmonic coefficient of the waveform.
