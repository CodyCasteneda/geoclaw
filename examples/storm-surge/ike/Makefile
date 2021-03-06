
# Makefile for Clawpack code in this directory.
# This version only sets the local files and frequently changed
# options, and then includes the standard makefile pointed to by CLAWMAKE.
CLAWMAKE = $(CLAW)/clawutil/src/Makefile.common

# See the above file for details and a list of make options, or type
#   make .help
# at the unix prompt.


# Adjust these variables if desired:
# ----------------------------------

CLAW_PKG = geoclaw                  # Clawpack package to use
EXE = xgeoclaw                 # Executable to create
SETRUN_FILE = setrun.py        # File containing function to make data
OUTDIR = _output               # Directory for output
SETPLOT_FILE = setplot.py      # File containing function to set plots
PLOTDIR = _plots               # Directory for plots

# Environment variable FC should be set to fortran compiler, e.g. gfortran
FFLAGS ?= -W -Wall -fbounds-check -pedantic-errors -Wunderflow -ffpe-trap=zero,overflow -g

# ---------------------------------
# List of sources for this program:
# ---------------------------------

AMRLIB = $(CLAW)/amrclaw/src/2d
GEOLIB = $(CLAW)/geoclaw/src/2d/shallow
RIEMANN = $(CLAW)/riemann/src

MODULES = \
 $(GEOLIB)/utility_module.f90 \
 $(AMRLIB)/amr_module.f90 \
 $(AMRLIB)/regions_module.f90 \
 $(AMRLIB)/gauges_module.f90 \
 $(GEOLIB)/geoclaw_module.f90 \
 $(GEOLIB)/topo_module.f90 \
 $(GEOLIB)/qinit_module.f90 \
 $(GEOLIB)/refinement_module.f90 \
 $(GEOLIB)/fixedgrids_module.f90 \
 $(GEOLIB)/holland_storm_module.f90 \
 $(GEOLIB)/constant_storm_module.f90 \
 $(GEOLIB)/stommel_storm_module.f90 \
 $(GEOLIB)/storm_module.f90 \
 $(GEOLIB)/friction_module.f90 \
 $(GEOLIB)/fgmax_module.f90

SOURCES = \
  $(GEOLIB)/src2.f90 \
  $(GEOLIB)/src1d.f90 \
  $(GEOLIB)/setaux.f90 \
  $(GEOLIB)/setprob.f90 \
  $(GEOLIB)/topo_update.f90 \
  $(GEOLIB)/flag2refine2.f90 \
  $(GEOLIB)/b4step2.f90 \
  $(GEOLIB)/tick.f \
  $(GEOLIB)/valout.f \
  $(GEOLIB)/qinit.f90 \
  $(GEOLIB)/bc2amr.f \
  $(GEOLIB)/allowflag.f90 \
  $(GEOLIB)/cellgridintegrate2.f \
  $(GEOLIB)/topointegral.f \
  $(GEOLIB)/bilinearintegral.f \
  $(GEOLIB)/stepgrid.f \
  $(RIEMANN)/rpn2_geoclaw.f \
  $(RIEMANN)/rpt2_geoclaw.f \
  $(RIEMANN)/geoclaw_riemann_utils.f \
  $(GEOLIB)/step2.f \
  $(GEOLIB)/flux2fw.f \
  $(GEOLIB)/qad.f \
  $(GEOLIB)/update.f \
  $(GEOLIB)/dumpgauge.f \
  $(GEOLIB)/upbnd.f  \
  $(GEOLIB)/setgrd.f \
  $(GEOLIB)/gfixup.f \
  $(GEOLIB)/ginit.f \
  $(GEOLIB)/getmaxspeed.f90 \
  $(GEOLIB)/advanc.f \
  $(GEOLIB)/filval.f90 \
  $(GEOLIB)/filpatch.f90 \
  $(AMRLIB)/prefilp.f90 \
  $(AMRLIB)/trimbd.f90 \
  $(AMRLIB)/bound.f90 \
  $(AMRLIB)/intfil.f90 \
  $(AMRLIB)/amr2.f90 \
  $(GEOLIB)/fgmax_read.f90 \
  $(GEOLIB)/fgmax_frompatch.f90 \
  $(GEOLIB)/fgmax_interpolate.f90 \
  $(GEOLIB)/fgmax_values.f90 \
  $(GEOLIB)/fgmax_finalize.f90 \
  $(AMRLIB)/quick_sort1.f \
  $(AMRLIB)/estdt.f \
  $(AMRLIB)/check4nans.f \
  $(AMRLIB)/spest2.f  \
  $(AMRLIB)/init_iflags.f \
  $(AMRLIB)/igetsp.f \
  $(AMRLIB)/reclam.f \
  $(AMRLIB)/birect.f \
  $(AMRLIB)/cleanup.f \
  $(AMRLIB)/colate2.f \
  $(AMRLIB)/flagregions2.f90  \
  $(AMRLIB)/errest.f \
  $(AMRLIB)/prepregstep.f \
  $(AMRLIB)/prepbigstep.f \
  $(AMRLIB)/bufnst2.f \
  $(AMRLIB)/flagger.f \
  $(AMRLIB)/errf1.f \
  $(AMRLIB)/fixcapaq.f \
  $(AMRLIB)/flglvl2.f \
  $(AMRLIB)/fluxad.f \
  $(AMRLIB)/fluxsv.f \
  $(AMRLIB)/grdfit2.f \
  $(AMRLIB)/moment.f \
  $(AMRLIB)/nestck2.f \
  $(AMRLIB)/prepc.f \
  $(AMRLIB)/prepf.f \
  $(AMRLIB)/projec2.f \
  $(AMRLIB)/signs.f \
  $(AMRLIB)/findcut.f \
  $(AMRLIB)/smartbis.f \
  $(AMRLIB)/putnod.f \
  $(AMRLIB)/putsp.f \
  $(AMRLIB)/regrid.f \
  $(AMRLIB)/setuse.f \
  $(AMRLIB)/stst1.f \
  $(AMRLIB)/nodget.f \
  $(AMRLIB)/basic.f \
  $(AMRLIB)/outval.f \
  $(AMRLIB)/copysol.f \
  $(AMRLIB)/outvar.f \
  $(AMRLIB)/outmsh.f \
  $(AMRLIB)/outtre.f \
  $(AMRLIB)/domain.f  \
  $(AMRLIB)/cellave.f \
  $(AMRLIB)/fdisc.f \
  $(AMRLIB)/fss.f \
  $(AMRLIB)/zeroin.f \
  $(AMRLIB)/setflags.f \
  $(AMRLIB)/shiftset2.f \
  $(AMRLIB)/conck.f \
  $(AMRLIB)/domshrink.f \
  $(AMRLIB)/domprep.f \
  $(AMRLIB)/domup.f \
  $(AMRLIB)/domcopy.f \
  $(AMRLIB)/coarsen.f \
  $(AMRLIB)/setdomflags.f \
  $(AMRLIB)/setIndices.f \
  $(AMRLIB)/coarseGridFlagSet.f \
  $(AMRLIB)/setPhysBndryFlags.f \
  $(AMRLIB)/griddomup.f \
  $(AMRLIB)/griddomcopy.f \
  $(AMRLIB)/griddomshrink.f \
  $(AMRLIB)/domgrid.f \
  $(AMRLIB)/addflags.f \
  $(AMRLIB)/baseCheck.f \
  $(AMRLIB)/drivesort.f \
  $(AMRLIB)/flagcheck.f \
  $(AMRLIB)/auxcoarsen.f \
  $(AMRLIB)/intcopy.f \
  $(AMRLIB)/preintcopy.f \
  $(AMRLIB)/icall.f \
  $(AMRLIB)/preicall.f \
  $(AMRLIB)/inlinelimiter.f \
  $(AMRLIB)/cstore.f \
  $(AMRLIB)/saveqc.f \
  $(AMRLIB)/check.f \
  $(AMRLIB)/restrt.f \
  $(AMRLIB)/opendatafile.f \
  $(AMRLIB)/init_alloc.f90 \
  $(AMRLIB)/restrt_alloc.f90 \
  $(AMRLIB)/resize_alloc.f90

#-------------------------------------------------------------------
# Include Makefile containing standard definitions and make options:
include $(CLAWMAKE)


# Construct the topography data
.PHONY: topo all

gulf_caribbean.tt3:
	python get_bathy.py

topo: gulf_caribbean.tt3

all: 
	$(MAKE) topo
	$(MAKE) .plots
	$(MAKE) .htmls


### DO NOT remove this line - make depends on it ###

