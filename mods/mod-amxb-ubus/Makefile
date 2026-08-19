# WARNING: Automatically generated file using BAF (Build system Agnostic File) tooling (version 2.40.6)
# WARNING: You should contribute changes to https://gitlab.com/prpl-foundation/components/ambiorix/modules/amxb_backends/amxb_ubus/-/blob/main/baf.yml instead
include $(TOPDIR)/rules.mk

PKG_NAME:=mod-amxb-ubus
RAW_VERSION:=dev_amx_v11
PKG_VERSION:=$(if $(filter v0% v1% v2% v3% v4% v5% v6% v7% v8% v9%,$(RAW_VERSION)),$(patsubst v%,%,$(RAW_VERSION)),$(RAW_VERSION))
SHORT_DESCRIPTION:=Ubus Backend

PKG_SOURCE_PROTO:=git
PKG_SOURCE_VERSION:=94253172aa4a6ba582e9a9d33e1b6ad0982c2f8e
PKG_SOURCE_URL:=https://gitlab.com/prpl-foundation/components/ambiorix/modules/amxb_backends/amxb_ubus.git
PKG_MIRROR_HASH:=7793cbd6c7c2d7c7acacc4691b7c910ec44e1d31ee756de4e094fe258cbf49a0
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
PKG_MAINTAINER:=Soft At Home <support.opensource@softathome.com>
PKG_LICENSE:=BSD-2-Clause-Patent
PKG_LICENSE_FILES:=LICENSE


PKG_RELEASE:=1

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
  CATEGORY:=prpl Foundation
  SUBMENU:=Ambiorix
  TITLE:=$(SHORT_DESCRIPTION)
  URL:=https://gitlab.com/prpl-foundation/components/ambiorix/modules/amxb_backends/amxb_ubus
  DEPENDS += +libamxc
  DEPENDS += +libamxb
  DEPENDS += +libamxd
  DEPENDS += +ubus
  MENU:=1
endef

define Package/$(PKG_NAME)/description
	Ubus Backend
endef

define Build/Compile
	$(call Build/Compile/Default, STAGINGDIR=$(STAGING_DIR) CONFIGDIR=$(STAGING_DIR) PKG_CONFIG_PATH=$(STAGING_DIR)/usr/lib/pkgconfig LIBDIR=/usr/lib INSTALL_LIB_DIR=/lib INSTALL_BIN_DIR=/bin RAW_VERSION=$(RAW_VERSION) HARDCO_HAL_DIR=$(STAGING_DIR)/usr/include PKG_CONFIG=$(PKG_CONFIG) CONFIG_SAH_LIB_AMXB_UBUS_ORDER=$(CONFIG_SAH_LIB_AMXB_UBUS_ORDER))
endef

define Build/Install
	$(call Build/Install/Default, install INSTALL=install D=$(PKG_INSTALL_DIR) DEST=$(PKG_INSTALL_DIR) STAGINGDIR=$(STAGING_DIR) CONFIGDIR=$(STAGING_DIR) PV=$(RAW_VERSION) PKG_CONFIG_LIBDIR=$(STAGING_DIR)/usr/lib/pkgconfig LIBDIR=/usr/lib INSTALL_LIB_DIR=/lib INSTALL_BIN_DIR=/bin RAW_VERSION=$(RAW_VERSION) HARDCO_HAL_DIR=$(STAGING_DIR)/usr/include PKG_CONFIG=$(PKG_CONFIG) CONFIG_SAH_LIB_AMXB_UBUS_ORDER=$(CONFIG_SAH_LIB_AMXB_UBUS_ORDER))
endef

define Build/InstallDev
	$(call Build/Install/Default, install INSTALL=install D=$(STAGING_DIR) DEST=$(STAGING_DIR) STAGINGDIR=$(STAGING_DIR) CONFIGDIR=$(STAGING_DIR) PV=$(RAW_VERSION) PKG_CONFIG_LIBDIR=$(STAGING_DIR)/usr/lib/pkgconfig LIBDIR=/usr/lib INSTALL_LIB_DIR=/lib INSTALL_BIN_DIR=/bin RAW_VERSION=$(RAW_VERSION) HARDCO_HAL_DIR=$(STAGING_DIR)/usr/include PKG_CONFIG=$(PKG_CONFIG) CONFIG_SAH_LIB_AMXB_UBUS_ORDER=$(CONFIG_SAH_LIB_AMXB_UBUS_ORDER))
endef

define Package/$(PKG_NAME)/install
	if [ -d $(PKG_INSTALL_DIR) ]; then \
		$(CP) $(PKG_INSTALL_DIR)/* $(1)/; \
	fi
	if [ -d ./files ]; then \
		$(CP) ./files/* $(1)/; \
	fi
	find $(1) -name *.a -exec rm {} +;
	find $(1) -name *.h -exec rm {} +;
	find $(1) -name *.pc -exec rm {} +;
endef

define Package/$(PKG_NAME)/config
	source "$(SOURCE)/Config.in"
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
