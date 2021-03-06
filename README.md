Reghack on wdr4310v1
================================================================

## Warning
* Using this improperly may violate the radio regulations of your country. Only use it when restrictions in your router are stricter than the regulations.
* ~~For some reason, some channels like 14 in 2.4g and 100 in 5g are not working even with these patches. It is either due to other restrictions in drivers or hardwares, or my computer and phone simply do not detect signals at those channels.~~ Channel 14 is actually working, just not visible for most clients. Though not sure about channel 100.
* Boosting tx power from 24 dBm to 30 dBm backfires. In my case at 5g it resulted in worse transmitting rate (from 260 Mbps to 150 Mbps).
* ART files are only for my own device. It is better to generate it for youself by using [BigNerd95/ARTool](https://github.com/BigNerd95/ARTool), or use the patch at [Atheros ART bypass reading the modified dump from /etc/config/my_eeprom](https://gist.github.com/BigNerd95/f06f14d46fa76ccaf519940592428c53).

## Usage

1. Select patch file according to your version. Some patch files with extension `.patch-${version}` are version diversified. You need to manually select one, rename its extension to `.patch` and delete other versions.
2. Put patches into their Makefile directory (when using buildroot) or manually apply them.

## Tested Versions

These patches are tested against the following versions. Newer versions may work as well.

| package | version | commit |
|---|---|---|
| mac80211 | kernel 4.19.85-1 & 5.4.27-1 |  |
| hostapd | 2019-08-08 | ca8c2bd28ad53f431d6ee60ef754e98cfdb4c17b |
| wireless-regdb | 2017-10-20 | 4343d359ed5e7404de8803a74df186457b26ab79 |

## References
* [bittorf/kalua](https://github.com/bittorf/kalua/tree/master/openwrt-patches/reghack)
* [BigNerd95/ARTool](https://github.com/BigNerd95/ARTool)
* [How to restore ART partition](https://openwrt.org/docs/guide-user/installation/restore_art_partition)
* [Atheros ART power limit bypass, linux regulatory will be applied](https://gist.github.com/BigNerd95/6ad73f59e19169ac0f95dbf3b9a272ac)
* [Atheros Country Code ART bypass passing a custom Country Name when loading the driver ](https://gist.github.com/BigNerd95/0be0a5b52a16524a78fc768f0d208a74)
* [Atheros ART bypass reading the modified dump from /etc/config/my_eeprom](https://gist.github.com/BigNerd95/f06f14d46fa76ccaf519940592428c53)
* [[OpenWrt-Devel] [OpenWrt-Users] Compile OpenWRT with channels from 2.3 GHz - 2.7 GHz to Ubiquiti (ar71xx)](https://www.mail-archive.com/openwrt-devel@lists.openwrt.org/msg40873.html)
* [Using WiFi Atheros chips in hamradio bands](http://yo3iiu.ro/blog/?p=1301)
* [Modifying Consumer Off the Shelf Wireless LAN devices for specialized amateur use](https://www.qsl.net/kb9mwr/projects/wireless/modify.html#atheros)
* [List of WLAN channels](https://en.wikipedia.org/wiki/List_of_WLAN_channels)
* [802.11 Wi-Fi Physical Layer and Transmitter Measurements](https://download.tek.com/document/Online%20version%2037W-29687-0%20802.11_WiFi_Poster_HR.pdf)