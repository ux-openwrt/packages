#
# Copyright (C) 2006-2010 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=sftpserver
PKG_VERSION:=0.2.2
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://www.greenend.org.uk/rjk/sftpserver/
PKG_MD5SUM:=0f5c4bda37ea16c6f075646e460cf060
PKG_LICENSE:=GPLv2

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/nls.mk

define Package/gesftpserver
  SECTION:=net
  CATEGORY:=Network
  SUBMENU:=SSH
  DEPENDS:=+libpthread $(ICONV_DEPENDS)
  TITLE:=SFTP server
  URL:=http://www.greenend.org.uk/rjk/sftpserver/
endef

define Package/gesftpserver/description
This is an experimental free SFTP server. It is currently still under development
(so don't trust it with critical data). It should be possible to use it as a
drop-in replacement for the widely-used OpenSSH SFTP server. It does not include
an SSH server, but rather runs as a subsystem of one.
endef

define Package/gesftpserver/install	
	$(INSTALL_DIR) $(1)/usr/libexec
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/gesftpserver $(1)/usr/libexec/sftp-server
endef

$(eval $(call BuildPackage,gesftpserver))
