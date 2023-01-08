# SPDX-License-Identifier: GPL-2.0-only
#
# Copyright (C) 2012-2015 OpenWrt.org

include $(TOPDIR)/rules.mk

BOARD:=mvebu
BOARDNAME:=Marvell EBU Armada
FEATURES:=fpu usb pci pcie gpio nand squashfs ramdisk boot-part rootfs-part
SUBTARGETS:=cortexa9 cortexa53 cortexa72

KERNEL_PATCHVER:=5.4
KERNEL_TESTING_PATCHVER:=5.4

include $(INCLUDE_DIR)/target.mk

DEFAULT_PACKAGES += uboot-envtools kmod-gpio-button-hotplug \
htop ca-bundle wget block-mount e2fsprogs cfdisk kmod-usb-storage-extras kmod-fs-ext4 \
luci-app-advanced-reboot luci-app-vlmcsd luci-app-upnp autocore-arm

$(eval $(call BuildTarget))
