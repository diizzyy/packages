#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=tinyssh
PKG_VERSION:=20190216-devel
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://codeload.github.com/janmojzis/$(PKG_NAME)/tar.gz/8fc6eff?dummy=/
PKG_HASH:=c40533679188a8c10d46ebff0f9bf72c68e0b378c4f687e06238e9e4b76b770e
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-8fc6eff

PKG_MAINTAINER:=Rosen Penev <rosenp@gmail.com>
PKG_LICENSE:=CC0
PKG_LICENSE_FILES:=LICENCE

PKG_BUILD_PARALLEL:=1
PKG_USE_MIPS16:=0

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

# TARGET_CFLAGS := $(filter-out -O%,$(TARGET_CFLAGS))
# TARGET_CFLAGS += -O2 -Wall -fwrapv -fno-strict-overflow -fomit-frame-pointer
TARGET_CFLAGS += -Wall -fwrapv -fno-strict-overflow -fomit-frame-pointer

define Package/tinyssh/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/build/bin/tinyssh* $(1)/usr/sbin/
endef

$(eval $(call BuildPackage,tinyssh))
