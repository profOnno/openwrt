#
# Copyright (C) 2010-2012 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=jq
PKG_VERSION:=1.4
PKG_RELEASE:=1
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://stedolan.github.io/jq/download/source
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=$(PKG_REV)

PKG_LICENSE:=CC BY 3.0
PKG_LICENSE_FILES:=COPYING
PKG_MAINTAINER:=Menno Vossen <menno.vossen@kuopzi.nl>

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)/$(PKG_NAME)-$(PKG_VERSION)
PKG_INSTALL:=1
#PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

define Package/jq
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=command-line JSON processor
  URL:=http://stedolan.github.io/jq/
endef


define Build/Configure
	$(call Build/Configure/Default,)
endef
TARGET_CFLAGS = -std=c99

define Package/jq/Description
jq is like sed for JSON data.
You can use it to slice and filter and map and transform structured data with the same ease that sed, awk, grep and friends let you play with text.
In this version the bessel functions are disabled by a patch (caused compile errors).
endef

define Package/jq/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/jq $(1)/usr/bin/
endef

$(eval $(call BuildPackage,jq))
