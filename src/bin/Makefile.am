# vim:tw=0:et:ts=4:sw=4
CLEANFILES += src/bin/.libs
EXTRA_DIST += src/bin/getopts_LICENSE.txt

# convenience lib for getopt
noinst_LTLIBRARIES += out/libgetopt.la
out_libgetopt_la_SOURCES = src/bin/getopts.c src/bin/getopts.h
out_libgetopt_la_LDFLAGS = $(AM_LDFLAGS) -static

pkgdatadir = $(datadir)/smbios-utils

# update __VERSION__ variable for python executables
__VERSION__ = $(PACKAGE_VERSION)
REPLACE_VARS += __VERSION__

#
# Python executables
#
if HAVE_PYTHON
dist_sbin_SCRIPTS += src/bin/smbios-token-ctl
DATA_HOOK_REPLACE += $(sbindir)/smbios-token-ctl
nodist_pkgdata_DATA = doc/token_list.csv doc/token_blacklist.csv
man1_MANS += out/scripts/smbios-token-ctl.1

dist_sbin_SCRIPTS += src/bin/smbios-passwd
DATA_HOOK_REPLACE += $(sbindir)/smbios-passwd
man1_MANS += out/scripts/smbios-passwd.1

dist_sbin_SCRIPTS += src/bin/smbios-sys-info
DATA_HOOK_REPLACE += $(sbindir)/smbios-sys-info
man1_MANS += out/scripts/smbios-sys-info.1

dist_sbin_SCRIPTS += src/bin/smbios-wakeup-ctl
DATA_HOOK_REPLACE += $(sbindir)/smbios-wakeup-ctl
man1_MANS += out/scripts/smbios-wakeup-ctl.1

dist_sbin_SCRIPTS += src/bin/smbios-wireless-ctl
DATA_HOOK_REPLACE += $(sbindir)/smbios-wireless-ctl
man1_MANS += out/scripts/smbios-wireless-ctl.1

dist_sbin_SCRIPTS += src/bin/smbios-lcd-brightness
DATA_HOOK_REPLACE += $(sbindir)/smbios-lcd-brightness
man1_MANS += out/scripts/smbios-lcd-brightness.1

dist_sbin_SCRIPTS += src/bin/smbios-keyboard-ctl
DATA_HOOK_REPLACE += $(sbindir)/smbios-keyboard-ctl
man1_MANS += out/scripts/smbios-keyboard-ctl.1

dist_sbin_SCRIPTS += src/bin/smbios-thermal-ctl
DATA_HOOK_REPLACE += $(sbindir)/smbios-thermal-ctl
man1_MANS += out/scripts/smbios-thermal-ctl.1

dist_sbin_SCRIPTS += src/bin/smbios-battery-ctl
DATA_HOOK_REPLACE += $(sbindir)/smbios-battery-ctl
man1_MANS += out/scripts/smbios-battery-ctl.1
endif

#
# C
#
sbin_PROGRAMS += out/smbios-sys-info-lite
out_smbios_sys_info_lite_SOURCES = src/bin/smbios-sys-info-lite.c
out_smbios_sys_info_lite_LDADD = out/libsmbios_c.la out/libgetopt.la $(AM_LDADD)
out_smbios_sys_info_lite_LDFLAGS = $(AM_LDFLAGS) -static
man1_MANS += out/smbios-sys-info-lite.1

sbin_PROGRAMS += out/smbios-get-ut-data
out_smbios_get_ut_data_SOURCES = src/bin/smbios-get-ut-data.c
out_smbios_get_ut_data_LDADD = out/libsmbios_c.la out/libgetopt.la $(AM_LDADD)
man1_MANS += out/smbios-get-ut-data.1

sbin_PROGRAMS += out/smbios-state-byte-ctl
out_smbios_state_byte_ctl_SOURCES = src/bin/smbios-state-byte-ctl.c
out_smbios_state_byte_ctl_LDADD = out/libsmbios_c.la out/libgetopt.la $(AM_LDADD)
man1_MANS += out/smbios-state-byte-ctl.1

sbin_PROGRAMS += out/smbios-upflag-ctl
out_smbios_upflag_ctl_SOURCES = src/bin/smbios-upflag-ctl.c
out_smbios_upflag_ctl_LDADD = out/libsmbios_c.la out/libgetopt.la $(AM_LDADD)
man1_MANS += out/smbios-upflag-ctl.1
