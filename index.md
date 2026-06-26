# UVEX Software 

# [The main UVEX Science page is here](https://www.uvex.caltech.edu/)

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

- Admin: Brian Grefenstette
- CCB: Hannah Earnshaw, Jason McPhate, Fiona Harrison
- Status: Private, available to UVEX team members.


## Planning purposes

The above repo is too unweildy to last long term. So I think the plan is to split it up
into smaller chunks.

| Repo      | Purpose | Inputs | Outputs | Lead Dev (CBB) |
| uvex_response      | Maintain UVEX throughput curves and synthesize performance curves based on ground calibration data. Maintain versioned releases of detector performance for use below  | Models of individual component performance for optical elements and detector performance.As data become available, incorporate lab measurements or measurements from vendors | Official throughout curves, detector performance values, grating dispersion, etc. Should serve as inputs to everything below. This is the bulk of uvex.config() and uvex.filters() in uvex-mission now. Should produce outputs compatible with the UVEX ETC and DRM tools below as well as ScopeSim and RustSim inputs. |BG (FAH, JBM, HPE) |
 | uvex_psf     | Maintain the UVEX PSF libraries and input tools.  | Inputs from Fucik and Reiley capturing the as-designed PSFs, estimates for the as-built PSFs, and estimates for the as-flown PSFs| Libraries of PSFs (ePSF inputs?) used by downstream tools. Output formats TBD. |TBD (TBD)) |
  | uvex_imager_etc     | Lightweight flux-to-counts converter and SRN estimation | Takes output of uvex_response and a source model. Simple scope of computations for throughput and SNR | Rates and SNR estimates for the UVEX FUV and NUV imagers (what’s in the ETC now) | HPE (BG, FAH, JBM)|
  | uvex_lss_sim     | Lightweight 1-D spectral simulation tools | Takes output of uvex_response and a source model to produce a simulated 1D spectrum | 1D spectral tools and performance estimation (what’s in the uvex-mission now) | HPE (BG, FAH, JBM)|
  | uvex_drm     | Official tool to estimate science margin for the implementation of the DRM | Takes output of uvex_response, and output of schedule simulator, and DRM requirements to estimate science margin | Science margin per L1 science goal (or something…this should be a copy of what’s in the uvex-mission now.| HPE (BG, FAH, JBM)|
  | uvex_quick_im     | Simple imaging simulator for single frame exposures. Primarily used for ground calibration preparations, compressibility testing, guide star sims, etc. | Takes PSF libraries, uvex_response outputs, and can produce detector-images that can serve as inputs for ground calibration analysis development| FITS images for either an FUV or NUV detector. This is what’s in uvex-mission/imaging now.| BG (JBM)|


## ScopeSim

## MayaSim


## **Imposter syndrome disclaimer**: We want your help. No, really.

There may be a little voice inside your head that is telling you that you're not
ready to be an open source contributor; that your skills aren't nearly good
enough to contribute. What could you possibly offer a project like this one?

We assure you - the little voice in your head is wrong. If you can write code at
all, you can contribute code to open source. Contributing to open source
projects is a fantastic way to advance one's coding skills. Writing perfect code
isn't the measure of a good developer (that would disqualify all of us!); it's
trying to create something, making mistakes, and learning from those
mistakes. That's how we all improve, and we are happy to help others learn.

Being an open source contributor doesn't just mean writing code, either. You can
help out by writing documentation, tests, or even giving feedback about the
project (and yes - that includes giving feedback about the contribution
process). Some of these contributions may be the most valuable to the project as
a whole, because you're coming to the project with fresh eyes, so you can see
the errors and assumptions that seasoned contributors have glossed over.

Note: This disclaimer was originally written by
`Adrienne Lowe <https://github.com/adriennefriend>`_ for a
`PyCon talk <https://www.youtube.com/watch?v=6Uj746j9Heo>`_ , and was adapted by
nustar-gen-util based on its use in the README file for the
`MetPy project <https://github.com/Unidata/MetPy>`_.