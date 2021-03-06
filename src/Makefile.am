# Copyright 2000-2018 Free Software Foundation, Inc.
# This Makefile.am is free software; the Free Software Foundation
# gives unlimited permission to copy and/or distribute it,
# with or without modifications, as long as this notice is preserved.

# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY, to the extent permitted by law; without
# even the implied warranty of MERCHANTABILITY or FITNESS FOR A
# PARTICULAR PURPOSE.


EXTRA_DIST = round_raw_generic.c jyn_asympt.c				\
	amd/mparam.h arm/mparam.h					\
	generic/coverage/mparam.h generic/mparam.h			\
	mips/mparam.h powerpc64/mparam.h sparc64/mparam.h		\
	x86/mparam.h x86_64/core2/mparam.h x86_64/mparam.h

include_HEADERS = mpfr.h mpf2mpfr.h

BUILT_SOURCES = mparam.h

lib_LTLIBRARIES = libmpfr.la

libmpfr_la_SOURCES = mpfr.h mpf2mpfr.h mpfr-cvers.h mpfr-gmp.h          \
mpfr-impl.h mpfr-intmax.h mpfr-longlong.h mpfr-sassert.h mpfr-thread.h 	\
exceptions.c extract.c uceil_exp2.c					\
uceil_log2.c ufloor_log2.c add.c add1.c add_ui.c agm.c clear.c cmp.c	\
cmp_abs.c cmp_si.c cmp_ui.c comparisons.c div_2exp.c div_2si.c		\
div_2ui.c div.c div_ui.c dot.c dump.c eq.c exp10.c exp2.c exp3.c exp.c	\
frac.c frexp.c get_d.c get_exp.c get_str.c init.c inp_str.c isinteger.c	\
isinf.c isnan.c isnum.c const_log2.c log.c modf.c mul_2exp.c mul_2si.c	\
mul_2ui.c mul.c mul_ui.c neg.c next.c out_str.c printf.c vasprintf.c	\
const_pi.c pow.c pow_si.c pow_ui.c print_raw.c print_rnd_mode.c		\
reldiff.c round_prec.c set.c setmax.c setmin.c set_d.c set_dfl_prec.c	\
set_exp.c set_rnd.c set_f.c set_prc_raw.c set_prec.c set_q.c set_si.c	\
set_str.c set_str_raw.c set_ui.c set_z.c sqrt.c sqrt_ui.c sub.c sub1.c	\
sub_ui.c rint.c ui_div.c ui_sub.c urandom.c urandomb.c get_z_exp.c	\
swap.c factorial.c cosh.c sinh.c tanh.c sinh_cosh.c acosh.c asinh.c	\
atanh.c atan.c cmp2.c exp_2.c asin.c const_euler.c cos.c sin.c tan.c	\
fma.c fms.c hypot.c log1p.c expm1.c log2.c log10.c ui_pow.c		\
ui_pow_ui.c minmax.c dim.c signbit.c copysign.c setsign.c gmp_op.c	\
init2.c acos.c sin_cos.c set_nan.c set_inf.c set_zero.c powerof2.c	\
gamma.c set_ld.c get_ld.c cbrt.c volatile.c fits_s.h fits_sshort.c	\
fits_sint.c fits_slong.c fits_u.h fits_ushort.c fits_uint.c		\
fits_ulong.c fits_uintmax.c fits_intmax.c get_si.c get_ui.c zeta.c	\
cmp_d.c erf.c inits.c inits2.c clears.c sgn.c check.c sub1sp.c		\
version.c mpn_exp.c mpfr-gmp.c mp_clz_tab.c sum.c add1sp.c		\
free_cache.c si_op.c cmp_ld.c set_ui_2exp.c set_si_2exp.c set_uj.c	\
set_sj.c get_sj.c get_uj.c get_z.c iszero.c cache.c sqr.c		\
int_ceil_log2.c isqrt.c strtofr.c pow_z.c logging.c mulders.c get_f.c	\
round_p.c erfc.c atan2.c subnormal.c const_catalan.c root.c		\
gen_inverse.h sec.c csc.c cot.c eint.c sech.c csch.c coth.c		\
round_near_x.c constant.c abort_prec_max.c stack_interface.c lngamma.c	\
zeta_ui.c set_d64.c get_d64.c jn.c yn.c rem1.c get_patches.c add_d.c	\
sub_d.c d_sub.c mul_d.c div_d.c d_div.c li2.c rec_sqrt.c min_prec.c	\
buildopt.c digamma.c bernoulli.c isregular.c set_flt.c get_flt.c	\
scale2.c set_z_exp.c ai.c gammaonethird.c ieee_floats.h			\
grandom.c fpif.c set_float128.c get_float128.c rndna.c nrandom.c        \
random_deviate.h random_deviate.c erandom.c mpfr-mini-gmp.c             \
mpfr-mini-gmp.h fmma.c log_ui.c gamma_inc.c ubf.c invert_limb.h 	\
invsqrt_limb.h beta.c odd_p.c get_q.c pool.c total_order.c set_d128.c   \
get_d128.c

libmpfr_la_LIBADD = @LIBOBJS@

# Libtool -version-info CURRENT[:REVISION[:AGE]] for libmpfr.la
#
# 1. No interfaces changed, only implementations (good):
#    ==> Increment REVISION.
# 2. Interfaces added, none removed (good):
#    ==> Increment CURRENT, increment AGE, set REVISION to 0.
# 3. Interfaces removed or changed (BAD, breaks upward compatibility):
#    ==> Increment CURRENT, set AGE and REVISION to 0.
#
#         MPFR     -version-info
#        2.1.x      -
#        2.2.x    1:x:0
#        2.3.x    2:x:1
#        2.4.x    3:x:2
#        3.0.x    4:x:0
#        3.1.x    5:x:1
#        4.0.x    6:x:0
libmpfr_la_LDFLAGS = $(MPFR_LDFLAGS) $(LIBMPFR_LDFLAGS) -version-info 6:0:0

# Important note: If for some reason, srcdir is read-only at build time
# (and you use objdir != srcdir), then you need to rebuild get_patches.c
# (with "make get_patches.c") just after patching the MPFR source. This
# should not be a problem in practice, in particular because "make dist"
# automatically rebuilds get_patches.c before generating the archives.
$(srcdir)/get_patches.c: $(top_srcdir)/PATCHES $(top_srcdir)/tools/get_patches.sh
	(cd $(top_srcdir) && ./tools/get_patches.sh) > $@ || rm -f $@

# Do not add get_patches.c to CLEANFILES so that this file doesn't
# need to be (re)built as long as no patches are applied. Anyway the
# update of this file should be regarded as part of the patch process,
# and "make clean" shouldn't remove it, just like it doesn't remove
# what has been changed by "patch".
#CLEANFILES = get_patches.c

# For check-gmp-symbols
GMPC = $(top_builddir)/src/gmp.c
GMPI = $(top_builddir)/src/gmp.i

# For check-gmp-symbols and check-exported-symbols (if the library does
# not have this name, e.g. on some platforms or when the shared library
# is disabled, these rules do nothing).
LIBMPFRSO = $(top_builddir)/src/.libs/libmpfr.so

# Check that MPFR does not use GMP internal symbols. Of course, do not run
# this rule if you use --with-gmp-build or --enable-gmp-internals. This
# test does nothing if --disable-shared has been used.
# Note: we use a temporary file $(GMPC) instead of "| $(COMPILE) -E -"
# because the latter is not supported by all compilers (at least under
# MS Windows).
check-gmp-symbols: $(LTLIBRARIES)
	if [ -f "$(LIBMPFRSO)" ]; then \
	  printf "#include <%s.h>\n" stdarg stdio gmp > $(GMPC) && \
	  $(COMPILE) -E $(GMPC) > $(GMPI) || exit 1; \
	  internals=`$(NM) -u "$(LIBMPFRSO)" | \
	    $(SED) -n 's/^ *U \(__gmp.*\)/\1/p' | \
	    while read s; \
	    do \
	      $(GREP) -q "$$s[ (;]" $(GMPI) || echo "$$s"; \
	    done`; \
	  if [ -n "$$internals" ]; then \
	    echo "Internal GMP symbols:" $$internals; \
	    exit 1; \
	  fi; \
	  rm $(GMPC) $(GMPI); \
	fi

# Check that MPFR does not define symbols with a GMP reserved prefix.
# For instance, with r11968, and
#   ./configure --with-gmp-build=... CC=tcc
# the symbol __gmpn_clz_tab is defined, which is wrong.
# Note: the "grep -v '@plt$$'" below is for tcc.
check-exported-symbols: $(LTLIBRARIES)
	if [ -f "$(LIBMPFRSO)" ]; then \
	  gsymbols=`$(NM) -gP "$(LIBMPFRSO)" | perl -ne \
	    '/^(__gmp[a-z]?_[_0-9A-Za-z]*) +[A-TV-Z]/ and print " $$1"' | \
	    { grep -v '@plt$$' || true ; }`; \
	  if [ -n "$$gsymbols" ]; then \
	    echo "MPFR defines symbols with a GMP reserved prefix:$$gsymbols"; \
	    exit 1; \
	  fi; \
	fi

CLEANFILES = $(GMPC) $(GMPI)

.PHONY: check-gmp-symbols check-exported-symbols
