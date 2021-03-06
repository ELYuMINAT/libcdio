#   $Id: Makefile.am,v 1.13 2008/08/31 13:38:21 flameeyes Exp $
#
#   Copyright (C) 2005, 2006, 2008 Rocky Bernstein <rocky@gnu.org>
#
#   This program is free software: you can redistribute it and/or modify
#   it under the terms of the GNU General Public License as published by
#   the Free Software Foundation, either version 3 of the License, or
#   (at your option) any later version.
#
#   This program is distributed in the hope that it will be useful,
#   but WITHOUT ANY WARRANTY; without even the implied warranty of
#   MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
#   GNU General Public License for more details.
#
#   You should have received a copy of the GNU General Public License
#   along with this program.  If not, see <http://www.gnu.org/licenses/>.

##########################################################
# Sample C++ programs using libcdio (without OO wrapper)
#########################################################
#
SUBDIRS = OO

if BUILD_CD_PARANOIA
paranoia_progs = paranoia paranoia2
endif
if BUILD_EXAMPLES
noinst_PROGRAMS = device eject isofile isofile2 isolist \
	          mmc1 mmc2 $(paranoia_progs)
endif

INCLUDES = -I$(top_srcdir) $(LIBCDIO_CFLAGS)

device_DEPENDENCIES = $(LIBCDIO_DEPS)
device_SOURCES      = device.cpp
device_LDADD        = $(LIBCDIO_LIBS)

eject_DEPENDENCIES  = $(LIBCDIO_DEPS)
eject_SOURCES       = eject.cpp
eject_LDADD         = $(LIBCDIO_LIBS)

if BUILD_CD_PARANOIA
paranoia_SOURCES  = paranoia.cpp
paranoia_LDADD    = $(LIBCDIO_PARANOIA_LIBS) $(LIBCDIO_CDDA_LIBS) \
	            $(LIBCDIO_LIBS)
paranoia2_SOURCES = paranoia.cpp
paranoia2_LDADD   = $(LIBCDIO_PARANOIA_LIBS) $(LIBCDIO_CDDA_LIBS) \
	            $(LIBCDIO_LIBS)
endif

isofile_SOURCES   = isofile.cpp
isofile_LDADD     = $(LIBISO9660_LIBS) $(LIBCDIO_LIBS) $(LTLIBICONV)
isofile2_SOURCES  = isofile2.cpp
isofile2_LDADD    = $(LIBISO9660_LIBS) $(LIBCDIO_LIBS) $(LTLIBICONV)
isolist_SOURCES   = isolist.cpp
isolist_LDADD     = $(LIBISO9660_LIBS) $(LIBCDIO_LIBS) $(LTLIBICONV)

mmc1_SOURCES      = mmc1.cpp
mmc1_DEPENDENCIES = $(LIBCDIO_DEPS)
mmc1_LDADD        = $(LIBCDIO_LIBS)

mmc2_SOURCES      = mmc2.cpp
mmc2_DEPENDENCIES = $(LIBCDIO_DEPS)
mmc2_LDADD        = $(LIBCDIO_LIBS)

# iso programs create file "copying"
MOSTLYCLEANFILES = copying
