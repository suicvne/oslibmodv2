# MikMod Library Makefile for DJGPP Linux
# Divine Entertainment Game Programming Pack


####################
### User Options ###
####################

# Use the C or C++ compiler
CC                = gcc 
CFLAGS  = -O2 -I. -I../include -g -DOSS

Lib_file          = ../lib/libmikmod.a

LoaderObjs        = mloader.o mlreg.o npertab.o sloader.o load_uni.o \
    load_mod.o load_m15.o load_mtm.o load_s3m.o load_stm.o load_669.o \
    load_far.o load_dsm.o load_med.o load_xm.o load_ult.o load_it.o \
    s3m_it.o

DriverObjs        = mdriver.o mdreg.o drv_nos.o drv_raw.o drv_wav.o \
	unix_drv/drv_oss.o 
# unix_drv/drv_AF.o unix_drv/drv_aix.o unix_drv/drv_hp.o
# unix_drv/drv_sun.o unix_drv/drv_sgi.o

PlayerObjs        = mplayer.o

####################
## Makefile rules ##
####################

all: $(Lib_file)

$(Lib_file): stream.o virtch.o munitrk.o \
	$(LoaderObjs) $(DriverObjs) $(PlayerObjs)
	ar r $(Lib_file) stream.o virtch.o munitrk.o \
        $(LoaderObjs) $(PlayerObjs) $(DriverObjs)

clean:
	rm -f *.o
	rm -f unix_drv/*.o
	rm -f $(Lib_file)
