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
# <a name="develop-apps-for-iot-devices-with-the-net-iot-libraries"></a><span data-ttu-id="e4353-103">Entwickeln von Apps für IOT-Geräte mit den .net IOT-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="e4353-103">Develop apps for IoT devices with the .NET IoT Libraries</span></span>

<span data-ttu-id="e4353-104">.Net wird auf einer Vielzahl von Plattformen und Architekturen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e4353-104">.NET runs on a variety of platforms and architectures.</span></span> <span data-ttu-id="e4353-105">Allgemeine IOT-Boards (Internet of Things, Internet der Dinge), z. b. Raspberry Pi und hummingboard, werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e4353-105">Common Internet of things (IoT) boards, such as Raspberry Pi and Hummingboard, are supported.</span></span> <span data-ttu-id="e4353-106">IOT-apps interagieren in der Regel mit spezieller Hardware, z. b. Sensoren, analog-zu-digital-Konvertern und LCD-Geräten.</span><span class="sxs-lookup"><span data-stu-id="e4353-106">IoT apps typically interact with specialized hardware, such as sensors, analog-to-digital converters, and LCD devices.</span></span> <span data-ttu-id="e4353-107">Die .net IOT-Bibliotheken ermöglichen diese Szenarien.</span><span class="sxs-lookup"><span data-stu-id="e4353-107">The .NET IoT Libraries enable these scenarios.</span></span>

## <a name="video-overview"></a><span data-ttu-id="e4353-108">Videoübersicht</span><span class="sxs-lookup"><span data-stu-id="e4353-108">Video overview</span></span>

<!--markdownlint-disable MD034 -->
> [!VIDEO https://channel9.msdn.com/Series/IoT-101/Intro-to-IOT-with-NET-Core-1-of-9/player]

## <a name="libraries"></a><span data-ttu-id="e4353-109">Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="e4353-109">Libraries</span></span>

<span data-ttu-id="e4353-110">Die .net IOT-Bibliotheken bestehen aus zwei nuget-Paketen:</span><span class="sxs-lookup"><span data-stu-id="e4353-110">The .NET IoT Libraries are composed of two NuGet packages:</span></span>

- <span data-ttu-id="e4353-111">[System.Device.Gpio](https://www.nuget.org/packages/System.Device.Gpio/) <span class="docon docon-navigate-external x-hidden-focus"></span></span><span class="sxs-lookup"><span data-stu-id="e4353-111">[System.Device.Gpio](https://www.nuget.org/packages/System.Device.Gpio/) <span class="docon docon-navigate-external x-hidden-focus"></span></span></span>
- <span data-ttu-id="e4353-112">[Iot.Device.Bindings](https://www.nuget.org/packages/Iot.Device.Bindings/) <span class="docon docon-navigate-external x-hidden-focus"></span></span><span class="sxs-lookup"><span data-stu-id="e4353-112">[Iot.Device.Bindings](https://www.nuget.org/packages/Iot.Device.Bindings/) <span class="docon docon-navigate-external x-hidden-focus"></span></span></span>

### <a name="systemdevicegpio"></a><span data-ttu-id="e4353-113">System.Device.Gpio</span><span class="sxs-lookup"><span data-stu-id="e4353-113">System.Device.Gpio</span></span>

<span data-ttu-id="e4353-114">`System.Device.Gpio` unterstützt eine Vielzahl von Protokollen für die Interaktion mit Hardware-Pins auf niedriger Ebene zum Steuern von Geräten.</span><span class="sxs-lookup"><span data-stu-id="e4353-114">`System.Device.Gpio` supports a variety of protocols for interacting with low-level hardware pins to control devices.</span></span> <span data-ttu-id="e4353-115">Dazu gehören:</span><span class="sxs-lookup"><span data-stu-id="e4353-115">These include:</span></span>

- <span data-ttu-id="e4353-116">E/a für allgemeine Zwecke (GPIO)</span><span class="sxs-lookup"><span data-stu-id="e4353-116">General-purpose I/O (GPIO)</span></span>
- <span data-ttu-id="e4353-117">Inter-Integrated Circuit (I2C)</span><span class="sxs-lookup"><span data-stu-id="e4353-117">Inter-Integrated Circuit (I2C)</span></span>
- <span data-ttu-id="e4353-118">Schnittstelle der seriellen Peripherie (SPI)</span><span class="sxs-lookup"><span data-stu-id="e4353-118">Serial Peripheral Interface (SPI)</span></span>
- <span data-ttu-id="e4353-119">Pulse Width-Modulation (PWM)</span><span class="sxs-lookup"><span data-stu-id="e4353-119">Pulse Width Modulation (PWM)</span></span>
- <span data-ttu-id="e4353-120">Serieller Anschluss</span><span class="sxs-lookup"><span data-stu-id="e4353-120">Serial port</span></span>

### <a name="iotdevicebindings"></a><span data-ttu-id="e4353-121">Iot.Device.Bindings</span><span class="sxs-lookup"><span data-stu-id="e4353-121">Iot.Device.Bindings</span></span>

<span data-ttu-id="e4353-122">Das `Iot.Device.Bindings` Paket:</span><span class="sxs-lookup"><span data-stu-id="e4353-122">The `Iot.Device.Bindings` package:</span></span>

* <span data-ttu-id="e4353-123">Enthält [Geräte Bindungen](https://github.com/dotnet/iot/blob/master/src/devices/README.md) <span class="docon docon-navigate-external x-hidden-focus"></span> zum Optimieren der APP-Entwicklung durch Wrapping von System. Device. GPIO.</span><span class="sxs-lookup"><span data-stu-id="e4353-123">Contains [device bindings](https://github.com/dotnet/iot/blob/master/src/devices/README.md) <span class="docon docon-navigate-external x-hidden-focus"></span> to streamline app development by wrapping System.Device.Gpio.</span></span>
* <span data-ttu-id="e4353-124">Wird von der Community unterstützt, und es werden kontinuierlich weitere Bindungen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e4353-124">Is community-supported, and additional bindings are added continually.</span></span>

<span data-ttu-id="e4353-125">Zu den häufig verwendeten Geräte Bindungen gehören:</span><span class="sxs-lookup"><span data-stu-id="e4353-125">Commonly used device bindings include:</span></span>

- <span data-ttu-id="e4353-126">[Merkmal-LCD-Bildschirm Zeichen Anzeige](https://github.com/dotnet/iot/tree/master/src/devices/CharacterLcd)<span class="docon docon-navigate-external x-hidden-focus"></span></span><span class="sxs-lookup"><span data-stu-id="e4353-126">[CharacterLcd - LCD character display](https://github.com/dotnet/iot/tree/master/src/devices/CharacterLcd) <span class="docon docon-navigate-external x-hidden-focus"></span></span></span>
- <span data-ttu-id="e4353-127">[SN74HC595-8-Bit-UMSCHALT Register](https://github.com/dotnet/iot/tree/master/src/devices/Sn74hc595)<span class="docon docon-navigate-external x-hidden-focus"></span></span><span class="sxs-lookup"><span data-stu-id="e4353-127">[SN74HC595 - 8-bit shift register](https://github.com/dotnet/iot/tree/master/src/devices/Sn74hc595) <span class="docon docon-navigate-external x-hidden-focus"></span></span></span>
- <span data-ttu-id="e4353-128">[BrickPi3](https://github.com/dotnet/iot/tree/master/src/devices/BrickPi3)<span class="docon docon-navigate-external x-hidden-focus"></span></span><span class="sxs-lookup"><span data-stu-id="e4353-128">[BrickPi3](https://github.com/dotnet/iot/tree/master/src/devices/BrickPi3) <span class="docon docon-navigate-external x-hidden-focus"></span></span></span>
- <span data-ttu-id="e4353-129">[Max7219-LED-Matrix Treiber](https://github.com/dotnet/iot/tree/master/src/devices/Max7219)<span class="docon docon-navigate-external x-hidden-focus"></span></span><span class="sxs-lookup"><span data-stu-id="e4353-129">[Max7219 - LED Matrix driver](https://github.com/dotnet/iot/tree/master/src/devices/Max7219) <span class="docon docon-navigate-external x-hidden-focus"></span></span></span>
- <span data-ttu-id="e4353-130">[Rgbledmatrix-RGB-LED-Matrix](https://github.com/dotnet/iot/tree/master/src/devices/RGBLedMatrix)<span class="docon docon-navigate-external x-hidden-focus"></span></span><span class="sxs-lookup"><span data-stu-id="e4353-130">[RGBLedMatrix - RGB LED Matrix](https://github.com/dotnet/iot/tree/master/src/devices/RGBLedMatrix) <span class="docon docon-navigate-external x-hidden-focus"></span></span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="e4353-131">Unterstützte Betriebssysteme</span><span class="sxs-lookup"><span data-stu-id="e4353-131">Supported operating systems</span></span>

<span data-ttu-id="e4353-132">`System.Device.Gpio` wird in den meisten Versionen von Linux unterstützt, die Arm/ARM64 und Windows 10 IOT Core unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e4353-132">`System.Device.Gpio` is supported on most versions of Linux that support ARM/ARM64 and Windows 10 IoT Core.</span></span>

> [!TIP]
> <span data-ttu-id="e4353-133">Für Raspberry PI wird ein [Raspberry Pi-Betriebssystem](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) <span class="docon docon-navigate-external x-hidden-focus"></span> (früher raspbian) empfohlen.  </span><span class="sxs-lookup"><span data-stu-id="e4353-133">For Raspberry Pi, [Raspberry Pi OS](https://www.raspberrypi.org/documentation/installation/installing-images/README.md)  <span class="docon docon-navigate-external x-hidden-focus"></span> (formerly Raspbian) is recommended.</span></span>

## <a name="supported-hardware-platforms"></a><span data-ttu-id="e4353-134">Unterstützte Hardwareplattformen</span><span class="sxs-lookup"><span data-stu-id="e4353-134">Supported hardware platforms</span></span>

<span data-ttu-id="e4353-135">`System.Device.Gpio` ist mit den meisten Plattformen mit einem Board kompatibel.</span><span class="sxs-lookup"><span data-stu-id="e4353-135">`System.Device.Gpio` is compatible with most single-board platforms.</span></span> <span data-ttu-id="e4353-136">Empfohlene Plattformen sind Raspberry PI (2 und höher) und hummingboard.</span><span class="sxs-lookup"><span data-stu-id="e4353-136">Recommended platforms are Raspberry Pi (2 and greater) and Hummingboard.</span></span> <span data-ttu-id="e4353-137">Andere Plattformen, die kompatibel sind, sind "BeagleBoard" und "ODROID".</span><span class="sxs-lookup"><span data-stu-id="e4353-137">Other platforms known to be compatible are BeagleBoard and ODROID.</span></span>

<span data-ttu-id="e4353-138">PC-Plattformen werden durch die Verwendung einer USB-zu-SPI/I2C-Bridge unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e4353-138">PC platforms are supported via the use of a USB to SPI/I2C bridge.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e4353-139">.Net wird auf ARMv6-Architektur Geräten, einschließlich Raspberry Pi-und Raspberry Pi-Geräte vor Raspberry Pi 2, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e4353-139">.NET is not supported on ARMv6 architecture devices, including Raspberry Pi Zero and Raspberry Pi devices prior to Raspberry Pi 2.</span></span>

## <a name="resources"></a><span data-ttu-id="e4353-140">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="e4353-140">Resources</span></span>

- <span data-ttu-id="e4353-141">[.Net-IOT-Bibliotheken auf GitHub](https://github.com/dotnet/iot)<span class="docon docon-navigate-external x-hidden-focus"></span></span><span class="sxs-lookup"><span data-stu-id="e4353-141">[.NET IoT Libraries on Github](https://github.com/dotnet/iot) <span class="docon docon-navigate-external x-hidden-focus"></span></span></span>
