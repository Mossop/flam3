AUTOMAKE_OPTIONS = foreign no-dependencies

GIT_DEF = -D'GIT_REV="$(shell git describe --tags --dirty)"'
AM_CFLAGS = -g -O3 -std=gnu99 -DPACKAGE_DATA_DIR=\"$(pkgdatadir)\" $(GIT_DEF)

ACLOCAL_AMFLAGS = -I m4

man1_MANS = flam3-animate.man flam3-genome.man flam3-render.man flam3-convert.man
bin_PROGRAMS = flam3-animate flam3-genome flam3-render flam3-convert
lib_LTLIBRARIES = libflam3.la
include_HEADERS = flam3.h isaac.h isaacs.h rect.c

libflam3_la_SOURCES = flam3.c filters.c parser.c variations.c interpolation.c palettes.c jpeg.c png.c isaac.c
libflam3_la_LDFLAGS = -no-undefined -ljpeg -lpng -lz -lpthread

flam3_genome_SOURCES = flam3-genome.c docstring.c
flam3_genome_LDADD = libflam3.la -lm

flam3_animate_SOURCES = flam3-animate.c docstring.c
flam3_animate_LDADD = libflam3.la -lm

flam3_render_SOURCES = flam3-render.c docstring.c
flam3_render_LDADD = libflam3.la -lm

flam3_convert_SOURCES = flam3-convert.c docstring.c
flam3_convert_LDADD = libflam3.la -lm

pkgdata_DATA = flam3-palettes.xml

EXTRA_DIST = rect.c flam3.h palettes.h variations.h interpolation.h parser.h \
   private.h isaac.h isaacs.h img.h test.flam3 vidres.flam3 \
   flam3.dsw render.dsp animate.dsp genome.dsp convert.dsp \
   mkinstalldirs README.txt COPYING.txt flam3-palettes.xml \
   flam3-animate.man flam3-render.man flam3-genome.man flam3-convert.man 

pkgconfigdir = $(libdir)/pkgconfig
pkgconfig_DATA = flam3.pc
