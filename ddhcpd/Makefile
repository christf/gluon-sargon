include $(TOPDIR)/rules.mk

PKG_NAME:=ddhcpd
PKG_VERSION:=2017-12-30

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/christf/ddhcpd
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=1c39ccb7408a03058b19c38c7d8ed836e1a93b87
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz

PKG_BUILD_PARALLEL:=1
PKG_INSTALL:=1

TARGET_CFLAGS += -DLOG_LEVEL=20 

include $(INCLUDE_DIR)/package.mk

define Package/ddhcpd
  SECTION:=net
  CATEGORY:=Network
  TITLE:=ddhcpd
endef

define Package/ddhcpd/description
 distributed dhcp server
endef

define Package/ddhcpd/install
	$(CP) ./files/* $(1)
	mkdir -p $(1)/usr/sbin/
	$(CP) $(PKG_BUILD_DIR)/ddhcpd  $(1)/usr/sbin/
	$(CP) $(PKG_BUILD_DIR)/ddhcpdctl $(1)/usr/sbin/
endef

$(eval $(call BuildPackage,ddhcpd))
