include $(TOPDIR)/rules.mk

PKG_NAME:=rsa
PKG_VERSION:=4.0
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/source/r/rsa
PKG_HASH:=1a836406405730121ae9823e19c6e806c62bbad73f890574fff50efa4122c487
PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-rsa-$(PKG_VERSION)

PKG_MAINTAINER:=Daniel Danzberger <daniel@dd-wrt.com>
PKG_LICENSE:=MIT

include $(INCLUDE_DIR)/package.mk
include ../python-package.mk
include ../python3-package.mk

PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

define Package/python-rsa/Default
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=rsa
  URL:=https://stuvel.eu/rsa
endef

define Package/python-rsa
$(call Package/python-rsa/Default)
  DEPENDS:=+python +python-pyasn1
  VARIANT:=python
endef

define Package/python3-rsa
$(call Package/python-rsa/Default)
  DEPENDS:=+python3 +python3-pyasn1
  VARIANT:=python3
endef

define Package/python-rsa/description
  Is a pure-Python RSA implementation. It supports encryption and decryption,
  signing and verifying signatures, and key generation according to PKCS#1 version 1.5.
  It can be used as a Python library as well as on the commandline. 
endef

define Package/python3-rsa/description
$(call Package/python-rsa/description)
.
(Variant for Python3)
endef

$(eval $(call PyPackage,python-rsa))
$(eval $(call BuildPackage,python-rsa))
$(eval $(call BuildPackage,python-rsa-src))

$(eval $(call Py3Package,python3-rsa))
$(eval $(call BuildPackage,python3-rsa))
$(eval $(call BuildPackage,python3-rsa-src))
