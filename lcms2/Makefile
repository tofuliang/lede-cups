# Copyright (C) 2007-2013 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=lcms2
PKG_VERSION:=2.12
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/mm2/Little-CMS/releases/download/lcms$(PKG_VERSION)/
PKG_MD5SUM:=8cb583c8447461896320b43ea9a688e0

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/lcms2
  SECTION:=net
  CATEGORY:=Network
  SUBMENU:=Printing
  TITLE:=Little CMS color engine
  DEPENDS:=+libtiff +libjpeg +zlib
  URL:=http://www.littlecms.com/
endef

define Package/lcms2/description
	Little CMS color engine
endef

define Package/lcms2/install
	$(INSTALL_DIR) $(1)/usr/bin $(1)/usr/lib
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/* $(1)/usr/bin/
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/* $(1)/usr/lib/
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/include/* $(1)/usr/include/
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/* $(1)/usr/lib
endef

$(eval $(call BuildPackage,lcms2))
