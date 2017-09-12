#
# Copyright (C) 2008-2014 The LuCI Team <luci@lists.subsignal.org>
#
# This is free software, licensed under the Apache License, Version 2.0 .
#

include $(TOPDIR)/rules.mk

LUCI_TITLE:=LuCI for SSR Server Python
LUCI_DEPENDS:=+python
LUCI_PKGARCH:=all
PKG_VERSION:=3.2.0
PKG_RELEASE:=3

include $(TOPDIR)/feeds/luci/luci.mk

# call BuildPackage - OpenWrt buildroot signature

define Package/luci-ssrserver-python/postinst
#!/bin/sh
[ -n "${IPKG_INSTROOT}" ] || {
( . /etc/uci-defaults/luci-ssrserver-python ) && rm -f /etc/uci-defaults/luci-ssrserver-python
	chmod 755 /etc/init.d/ssr_server >/dev/null 2>&1
exit 0
}
endef

$(eval $(call BuildPackage,luci-app-ssrserver-python))
