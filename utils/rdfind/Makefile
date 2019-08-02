#
# Copyright (C) 2019 Daniel Engberg <daniel.engberg.lists@pyret.net>
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=rdfind
PKG_VERSION:=1.4.1
PKG_RELEASE:=1
PKG_MAINTAINER:=
PKG_LICENSE:=GPL-2.0-or-later
PKG_LICENSE_FILES:=COPYING

PKG_SOURCE_URL:=https://rdfind.pauldreik.se
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_HASH:=30c613ec26eba48b188d2520cfbe64244f3b1a541e60909ce9ed2efb381f5e8c

PKG_FIXUP:=autoreconf
PKG_FIXUP:=patch-libtool
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/rdfind
  SUBMENU:=Filesystem
  SECTION:=utils
  CATEGORY:=Utilities
  DEPENDS:=+libstdcpp +libnettle
  TITLE:=A program that finds duplicate files
  URL:=https://rdfind.pauldreik.se/
endef

define Package/rdfind/description
  Rdfind is a program that finds duplicate files. It is useful for compressing
  backup directories or just finding duplicate files. It compares files based
  on their content, NOT on their file names.
endef

TARGET_CFLAGS+= -flto
TARGET_LDFLAGS+= -flto -Wl,--gc-sections,--as-needed

define Package/rdfind/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/rdfind $(1)/usr/bin/rdfind
endef

$(eval $(call BuildPackage,rdfind))
