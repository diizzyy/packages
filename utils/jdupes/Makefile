#
# Copyright (C) 2019 Daniel Engberg <daniel.engberg.lists@pyret.net>
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=jdupes
PKG_VERSION:=1.13.2
PKG_RELEASE:=1
PKG_MAINTAINER:=
PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=LICENSE

PKG_SOURCE_URL:=https://codeload.github.com/jbruchon/$(PKG_NAME)/tar.gz/v$(PKG_VERSION)?
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_HASH:=41376ace274320a77e35ffed170ff0cbca2cd0cfd0ff1cea53d7464e97d4341f

include $(INCLUDE_DIR)/package.mk

define Package/jdupes
  SUBMENU:=Filesystem
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=Program for identifying and taking actions upon duplicate files
  URL:=https://github.com/jbruchon/jdupes
endef

define Package/jdupes/description
  jdupes is a program for identifying and taking actions upon duplicate files.
  It is a fork of fdupes, but not a drop-in replacement.
endef

TARGET_CFLAGS:= $(filter-out -O%,$(TARGET_CFLAGS))
TARGET_CFLAGS+= -flto
TARGET_LDFLAGS+= -flto -Wl,--gc-sections,--as-needed

ifeq ($(CONFIG_PACKAGE_kmod-fs-btrfs),y)
  TARGET_CFLAGS+= -DENABLE_BTRFS
endif

define Package/jdupes/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/jdupes $(1)/usr/bin/jdupes
endef

$(eval $(call BuildPackage,jdupes))
