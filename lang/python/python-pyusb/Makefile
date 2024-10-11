#
# Copyright (C) 2024 TDT AG <development@tdt.de>
#
# This is free software, licensed under the GNU General Public License v2.
# See https://www.gnu.org/licenses/gpl-2.0.txt for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python-pyusb
PKG_VERSION:=1.2.1
PKG_RELEASE:=1

PYPI_NAME:=pyusb
PKG_HASH:=a4cc7404a203144754164b8b40994e2849fde1cfff06b08492f12fff9d9de7b9

PKG_MAINTAINER:=Lukas Voegl <lvoegl@tdt.de>
PKG_LICENSE:=BSD-3-Clause
PKG_LICENSE_FILES:=LICENSE

include ../pypi.mk
include $(INCLUDE_DIR)/package.mk
include ../python3-package.mk

define Package/python3-pyusb
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=PyUSB
  URL:=https://github.com/pyusb/pyusb
  DEPENDS:= \
    +python3 \
    +libusb-1.0
endef

define Package/python3-pyusb/description
  PyUSB provides for easy access to the host machine's Universal Serial Bus
  (USB) system for Python 3.
endef

$(eval $(call Py3Package,python3-pyusb))
$(eval $(call BuildPackage,python3-pyusb))
$(eval $(call BuildPackage,python3-pyusb-src))
