#
# Copyright (C) 2019 Daniel Engberg <daniel.engberg.lists@pyret.net>
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=microsocks
PKG_VERSION:=snapshot-20190227
PKG_RELEASE:=1
PKG_MAINTAINER:=
PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=COPYING

PKG_SOURCE_URL:=https://codeload.github.com/rofl0r/$(PKG_NAME)/tar.gz/f94a1c3?dummy=/
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-f94a1c3.tar.gz
PKG_HASH:=bc2bdea06f62848923253eca39fd84a6e16867f0c79b28600c47a295742314d6
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-f94a1c3

include $(INCLUDE_DIR)/package.mk

define Package/microsocks
  SUBMENU:=Web Servers/Proxies
  SECTION:=net
  CATEGORY:=Network
  TITLE:=microsocks
  URL:=https://github.com/rofl0r/microsocks
endef

define Package/microsocks/description
  A multithreaded, small, efficient SOCKS5 server. 
endef

TARGET_CFLAGS+= -flto
TARGET_LDFLAGS+= -flto -Wl,--gc-sections,--as-needed

define Package/microsocks/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/microsocks $(1)/usr/sbin/microsocks
endef

$(eval $(call BuildPackage,microsocks))
