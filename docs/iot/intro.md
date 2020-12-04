---
title: Entwickeln von Apps für IOT-Geräte mit den .net IOT-Bibliotheken
description: Erfahren Sie, wie Sie .net zum Erstellen von Anwendungen für IOT-Geräte und-Szenarien verwenden können.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: overview
ms.prod: dotnet
ms.openlocfilehash: c3d05ec5b05780f91404c3c27e91bcd602b0faeb
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2020
ms.locfileid: "96592076"
---
# <a name="develop-apps-for-iot-devices-with-the-net-iot-libraries"></a>Entwickeln von Apps für IOT-Geräte mit den .net IOT-Bibliotheken

.Net wird auf einer Vielzahl von Plattformen und Architekturen ausgeführt. Allgemeine IOT-Boards (Internet of Things, Internet der Dinge), z. b. Raspberry Pi und hummingboard, werden unterstützt. IOT-apps interagieren in der Regel mit spezieller Hardware, z. b. Sensoren, analog-zu-digital-Konvertern und LCD-Geräten. Die .net IOT-Bibliotheken ermöglichen diese Szenarien.

## <a name="video-overview"></a>Videoübersicht

<!--markdownlint-disable MD034 -->
> [!VIDEO https://channel9.msdn.com/Series/IoT-101/Intro-to-IOT-with-NET-Core-1-of-9/player]

## <a name="libraries"></a>Bibliotheken

Die .net IOT-Bibliotheken bestehen aus zwei nuget-Paketen:

- [System.Device.Gpio](https://www.nuget.org/packages/System.Device.Gpio/) <span class="docon docon-navigate-external x-hidden-focus"></span>
- [Iot.Device.Bindings](https://www.nuget.org/packages/Iot.Device.Bindings/) <span class="docon docon-navigate-external x-hidden-focus"></span>

### <a name="systemdevicegpio"></a>System.Device.Gpio

`System.Device.Gpio` unterstützt eine Vielzahl von Protokollen für die Interaktion mit Hardware-Pins auf niedriger Ebene zum Steuern von Geräten. Dazu gehören:

- E/a für allgemeine Zwecke (GPIO)
- Inter-Integrated Circuit (I2C)
- Schnittstelle der seriellen Peripherie (SPI)
- Pulse Width-Modulation (PWM)
- Serieller Anschluss

### <a name="iotdevicebindings"></a>Iot.Device.Bindings

Das `Iot.Device.Bindings` Paket:

* Enthält [Geräte Bindungen](https://github.com/dotnet/iot/blob/master/src/devices/README.md) <span class="docon docon-navigate-external x-hidden-focus"></span> zum Optimieren der APP-Entwicklung durch Wrapping von System. Device. GPIO.
* Wird von der Community unterstützt, und es werden kontinuierlich weitere Bindungen hinzugefügt.

Zu den häufig verwendeten Geräte Bindungen gehören:

- [Merkmal-LCD-Bildschirm Zeichen Anzeige](https://github.com/dotnet/iot/tree/master/src/devices/CharacterLcd)<span class="docon docon-navigate-external x-hidden-focus"></span>
- [SN74HC595-8-Bit-UMSCHALT Register](https://github.com/dotnet/iot/tree/master/src/devices/Sn74hc595)<span class="docon docon-navigate-external x-hidden-focus"></span>
- [BrickPi3](https://github.com/dotnet/iot/tree/master/src/devices/BrickPi3)<span class="docon docon-navigate-external x-hidden-focus"></span>
- [Max7219-LED-Matrix Treiber](https://github.com/dotnet/iot/tree/master/src/devices/Max7219)<span class="docon docon-navigate-external x-hidden-focus"></span>
- [Rgbledmatrix-RGB-LED-Matrix](https://github.com/dotnet/iot/tree/master/src/devices/RGBLedMatrix)<span class="docon docon-navigate-external x-hidden-focus"></span>

## <a name="supported-operating-systems"></a>Unterstützte Betriebssysteme

`System.Device.Gpio` wird in den meisten Versionen von Linux unterstützt, die Arm/ARM64 und Windows 10 IOT Core unterstützen.

> [!TIP]
> Für Raspberry PI wird ein [Raspberry Pi-Betriebssystem](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) <span class="docon docon-navigate-external x-hidden-focus"></span> (früher raspbian) empfohlen.  

## <a name="supported-hardware-platforms"></a>Unterstützte Hardwareplattformen

`System.Device.Gpio` ist mit den meisten Plattformen mit einem Board kompatibel. Empfohlene Plattformen sind Raspberry PI (2 und höher) und hummingboard. Andere Plattformen, die kompatibel sind, sind "BeagleBoard" und "ODROID".

PC-Plattformen werden durch die Verwendung einer USB-zu-SPI/I2C-Bridge unterstützt.

> [!IMPORTANT]
> .Net wird auf ARMv6-Architektur Geräten, einschließlich Raspberry Pi-und Raspberry Pi-Geräte vor Raspberry Pi 2, nicht unterstützt.

## <a name="resources"></a>Ressourcen

- [.Net-IOT-Bibliotheken auf GitHub](https://github.com/dotnet/iot)<span class="docon docon-navigate-external x-hidden-focus"></span>
