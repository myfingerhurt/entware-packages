#
# Copyright (C) 2006-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=horst
PKG_VERSION:=5.0
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-git.tar.gz
PKG_MIRROR_HASH:=3a677e504e8a1f27c899dfbf39da8c94412b24b08bb2eab0de7807cef07d078b
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_URL:=git://github.com/br101/horst.git
PKG_SOURCE_PROTO:=git
PKG_SOURCE_VERSION:=version-$(PKG_VERSION)

PKG_MAINTAINER:=Bruno Randolf <br1@einfach.org>
PKG_LICENSE:=GPL-2.0+
PKG_LICENSE_FILES:=LICENSE

PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

MAKE_FLAGS += DEBUG=1 LIBNL=0

define Package/horst
	SECTION:=net
	CATEGORY:=Network
	SUBMENU:=wireless
	DEPENDS:=+libncurses
	MAINTAINER:=Bruno Randolf <br1@einfach.org>
	TITLE:=Highly Optimized 802.11 Radio Scanning Tool
	URL:=http://br1.einfach.org/tech/horst/
endef

define Package/horst/description
	[horst] is a scanning and analysis tool for 802.11 wireless networks
	and especially IBSS (ad-hoc) mode and mesh networks (OLSR).
endef

define Package/horst/install
	$(INSTALL_DIR) $(1)/opt/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/horst $(1)/opt/sbin/
endef

$(eval $(call BuildPackage,horst))
