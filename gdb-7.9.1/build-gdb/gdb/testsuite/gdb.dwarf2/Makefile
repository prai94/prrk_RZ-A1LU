# Makefile for regression testing the GNU debugger.
# Copyright 1992-2015 Free Software Foundation, Inc.

# This file is part of GDB.

# GDB is free software; you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation; either version 3, or (at your option)
# any later version.

# GDB is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.

# You should have received a copy of the GNU General Public License
# along with this program; if not, write to the Free Software
# Foundation, Inc., 59 Temple Place - Suite 330, Boston, MA 02111-1307, USA.

VPATH = ../../../../gdb/testsuite/gdb.dwarf2
srcdir = ../../../../gdb/testsuite/gdb.dwarf2

EXECUTABLES = *.x pr10770 dw2-cp-infcall-ref-static dw2-inline-param \
	dw2-noloc dw2-ranges dw2-ref-missing-frame dw2-unresolved gdb-index \
	dwp-symlink

MISCELLANEOUS = \
	dwp-symlink.dwp dwp-symlink-thelink dwp-symlink-thelink.dwp \
	dwp-dir1 dwp-dir2 dwp-dir3

all info install-info dvi install uninstall installcheck check:
	@echo "Nothing to be done for $@..."

clean mostlyclean:
	-rm -f *~ *.o a.out *.x *.ci *.tmp
	-rm -f core core.coremaker coremaker.core corefile
	-rm -f *.dwo *.dwp
	-rm -f $(EXECUTABLES)
	-rm -rf $(MISCELLANEOUS)
	-rm -f *.gdb-index *.with-index

distclean maintainer-clean realclean: clean
	-rm -f *~ core
	-rm -f Makefile config.status config.log
	-rm -f *-init.exp gdb.log gdb.sum
	-rm -fr *.log summary detail *.plog *.sum *.psum site.*
