#
# Copyright (C) 2018 Daniel Engberg <daniel.engberg.lists@pyret.net>
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=socks-libevent
PKG_VERSION:=snapshot-20170423
PKG_RELEASE:=1
PKG_MAINTAINER:=
PKG_LICENSE:=BSD-3-Clause
PKG_LICENSE_FILES:=LICENSE.md

PKG_SOURCE_URL:=https://codeload.github.com/Mirraz/$(PKG_NAME)/tar.gz/c5bfd02?dummy=/
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-c5bfd02.tar.gz
PKG_HASH:=99439967210c832cc5e30c13228d250299a565f22db0a89e68ad7757aa515071
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-c5bfd02

include $(INCLUDE_DIR)/package.mk

define Package/socks-libevent
  SUBMENU:=Web Servers/Proxies
  SECTION:=net
  CATEGORY:=Network
  DEPENDS:=+libevent2-core +libevent2-extra
  TITLE:=socks-libevent
  URL:=https://github.com/Mirraz/socks-libevent/
endef

define Package/socks-libevent/description
  SOCKSv5 server implementation based on libevent 
endef

TARGET_LDFLAGS+= -Wl,--gc-sections,--as-needed

define Package/socks-libevent/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/socks_server_libevent $(1)/usr/sbin/socks-libevent-server
endef

$(eval $(call BuildPackage,socks-libevent))
