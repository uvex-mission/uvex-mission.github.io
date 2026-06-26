
# UVEX Software

## Goals and overview

Goal is to capture the various elements of the UVEX instrument performance simulators
used for both science simulations, for science validation, and or ground validation of
instrument performance. Lead Dev is responsible for maintaining the code base and
addressing items raised via the Issue page (or delegating them, as needed).

Versions will follow standard conventions of:

vX.Y.Z

…where X are major releases (e.g., v.1.0.0), Y are incremental (monthly, e.g., v1.1.0)
releases, and Z are minor releases, bug fixes, and updates (as needed, e.g., v1.1.1) 

CCB will be an informal Change Control Board (until we decide this needs to be more
formal) to be polled ahead of major versioned releases.

When practical (e.g., when the code base does not include proprietary data from a
vendor) the code repo’s will be public and open source (e.g., standard MIT license).  


## Repository information:

[uvex-mission](https://github.com/uvex-mission/uvex-mission)

Description: Main repository during the preliminary design phase of the mission. Includes
a large number of configurable options tested during mission design.

Subsections:
- uvex-mission/sensitivity: All of the throughput curves, backgrounds definitions, and
ETC live here. Includes a 1D LSS spectral simulator. Margins against Level 2 and the DRM
live here.
- uvex-mission/imaging: Preliminary PSF libraries and a simple image simulation tool
live here.
- uvex-mission/scheduling: Mostly jupyter notebooks to assess things like the field-of-
regard throughout the year live here. The main scheduler tool does NOT live here.

Admin: Brian Grefenstette
CCB: Hannah Earnshaw, Jason McPhate, Fiona Harrison
Status: Private, available to UVEX team members.


