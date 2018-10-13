#
# Copyright (c) 2018 Cadence Design Systems Inc.
#
# Permission is hereby granted, free of charge, to any person obtaining
# a copy of this software and associated documentation files (the
# "Software"), to deal in the Software without restriction, including
# without limitation the rights to use, copy, modify, merge, publish,
# distribute, sublicense, and/or sell copies of the Software, and to
# permit persons to whom the Software is furnished to do so, subject to
# the following conditions:
#
# The above copyright notice and this permission notice shall be included
# in all copies or substantial portions of the Software.
#
# THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
# EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
# MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
# IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
# CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
# TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
# SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
#

SUBDIRS = libfdt
bin_PROGRAMS = dtc fdtput fdtget fdtdump

BUILT_SOURCES = dtc-parser.tab.c dtc-parser.tab.h dtc-lexer.lex.c

dtc_SOURCES = \
	checks.c \
	data.c \
	dtc.c \
	dtc-parser.tab.c \
	dtc-lexer.lex.c \
	flattree.c \
	fstree.c \
	livetree.c \
	srcpos.c \
	treesource.c \
	util.c
dtc_CPPFLAGS = -I$(srcdir)/libfdt
dtc_LDADD = libfdt/libfdt.a

fdtput_SOURCES = fdtput.c util.c
fdtput_CPPFLAGS = -I$(srcdir)/libfdt
fdtput_LDADD = libfdt/libfdt.a

fdtget_SOURCES = fdtget.c util.c
fdtget_CPPFLAGS = -I$(srcdir)/libfdt
fdtget_LDADD = libfdt/libfdt.a

fdtdump_SOURCES = fdtdump.c util.c
fdtdump_CPPFLAGS = -I$(srcdir)/libfdt
fdtdump_LDADD = libfdt/libfdt.a

dtc-parser.tab.c dtc-parser.tab.h: dtc-parser.y
	$(AM_V_GEN)$(YACC) -odtc-parser.tab.c -d $^

dtc-lexer.lex.c: dtc-lexer.l
	$(AM_V_GEN)$(LEX) -o$@  $^
