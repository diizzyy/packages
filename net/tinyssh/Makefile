#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=tinyssh
PKG_VERSION:=20190101
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://codeload.github.com/janmojzis/tinyssh/tar.gz/$(PKG_VERSION)?
PKG_HASH:=554a9a94e53b370f0cd0c5fbbd322c34d1f695cbcea6a6a32dcb8c9f595b3fea

PKG_MAINTAINER:=Rosen Penev <rosenp@gmail.com>
PKG_LICENSE:=CC0
PKG_LICENSE_FILES:=LICENCE

PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

define Package/tinyssh
  SECTION:=net
  CATEGORY:=Network
  TITLE:=TinySSH
  URL:=https://tinyssh.org/
  SUBMENU:=SSH
endef

define Package/tinyssh/description
  TinySSH is a minimalistic SSH server which implements only a subset of SSHv2 features.
endef

define Package/tinyssh/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/build/bin/tinyssh* $(1)/usr/sbin/
endef

$(eval $(call BuildPackage,tinyssh))
