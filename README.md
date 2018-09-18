# OpalKellyXEM3001 pseudoclock firmware for the labscript suite

[project home](https://bitbucket.org/labscript_suite/opalkellyxem3001)

A FPGA based pseudoclock for the labscript suite using the Opal Kelly XEM3001 board.

This is based on a fork of the Cicero Word Generator FPGA code located [here](https://github.com/akeshet/Cicero-Word-Generator/tree/master/Opal%20Kelly) and is thus licensed under the GPL as documented [here](http://akeshet.github.io/Cicero-Word-Generator/).  

The FPGA logic has been modified to correct a bug in how "waits" were implemented, which caused the output state associated with the wait instruction to change prior to entering retrigger mode. The bug was documented on the Cicero project [here](https://github.com/akeshet/Cicero-Word-Generator/issues/16) however the solution was to change the expected behaviour of a "wait for retrigger" instruction to what is know known as "hold and re-trigger" instructions, rather than fixing the FPGA firmware. This is incompatible with the architecture of [the labscript suite](https://bitbucket.org/labscript_suite), so we corrected the bug in the FPGA code.


## Project status

This firmware is currently in beta-test stage. Feel free to test it out (in combination with the labscript suite), however there are likely still bugs we have not uncovered yet. If you find bugs in the firmware, please create an issue on this project! If you find bugs in the labscript device code, please log them in the [labscript_devices repository](https://bitbucket.org/labscript_suite/labscript_devices/).

We do not yet recommend using this for 'production' (aka experiments you care about!)

As always, you use this at your own risk and we provide no warranty (as outlined in the GPL license).

## How to use
There are two .bit files (for the different reference clock schemes) located at the top level of this repository. These should be placed in your labscript_devices folder.

You will also need to install the Opal Kelly Front Panel SDK, including Python bindings. This is only available for download by people who actually own an Opal Kelly board and have registered for access to the Opal Kelly support/download website. Our testing/development was done with Opal Kelly Front Panel v4.5.0. Other v4 variants will likely work, but we are unsure if v5 will or not yet. Feel free to experiment and let us know!

If you want to modify/recompile these yourself, you will need Xilinx ISE Project Navigator v14.7. This is quite an old version, but is the newest version still compatible with the Opal Kelly Xem3001 as far as I'm aware. The ISE project files are located in the AvivFPGAv2 folder (you will want to open AvivFPGA2.xise, which will then allow you to edit AvivFPGA.v and rebuild the firmware).

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