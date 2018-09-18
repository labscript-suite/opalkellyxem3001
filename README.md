# OpalKellyXEM3001 pseudoclock firmware for the labscript suite

[project home](https://bitbucket.org/labscript_suite/opalkellyxem3001)

A FPGA based pseudoclock for the labscript suite using the Opal Kelly XEM3001 board.

This is based on a fork of the Cicero Word Generator FPGA code located [here](https://github.com/akeshet/Cicero-Word-Generator/tree/master/Opal%20Kelly) and is thus licensed under the GPL as documented [here](http://akeshet.github.io/Cicero-Word-Generator/).  

The FPGA logic has been modified to correct a bug in how "waits" were implemented, which caused the output state associated with the wait instruction to change prior to entering retrigger mode. The bug was documented on the Cicero project [here](https://github.com/akeshet/Cicero-Word-Generator/issues/16) however the solution was to change the expected behaviour of a "wait for retrigger" instruction to what is know known as "hold and re-trigger" instructions, rather than fixing the FPGA firmware. This is incompatible with the architecture of [the labscript suite](https://bitbucket.org/labscript_suite), so we corrected the bug in the FPGA code.

## License and copyright information:

    Original work copyright (C) 2008 Aviv Keshet  
    Modified work copyright (C) 2015 Philip Starkey

    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <https://www.gnu.org/licenses/>.