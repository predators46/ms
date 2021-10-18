#
# Copyright (C) 2021 Jo-Philipp Wich <jo@mein.io>
#

include $(TOPDIR)/rules.mk

PKG_NAME:=firewall4
PKG_RELEASE:=$(AUTORELEASE)

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL=$(PROJECT_GIT)/project/firewall4.git
PKG_SOURCE_DATE:=2021-11-25
PKG_SOURCE_VERSION:=1cee4dd4c6ceb58e12ca230d3d5889c4d848dc76
PKG_MIRROR_HASH:=de9065b40c40653820ff09b7f3e31216ae7adf0183a253def911125ff17ce973
PKG_MAINTAINER:=Jo-Philipp Wich <jo@mein.io>
PKG_LICENSE:=ISC

include $(INCLUDE_DIR)/package.mk

define Package/firewall4
  SECTION:=net
  CATEGORY:=Base system
  TITLE:=OpenWrt 4th gen firewall
  DEPENDS:=+ \
	+kmod-nft-core +kmod-nft-fib +kmod-nft-offload \
	+kmod-nft-nat +kmod-nft-nat6 \
	+nftables-json \
	+ucode +ucode-mod-fs +ucode-mod-ubus +ucode-mod-uci
  PROVIDES:=uci-firewall
endef

define Package/firewall4/description
 This package provides an nftables-based implementation of the UCI firewall
 sharing the same configuration format.
endef

define Package/firewall4/conffiles
/etc/config/firewall
/etc/nftables.d/
endef

define Package/firewall4/install
	$(CP) -a $(PKG_BUILD_DIR)/root/* $(1)/
endef

define Build/Compile
endef

$(eval $(call BuildPackage,firewall4))
