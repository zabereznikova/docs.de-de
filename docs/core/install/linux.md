---
title: Installieren von .NET für Linux-Distributionen
description: Hier erfahren Sie, welche Linux-Distributionen die Installation von .NET unter Linux unterstützen.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 6354ef6f0f9af2126312683893d6705b3b4c70f4
ms.sourcegitcommit: c38bf879a2611ff46aacdd529b9f2725f93e18a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2020
ms.locfileid: "94594518"
---
# <a name="install-net-on-linux"></a>Installieren von .NET unter Linux

> [!div class="op_single_selector"]
>
> - [Installieren unter Windows](windows.md)
> - [Installieren unter macOS](macos.md)
> - [Installieren unter Linux](linux.md)

.NET ist für verschiedene Linux-Distributionen verfügbar. Für die meisten Linux-Plattformen und -Distributionen gibt es jedes Jahr eine Hauptversion. Die meisten bieten einen Paket-Manager, der zur Installation von .NET genutzt wird. In diesem Artikel wird beschrieben, was derzeit unterstützt wird und welcher Paket-Manager verwendet wird.

Der Rest dieses Artikels ist eine Übersicht über die einzelnen Linux-Hauptdistributionen, die .NET unterstützt. Alle .NET-Releases werden weiterhin unterstützt, bis entweder die Version von [.NET das Ende des Supports](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) erreicht oder die Linux-Distribution das Ende ihrer Lebensdauer erreicht.

Eine LTS-Version (Long-Term Release) bietet bestmögliche Kompatibilität.

## <a name="unsupported-releases"></a>Nicht unterstützte Versionen

Die folgenden Versionen von .NET werden nicht mehr unterstützt (❌). Die Downloads dafür bleiben weiterhin veröffentlicht:

- 3.0
- 2.2
- 2.0

Diese Versionen ohne Support werden in den folgenden Abschnitten nicht näher beschrieben, und Ihre Laufzeit kann variieren, wenn Sie versuchen, sie zu installieren.

## <a name="alpine"></a>Alpine

Es sind keine Installationsprogramme für Alpine vorhanden. Sie müssen entweder das [Installationsskript](linux-alpine.md#scripted-install) verwenden oder die Anweisungen zur [manuellen Installation](linux-alpine.md#manual-install) befolgen.

Die folgende Tabelle enthält die derzeit unterstützten .NET-Releases und die Alpine-Versionen, die diese unterstützen. Diese Versionen werden weiterhin unterstützt, bis entweder die Version von [.NET das Ende des Supports](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) oder die Version von [Alpine das Ende ihrer Lebensdauer](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases) erreicht.

- ✔️ gibt an, dass die Version von Alpine oder .NET weiterhin unterstützt wird.
- ❌ gibt an, dass die Version von Alpine oder .NET in diesem Alpine-Release nicht unterstützt wird.
- Wenn sowohl eine Version von Alpine als auch eine Version von .NET mit ✔️ markiert sind, wird diese Kombination aus Betriebssystem und .NET unterstützt.

| Alpine                      | .NET Core 2.1 | .NET Core 3.1 | .NET 5.0 |
|-----------------------------|---------------|---------------|----------------|
| ✔️ [3.12](linux-alpine.md)  | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ✔️ [3.11](linux-alpine.md)  | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ✔️ [3.10](linux-alpine.md)  | ✔️ 2.1        | ✔️ 3.1        | ❌ 5.0 |
| ❌ [3.9](linux-alpine.md)   | ✔️ 2.1        | ✔️ 3.1        | ❌ 5.0 |
| ❌ [3.8](linux-alpine.md)   | ✔️ 2.1        | ✔️ 3.1        | ❌ 5.0 |

Weitere Informationen finden Sie unter [Installieren von .NET unter Alpine](linux-alpine.md).

## <a name="centos"></a>CentOS

CentOS 7 nutzt Yum als Paket-Manager, CentOS 8 verwendet DNF.

Die folgende Tabelle enthält die derzeit unter CentOS 7 und CentOS 8 unterstützten .NET-Releases. Diese Versionen werden weiterhin unterstützt, bis entweder die Version von [.NET das Ende des Supports](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) erreicht oder die Version von CentOS nicht mehr unterstützt wird.

| CentOS                   | .NET Core 2.1 | .NET Core 3.1 | .NET 5.0 |
|--------------------------|---------------|---------------|----------------|
| ✔️ [8](linux-centos.md#centos-8-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ✔️ [7](linux-centos.md#centos-7-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |

Weitere Informationen finden Sie unter [Installieren von .NET unter CentOS](linux-centos.md).

## <a name="debian"></a>Debian

Debian verwendet APT (Advanced Package Tool) als Paket-Manager.

Die folgende Tabelle enthält die derzeit unterstützten .NET-Releases und Versionen von Debian, unter denen sie unterstützt werden. Diese Versionen werden weiterhin unterstützt, bis entweder die Version von [.NET das Ende des Supports](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) oder die Version von [Debian das Ende ihrer Lebensdauer erreicht](https://wiki.debian.org/DebianReleases).

- ✔️ gibt an, dass die Version von Debian oder .NET weiterhin unterstützt wird.
- ❌ gibt an, dass die Version von Debian oder .NET in diesem Debian-Release nicht unterstützt wird.
- Wenn sowohl eine Version von Debian als auch eine Version von .NET über ✔️ verfügen, wird diese Kombination aus Betriebssystem und .NET unterstützt.

| Debian                   | .NET Core 2.1 | .NET Core 3.1 | .NET 5.0 |
|--------------------------|---------------|---------------|----------------|
| ✔️ [10](linux-debian.md#debian-10-)     | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ✔️ [9](linux-debian.md#debian-9-)       | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ❌ [8](linux-debian.md#debian-8-)       | ✔️ 2.1        | ❌ 3.1        | ❌ 5.0 |

Weitere Informationen finden Sie unter [Installieren von .NET unter Debian](linux-debian.md).

## <a name="fedora"></a>Fedora

Fedora verwendet DNF als Paket-Manager.

Die folgende Tabelle enthält die derzeit unterstützten .NET-Releases und Versionen von Fedora, unter denen sie unterstützt werden. Diese Versionen werden weiterhin unterstützt, bis entweder die Version von [.NET das Ende des Supports](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) oder die Version von [Fedora das Ende ihrer Lebensdauer erreicht](https://fedoraproject.org/wiki/End_of_life).

- ✔️ gibt an, dass die Version von Fedora oder .NET weiterhin unterstützt wird.
- ❌ gibt an, dass die Version von Fedora oder .NET in diesem Fedora-Release nicht unterstützt wird.
- Wenn sowohl eine Version von Fedora als auch eine Version von .NET mit ✔️ markiert sind, wird diese Kombination aus Betriebssystem und .NET unterstützt.

| Fedora                   | .NET Core 2.1 | .NET Core 3.1 | .NET 5.0 |
|--------------------------|---------------|---------------|----------------|
| ✔️ [33](linux-fedora.md#fedora-33-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ✔️ [32](linux-fedora.md#fedora-32-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ❌ [31](linux-fedora.md#fedora-31-) | ✔️ 2.1        | ✔️ 3.1        | ❌ 5.0 |
| ❌ [30](linux-fedora.md#fedora-30-) | ✔️ 2.1        | ✔️ 3.1        | ❌ 5.0 |
| ❌ [29](linux-fedora.md#fedora-29-) | ✔️ 2.1        | ✔️ 3.1        | ❌ 5.0 |
| ❌ [28](linux-fedora.md#fedora-28-) | ✔️ 2.1        | ❌ 3.1        | ❌ 5.0 |
| ❌ [27](linux-fedora.md#fedora-27-) | ✔️ 2.1        | ❌ 3.1        | ❌ 5.0 |

Weitere Informationen finden Sie unter [Installieren von .NET unter Fedora](linux-fedora.md).

## <a name="opensuse"></a>openSUSE

openSUSE verwendet zypper als Paket-Manager.

Die folgende Tabelle enthält die derzeit unter openSUSE 15 unterstützten .NET-Releases. Diese Versionen werden weiterhin unterstützt, bis entweder die Version von [.NET das Ende des Supports](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) erreicht oder die Version von openSUSE nicht mehr unterstützt wird.

| openSUSE                   | .NET Core 2.1 | .NET Core 3.1 | .NET 5.0 |
|----------------------------|---------------|---------------|----------------|
| ✔️ [15](linux-opensuse.md#opensuse-15-)     | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |

Weitere Informationen finden Sie unter [Installieren von .NET unter openSUSE](linux-opensuse.md).

## <a name="red-hat"></a>Red Hat

Red Hat Enterprise Linux (RHEL) verwendet yum (RHEL 7) und DNF (RHEL 8) als Paket-Manager.

Die folgende Tabelle enthält die derzeit unter RHEL 7 und RHEL 8 unterstützten .NET-Releases. Diese Versionen werden weiterhin unterstützt, bis entweder die Version von [.NET das Ende des Supports](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) erreicht oder die Version von RHEL nicht mehr unterstützt wird.

- ✔️ gibt an, dass die Version von RHEL oder .NET weiterhin unterstützt wird.
- ❌ gibt an, dass die Version von RHEL oder .NET in diesem RHEL-Release nicht unterstützt wird.
- Wenn sowohl eine Version von RHEL als auch eine Version von .NET mit ✔️ markiert sind, wird diese Kombination aus Betriebssystem und .NET unterstützt.

| RHEL                   | .NET Core 2.1 | .NET Core 3.1 | .NET 5.0 |
|--------------------------|---------------|---------------|----------------|
| ✔️ [8](linux-rhel.md#rhel-8-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ✔️ [7](linux-rhel.md#rhel-7--net-50) | ✔️ 2.1        | ✔️ [3.1](linux-rhel.md#rhel-7--net-core-31)        | ✔️ [5.0](linux-rhel.md#rhel-7--net-50) |

Weitere Informationen finden Sie unter [Installieren von .NET unter RHEL](linux-rhel.md).

## <a name="sles"></a>SLES

SLES verwendet zypper als Paket-Manager.

Die folgende Tabelle enthält die derzeit unter SLES 12 SP2 und SLES 15 unterstützten .NET-Releases. Diese Versionen werden weiterhin unterstützt, bis entweder die Version von [.NET das Ende des Supports](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) erreicht oder die Version von SLES nicht mehr unterstützt wird.

- ✔️ gibt an, dass die Version von SLES oder .NET weiterhin unterstützt wird.
- ❌ gibt an, dass die Version von SLES oder .NET in diesem SLES-Release nicht unterstützt wird.
- Wenn sowohl eine Version von SLES als auch eine Version von .NET mit ✔️ markiert sind, wird diese Kombination aus Betriebssystem und .NET unterstützt.

| SLES                   | .NET Core 2.1 | .NET Core 3.1 | .NET 5.0 |
|------------------------|---------------|---------------|----------------|
| ✔️ [15](linux-sles.md#sles-15-)     | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ✔️ [12 SP2](linux-sles.md#sles-12-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |

Weitere Informationen finden Sie unter [Installieren von .NET unter SLES](linux-sles.md).

## <a name="ubuntu"></a>Ubuntu

Ubuntu verwendet APT (Advanced Package Tool) als Paket-Manager.

Die folgende Tabelle zeigt den Supportstatus von Ubuntu und .NET.

- ✔️ gibt an, dass die Version von Ubuntu oder .NET Core weiterhin unterstützt wird.
- ❌ gibt an, dass die Version von Ubuntu oder .NET unter diesem Ubuntu-Release nicht unterstützt wird.
- Wenn sowohl eine Version von Ubuntu als auch eine Version von .NET mit ✔️ markiert sind, wird diese Kombination aus Betriebssystem und .NET unterstützt.

| Ubuntu                   | .NET Core 2.1 | .NET Core 3.1 | .NET 5.0 |
|--------------------------|---------------|---------------|----------------|
| ✔️ [20.10](linux-ubuntu.md#2010-)       | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ✔️ [20.04 (LTS)](linux-ubuntu.md#2004-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ❌ [19.10](linux-ubuntu.md#1910-)       | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ❌ [19.04](linux-ubuntu.md#1904-)       | ✔️ 2.1        | ✔️ 3.1        | ❌ 5.0 |
| ❌ [18.10](linux-ubuntu.md#1810-)       | ✔️ 2.1        | ❌ 3.1        | ❌ 5.0 |
| ✔️ [18.04 (LTS)](linux-ubuntu.md#1804-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ❌ [17.10](linux-ubuntu.md#1710-)       | ✔️ 2.1        | ❌ 3.1        | ❌ 5.0 |
| ❌ [17.04](linux-ubuntu.md#1704-)       | ✔️ 2.1        | ❌ 3.1        | ❌ 5.0 |
| ❌ [16.10](linux-ubuntu.md#1610-)       | ❌ 2.1        | ❌ 3.1        | ❌ 5.0 |
| ✔️ [16.04 (LTS)](linux-ubuntu.md#1604-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |

Weitere Informationen finden Sie unter [Installieren von .NET unter Ubuntu](linux-ubuntu.md).

## <a name="next-steps"></a>Nächste Schritte

- [Überprüfen, ob .NET Core bereits installiert ist](how-to-detect-installed-versions.md?pivots=os-linux)
- [Tutorial: Erstellen einer neuen App mit Visual Studio Code](../tutorials/with-visual-studio-code.md)
- [Tutorial: Containerisieren einer .NET Core-App](../docker/build-container.md)
