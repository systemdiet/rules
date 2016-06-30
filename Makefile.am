ACLOCAL_AMFLAGS = ${ACLOCAL_FLAGS}
AM_MAKEFLAGS = --no-print-directory

SUBDIRS = .

rootprefix=@rootprefix@
udevlibexecdir=$(rootprefix)/lib/udev
udevrulesdir=$(udevlibexecdir)/rules.d

INSTALL_DIRS =
CLEANFILES =
EXTRA_DIST =
INSTALL_EXEC_HOOKS =

INSTALL_DIRS += \
	$(sysconfdir)/udev/rules.d

substitutions = \
		'|rootlibexecdir=$(rootlibexecdir)|'

SED_PROCESS = \
        $(AM_V_GEN)$(MKDIR_P) $(dir $@) && \
        $(SED) $(subst '|,-e 's|@,$(subst =,\@|,$(subst |',|g',$(substitutions)))) \
	< $< > $@

INSTALL_EXEC_HOOKS += \
		      install-directories-hook

install-directories-hook:
	        $(MKDIR_P) $(addprefix $(DESTDIR),$(INSTALL_DIRS))

install-exec-hook: $(INSTALL_EXEC_HOOKS)

DISTCHECK_CONFIGURE_FLAGS = \
	--with-rootprefix=$$dc_install_base

dist_udevrules_DATA =
nodist_udevrules_DATA =

dist_udevrules_DATA += \
	default/42-usb-hid-pm.rules \
	default/50-udev-default.rules \
	default/60-drm.rules \
	default/60-keyboard.rules \
	default/60-persistent-storage-tape.rules \
	default/60-persistent-serial.rules \
	default/60-persistent-input.rules \
	default/60-persistent-alsa.rules \
	default/60-persistent-storage.rules \
	default/64-btrfs.rules \
	default/75-net-description.rules \
	default/75-tty-description.rules \
	default/78-sound-card.rules \
	default/80-net-name-slot.rules \
	default/95-udev-late.rules

nodist_udevrules_DATA += \
	default/99-systemd.rules

EXTRA_DIST += \
	default/99-systemd.rules.in

CLEANFILES += \
	default/99-systemd.rules

dist_udevrules_DATA += \
	default/50-firmware.rules

dist_udevrules_DATA += \
	default/80-drivers.rules

dist_udevrules_DATA += \
	default/60-cdrom_id.rules

dist_udevrules_DATA += \
	default/60-persistent-v4l.rules

dist_udevrules_DATA += \
	default/61-accelerometer.rules

dist_udevrules_DATA += \
	default/75-probe_mtd.rules

dist_udevrules_DATA += \
	default/70-uaccess.rules \
	default/70-power-switch.rules

nodist_udevrules_DATA += \
	default/71-seat.rules \
	default/73-seat-late.rules

 CLEANFILES += \
	default/71-seat.rules \
	default/73-seat-late.rules

 EXTRA_DIST += \
	default/71-seat.rules.in \
	default/73-seat-late.rules.in

%.rules: %.rules.in Makefile
	$(SED_PROCESS)
