#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=minisatip
PKG_VERSION:=0.7.15
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/catalinii/minisatip.git
PKG_SOURCE_VERSION:=bf6fc469ddd21ed7a74d6c2f77d501fff2231a40

PKG_MAINTAINER:=Daniel Kucera <github@danman.eu>

include $(INCLUDE_DIR)/package.mk

define Package/minisatip
  TITLE:=SATIP server
  URL:=https://github.com/catalinii/minisatip
  SECTION:=multimedia
  CATEGORY:=Multimedia
endef

define Package/minisatip/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/minisatip $(1)/usr/bin/
	$(INSTALL_DIR) $(1)/usr/share/minisatip/html/
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/html/* $(1)/usr/share/minisatip/html
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./files/minisatip.init $(1)/etc/init.d/minisatip
endef

$(eval $(call BuildPackage,minisatip))
