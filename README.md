# WifiDirectPlus (fixed)

Wi-Fi Direct sharing + hotspot control + daily schedules + local control website. minSdk 24 (Android 7).

## Build on GitHub
Push to `main` > Actions tab > "Android CI" > download artifact `WifiDirectPlus-debug-apk`.

## How sharing works (no root)
Wi-Fi Direct / hotspot give the other phone a Wi-Fi link. Internet is relayed by a proxy inside the app
(port 8282). On the other phone: Wi-Fi > the network > Proxy > Manual > Host = phone IP (Wi-Fi Direct
usually 192.168.49.1), Port 8282 - or Auto-config `http://IP:8080/proxy.pac`.
Apps that ignore the Wi-Fi proxy setting will not get internet. (Android 7 system hotspot is real tethering: no proxy needed.)

## Hotspot
- Android 7.x: real system hotspot switched by the app (grant "modify system settings").
- Android 8+: Google blocks apps from the system hotspot. The app runs its own hotspot (fully on/off + schedulable);
  clients use the proxy. Needs Location ON (and Nearby devices permission on Android 13+).

## Schedules
Four independent daily schedules: Direct ON/OFF, Hotspot ON/OFF. Saved, re-armed after reboot.
On Android 12+ allow "exact alarms"; allow background running for best reliability.

## Control website
`http://IP:8080` from a phone on the shared network, PIN shown in the app. Turn Direct/Hotspot on/off, edit schedules.
# WifiDirectPlus
# WifiDirectPlus
