# WARNING: Automatically generated file using BAF (Build system Agnostic File) tooling (version 2.40.3)
# WARNING: You should contribute changes to https://gitlab.com/prpl-foundation/components/ambiorix/bindings/lua/lua-amx/-/blob/main/baf.yml instead
include $(TOPDIR)/rules.mk

PKG_NAME:=lua-amx
RAW_VERSION:=dev_amx_v11
PKG_VERSION:=$(if $(filter v0% v1% v2% v3% v4% v5% v6% v7% v8% v9%,$(RAW_VERSION)),$(patsubst v%,%,$(RAW_VERSION)),$(RAW_VERSION))
SHORT_DESCRIPTION:=LUA AMX Bindings 

PKG_SOURCE_PROTO:=git
PKG_SOURCE_VERSION:=de53846578bb816704a11350a8eea2a5a67c3926
PKG_SOURCE_URL:=https://gitlab.com/prpl-foundation/components/ambiorix/bindings/lua/lua-amx.git
PKG_MIRROR_HASH:=33c9f7c25847b2610b2dcb23623264468e7e740625bbee59e2de301b1c2e3816
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
  URL:=https://gitlab.com/prpl-foundation/components/ambiorix/bindings/lua/lua-amx
  DEPENDS += +libamxc
  DEPENDS += +libamxj
  DEPENDS += +libamxp
  DEPENDS += +libamxd
  DEPENDS += +libamxb
  DEPENDS += +libamxo
  DEPENDS += +lua
  DEPENDS += +libevent2
  MENU:=1
endef

define Package/$(PKG_NAME)/description
	LUA AMX Bindings 
endef

define Build/Compile
	$(call Build/Compile/Default, STAGINGDIR=$(STAGING_DIR) CONFIGDIR=$(STAGING_DIR) PKG_CONFIG_PATH=$(STAGING_DIR)/usr/lib/pkgconfig LIBDIR=/usr/lib INSTALL_LIB_DIR=/lib INSTALL_BIN_DIR=/bin RAW_VERSION=$(RAW_VERSION) HARDCO_HAL_DIR=$(STAGING_DIR)/usr/include PKG_CONFIG=$(PKG_CONFIG) CONFIG_SAH_LUA_AMX_LUA_VERSION_OVERRIDE=$(CONFIG_SAH_LUA_AMX_LUA_VERSION_OVERRIDE) CONFIG_SAH_LUA_AMX_LUA_VERSION=$(CONFIG_SAH_LUA_AMX_LUA_VERSION))
endef

define Build/Install
	$(call Build/Install/Default, install INSTALL=install D=$(PKG_INSTALL_DIR) DEST=$(PKG_INSTALL_DIR) STAGINGDIR=$(STAGING_DIR) CONFIGDIR=$(STAGING_DIR) PV=$(RAW_VERSION) PKG_CONFIG_LIBDIR=$(STAGING_DIR)/usr/lib/pkgconfig LIBDIR=/usr/lib INSTALL_LIB_DIR=/lib INSTALL_BIN_DIR=/bin RAW_VERSION=$(RAW_VERSION) HARDCO_HAL_DIR=$(STAGING_DIR)/usr/include PKG_CONFIG=$(PKG_CONFIG) CONFIG_SAH_LUA_AMX_LUA_VERSION_OVERRIDE=$(CONFIG_SAH_LUA_AMX_LUA_VERSION_OVERRIDE) CONFIG_SAH_LUA_AMX_LUA_VERSION=$(CONFIG_SAH_LUA_AMX_LUA_VERSION))
endef

define Build/InstallDev
	$(call Build/Install/Default, install INSTALL=install D=$(STAGING_DIR) DEST=$(STAGING_DIR) STAGINGDIR=$(STAGING_DIR) CONFIGDIR=$(STAGING_DIR) PV=$(RAW_VERSION) PKG_CONFIG_LIBDIR=$(STAGING_DIR)/usr/lib/pkgconfig LIBDIR=/usr/lib INSTALL_LIB_DIR=/lib INSTALL_BIN_DIR=/bin RAW_VERSION=$(RAW_VERSION) HARDCO_HAL_DIR=$(STAGING_DIR)/usr/include PKG_CONFIG=$(PKG_CONFIG) CONFIG_SAH_LUA_AMX_LUA_VERSION_OVERRIDE=$(CONFIG_SAH_LUA_AMX_LUA_VERSION_OVERRIDE) CONFIG_SAH_LUA_AMX_LUA_VERSION=$(CONFIG_SAH_LUA_AMX_LUA_VERSION))
endef

define Package/$(PKG_NAME)/install
	$(CP) $(PKG_INSTALL_DIR)/* $(1)/
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
