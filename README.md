# Hackintosh Z390 AORUS PRO OpenCore guide
Hackintosh on a Z390 AORUS PRO motherboard, Core i9 9900K CPU and RX 5700 XT GPU

## Context

I was used to work with Clover for older builds but I ran into a lot of troubles fixing NVRAM with no success (AptioFix-shit which is automatically managed by OpenCore). So I ended up trying OpenCore for the first time, and guess what? It just works.

## My setup

**Note:** Links are for [Amazon France](https://www.amazon.fr).

| Type | Item |
|:--|:--|
| CPU | [Intel - Core i9 9900K](https://www.amazon.fr/Intel-Core-i9-9900K-Retail-Graphics/dp/B07ZTCVY9M) |
| CPU Cooler | [Noctua - NH-D15](https://www.amazon.fr/Noctua-NH-D15-Refroidisseur-NF-A15-Ventilateur/dp/B00L7UZMAK) |
| Motherboard | [Gigabyte - Z390 AORUS PRO](https://www.amazon.fr/Gigabyte-Z390-AORUS-Socket-LGA1151/dp/B07HS3BV24) |
| RAM | [Patriot Memory Viper Steel DDR4 3000MHz 32Go (2x16Go)](https://www.amazon.fr/dp/B07MV1328Q) |
| Storage | [Samsung - EVO 970 NVMe 1TB](https://www.amazon.fr/Samsung-MZ-V7E1T0BW-970-EVO-Interne/dp/B07CGJNLBB) (for macOS)|
| Storage | [Crucial - MX500 SATA 1TB](https://www.amazon.fr/Crucial-CT1000MX500SSD1-Interne-MX500-Pouces/dp/B077SF8KMG) (for Windows) |
| Storage | 2x [Seagate - IronWolf 2TB](https://www.amazon.fr/Seagate-St2000vnz04-Ironwolf-Interne-1-8-Bay-systèmes/dp/B07H2GY8ZV) |
| GPU | [SAPPHIRE Nitro+ Radeon RX 5700 XT 8G](www.amazon.fr/dp/B07XGV3FL3) |
| Case | [Dune Pro](https://www.dunecase.com) |
| Power supply | [Seasonic - Focus Plus 1000W](https://www.amazon.fr/Seasonic-Focus-Plus-dalimentation-modulaire/dp/B078T1XSJ1) |
| WiFi/Bluetooth module | [Tonysa - BCM943602CS](https://www.amazon.fr/gp/product/B07VT58PH5) |

## What is working and what is not

### Working out of the box (hurray!)

- AirDrop
- APFS
- Sidecar

### Working thanks to kexts and OpenCore configuration

- Audio (even optical output)
- All USB ports (USB 2.0, 3.0, 3.1 Gen 2, USB Type-C)
- App Store
- Apple Music
- iMessages

### Not working

- Handoff (how can I have AirDrop but not Handoff?)
- Netflix DRM in Safari (works with Firefox)

## Step by step guide

The best guide you can find is the [Dortania OpenCore guide](https://dortania.github.io/OpenCore-Desktop-Guide/).

Here is a list of kernel extensions (kext) you will need:

- AppleALC.kext
	- This will enable audio
- IntelMausi.kext
	- This will enable your Ethernet interface
- Lilu.kext
	- This is a dependency for a lot of kexts (like WhateverGreen)
- NVMeFix.kext
- VirtualSMC.kext
	- This will allow macOS to read sensors values
- SMCProcessor.kext
- SMCSuperIO.kext
- USBInjectAll.kext
- WhateverGreen.kext