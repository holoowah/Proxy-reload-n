# Proxy Reload — Android Studio prototype

This project creates a basic Android app with a persistent notification containing **RELOAD** and **STOP** actions, plus fields for proxy type, host/IP, port, username and password.

## Important limitation
This is a UI/service prototype, **not yet a working proxy client**. The RELOAD action currently reports that reload was requested; it does not reconnect a real tunnel. To route phone/app traffic, a compatible VPN/tun2socks engine must be integrated, with explicit Android `VpnService` consent, proper lifecycle handling, DNS/IPv6 handling, authentication, and device testing. Do not use it as a functioning proxy until that integration is complete.

## Build
1. Install Android Studio on a computer.
2. Open this folder as an existing Gradle project.
3. Let Gradle sync, then build an APK from **Build > Build Bundle(s) / APK(s) > Build APK(s)**.
4. Test on an Android device. Android 13+ requires notification permission.

## Current prototype features
- Proxy type selector (SOCKS5 / HTTP)
- Host/IP, port, username and password fields
- Saves configuration locally on the device
- Persistent notification with RELOAD and STOP buttons
- Foreground service scaffold

## Not included yet
- Real proxy tunnel or VPN routing
- START button after STOP (reopen app and start the service)
- Automatic reconnection/watchdog
- End-to-end tests for IPv4, IPv6, HTTP and SOCKS5
