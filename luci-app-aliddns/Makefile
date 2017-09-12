#
# Copyright (C) 2008-2014 The LuCI Team <luci@lists.subsignal.org>
#
# This is free software, licensed under the Apache License, Version 2.0 .
#

include $(TOPDIR)/rules.mk

LUCI_TITLE:=LuCI for Aliddns
LUCI_DEPENDS:=+wget +openssl-util
LUCI_PKGARCH:=all
PKG_VERSION:=1.0
PKG_RELEASE:=1

include $(TOPDIR)/feeds/luci/luci.mk

# call BuildPackage - OpenWrt buildroot signature
define Package/luci-app-aliddn/postinst
#!/bin/sh
[ -n "${IPKG_INSTROOT}" ] || {
( . /etc/uci-defaults/luci-aliddns ) && rm -f /etc/uci-defaults/luci-aliddns
	chmod 755 /etc/init.d/aliddns >/dev/null 2>&1
	chmod 755 /usr/sbin/aliddns >/dev/null 2>&1
exit 0
}
endef

$(eval $(call BuildPackage,luci-app-aliddns))
