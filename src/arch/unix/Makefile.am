# Makefile.am for the Unix version of `libarch.a'.

if MACOSX_COCOA
SUBDIRS = macosx
else
if UNIX_MACOSX_COMPILE
if NEED_READLINE
SUBDIRS = gui x11 readline macosx
else
SUBDIRS = gui x11 macosx
endif
else
if NEED_READLINE
SUBDIRS = gui minix next_open_rhap qnx4 qnx6 readline sco_sol skyos x11
else
SUBDIRS = gui minix next_open_rhap qnx4 qnx6 sco_sol skyos x11
endif
endif
endif

AM_CPPFLAGS = \
	@ARCH_INCLUDES@ \
	-I$(top_builddir)/src \
	-I$(top_srcdir)/src/drive \
	-I$(top_srcdir)/src/arch/unix/readline \
	-I$(top_srcdir)/src/rs232drv \
	-I$(top_srcdir)/src/c64 \
	-I$(top_srcdir)/src/c64dtv \
	-I$(top_srcdir)/src/c128 \
	-I$(top_srcdir)/src/vic20 \
	-I$(top_srcdir)/src/pet \
	-I$(top_srcdir)/src/cbm2 \
	-I$(top_srcdir)/src/sid \
	-I$(top_srcdir)/src/joyport \
	-I$(top_srcdir)/src/lib/p64 \
	-I$(top_srcdir)/src/platform \
	-I$(top_srcdir)/src

noinst_LIBRARIES = libarch.a

libarch_a_DEPENDENCIES = @VICE_UI_THREADS@
libarch_a_LIBADD = @VICE_UI_THREADS@

libarch_a_SOURCES = \
	archdep.c \
	archdep.h \
	blockdev.c \
	catweaselmkiii-drv.c \
	coproc.h \
	coproc.c \
	cw.h \
	cw-device.c \
	cw-pci.c \
	dynlib.c \
	fullscreenarch.h \
	hardsid-drv.c \
	hs.h \
	hs-linux.c \
	hs-isa.c \
	hs-pci.c \
	icon.h \
	io-access.c \
	io-access.h \
	joy.c \
	joy.h \
	joy_usb.c \
	kbd.h \
	mididrv.c \
	mousedrv.c \
	mousedrv.h \
	openGL_sync.h \
	parsid-drv.c \
	pci-drv.c \
	pci-drv.h \
	ps.h \
	ps-file.c \
	ps-ieee1284.c \
	ps-io.c \
	rs232dev.c \
	signals.c \
	socketimpl.h \
	rawnetarch.c \
	ssi2001-drv.c \
	types.h \
	ui.h \
	uimenu.h \
	unixmain.c \
	videoarch.h \
	vmstermios.h \
	vsyncarch.c \
	vsiduiunix.h

EXTRA_libarch_a_SOURCES = \
	ui-threads.h \
	ui-threads.c 

.PHONY: x11
x11:
	(cd x11; $(MAKE))

.PHONY: gui
gui:
	(cd gui; $(MAKE))

.PHONY: macosx
macosx:
	(cd macosx; $(MAKE))
