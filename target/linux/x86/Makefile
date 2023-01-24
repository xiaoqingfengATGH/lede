# SPDX-License-Identifier: GPL-2.0-only
#
# Copyright (C) 2006-2011 OpenWrt.org

include $(TOPDIR)/rules.mk

ARCH:=i386
BOARD:=x86
BOARDNAME:=x86
FEATURES:=squashfs vdi vmdk vhdx pcmcia fpu boot-part rootfs-part
SUBTARGETS:=64 generic legacy geode 

KERNEL_PATCHVER:=6.1
KERNEL_TESTING_PATCHVER:=5.4

KERNELNAME:=bzImage

include $(INCLUDE_DIR)/target.mk

#\
DEFAULT_PACKAGES += partx-utils mkf2fs e2fsprogs kmod-button-hotplug kmod-usb-hid kmod-mmc kmod-sdhci kmod-fs-f2fs cfdisk usbutils pciutils \
kmod-alx kmod-e1000e kmod-igb kmod-igc kmod-igbvf kmod-iavf kmod-bnx2x kmod-pcnet32 kmod-tulip kmod-via-velocity kmod-vmxnet3 kmod-i40e kmod-i40evf kmod-r8125 kmod-8139cp kmod-8139too kmod-tg3 \
htop lm-sensors iperf3 autocore-x86 automount autosamba luci-app-adbyby-plus luci-app-ipsec-vpnd luci-proto-bonding luci-app-diskman \
luci-app-unblockmusic luci-app-zerotier luci-app-xlnetacc ddns-scripts_aliyun ddns-scripts_dnspod ca-bundle luci-app-wireguard luci-app-ttyd \
kmod-sound-hda-core kmod-sound-hda-codec-realtek kmod-sound-hda-codec-via kmod-sound-via82xx kmod-sound-hda-intel kmod-sound-hda-codec-hdmi kmod-sound-i8x0 kmod-usb-audio \
kmod-usb-net kmod-usb-net-asix-ax88179 kmod-usb-net-rtl8150 kmod-usb-net-rtl8152-vendor kmod-usb-net-aqc111 kmod-mlx4-core kmod-mlx5-core kmod-drm-i915 kmod-drm-amdgpu

# Home Lede default x86 packages
DEFAULT_PACKAGES += partx-utils mkf2fs e2fsprogs kmod-button-hotplug kmod-usb-hid kmod-mmc kmod-sdhci kmod-fs-f2fs cfdisk usbutils pciutils \
kmod-alx kmod-e1000e kmod-igb kmod-igc kmod-igbvf kmod-iavf kmod-bnx2x kmod-pcnet32 kmod-tulip kmod-via-velocity kmod-vmxnet3 kmod-i40e kmod-i40evf kmod-r8125 kmod-8139cp kmod-8139too kmod-tg3 kmod-ath5k kmod-ath9k kmod-ath9k-htc kmod-ath10k kmod-rt2800-usb kmod-igc kmod-ixgbe kmod-ixgbevf kmod-8139too kmod-fs-f2fs cfdisk \
kmod-sound-hda-core kmod-sound-hda-codec-realtek kmod-sound-hda-codec-via kmod-sound-via82xx kmod-sound-hda-intel kmod-sound-hda-codec-hdmi kmod-sound-i8x0 kmod-usb-audio \
kmod-usb-net kmod-usb-net-asix kmod-usb-net-asix-ax88179 kmod-usb-net-rtl8150 kmod-usb-net-rtl8152-vendor kmod-mlx4-core kmod-r8168 kmod-mlx4-core kmod-mlx5-core kmod-drm-amdgpu \
ath10k-firmware-qca988x ath10k-firmware-qca9888 ath10k-firmware-qca9984 brcmfmac-firmware-43602a1-pcie \
htop lm-sensors autocore-x86 automount autosamba luci-proto-bonding \
ddns-scripts_aliyun ddns-scripts_dnspod ca-certificates \
homelede-autoconfig \
dockerd docker open-vm-tools \
bind-dig subweb unrar unzip dmesg p7zip \
luci-app-aria2 \
luci-theme-infinityfreedom luci-theme-argon-dark-mod luci-theme-netgear luci-theme-opentomato luci-theme-opentomcat \
ipv6helper \
luci-app-accesscontrol luci-app-control-timewol luci-app-control-webrestriction luci-app-control-weburl \
luci-app-samba luci-app-cifs-mount  \
luci-app-dockerman luci-app-hd-idle \
luci-app-homeconnect luci-app-homeredirect \
luci-app-adguardhome luci-app-chinadns-ng luci-app-smartdns \
luci-app-mwan3 luci-app-syncdial \
luci-app-ttyd luci-app-upnp luci-app-vlmcsd luci-app-vsftpd luci-app-watchcat luci-app-wireguard luci-app-wol luci-app-ramfree \
luci-app-jd-dailybonus \
ppp-mod-pppoa ppp-mod-pppoe ppp-mod-pppol2tp ppp-mod-pptp pppossh xl2tpd 

$(eval $(call BuildTarget))

$(eval $(call $(if $(CONFIG_ISO_IMAGES),SetupHostCommand,Ignore),mkisofs, \
	Please install mkisofs. , \
	mkisofs -v 2>&1 , \
	genisoimage -v 2>&1 | grep genisoimage, \
	xorrisofs -v 2>&1 | grep xorriso \
))
