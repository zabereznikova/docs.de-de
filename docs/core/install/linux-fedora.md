---
title: Installieren von .NET Core unter Fedora (.NET Core)
description: Veranschaulicht verschiedene Möglichkeiten, das .NET Core SDK und die NET Core-Runtime unter Fedora zu installieren.
author: thraka
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 52aa9409ec876e0d1eaef22fb739046941fda897
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602837"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-fedora"></a>Installieren des .NET Core SDK oder der .NET Core-Runtime unter Fedora

.NET Core wird unter Fedora unterstützt. In diesem Artikel wird beschrieben, wie Sie .NET Core unter Fedora installieren. Wenn für eine Fedora-Version kein Support mehr geboten wird, wird .NET Core mit dieser Version nicht mehr unterstützt. Diese Anweisungen können Ihnen jedoch helfen, .NET Core in diesen Versionen auszuführen, auch wenn kein Support dafür geboten wird.

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a>Unterstützte Distributionen

Die folgende Tabelle ist eine Liste der derzeit unterstützten .NET Core-Versionen und der Versionen von Fedora, unter denen sie unterstützt werden. Diese Versionen werden weiterhin unterstützt, bis entweder die Version von [.NET Core das Ende des Supports](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) oder die Version von [Fedora das Ende ihrer Lebensdauer erreicht](https://fedoraproject.org/wiki/End_of_life).

- ✔️ gibt an, dass die Version von Fedora oder .NET Core weiterhin unterstützt wird.
- ❌ gibt an, dass die Version von Fedora oder .NET Core in dieser Fedora-Version nicht unterstützt wird.
- Wenn sowohl eine Version von Fedora als auch eine Version von .NET Core über ✔️ verfügen, wird diese Kombination aus Betriebssystem und .NET unterstützt.

| Fedora                   | .NET Core 2.1 | .NET Core 3.1 | .NET 5 Preview (nur manuelle Installation) |
|--------------------------|---------------|---------------|----------------|
| ✔️ [32](linux-fedora.md#fedora-32-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 Preview |
| ✔️ [31](linux-fedora.md#fedora-31-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 Preview |
| ❌ [30](linux-fedora.md#fedora-30-) | ✔️ 2.1        | ✔️ 3.1        | ❌ 5.0 Preview |
| ❌ [29](linux-fedora.md#fedora-29-) | ✔️ 2.1        | ✔️ 3.1        | ❌ 5.0 Preview |
| ❌ [28](linux-fedora.md#fedora-28-) | ✔️ 2.1        | ❌ 3.1        | ❌ 5.0 Preview |
| ❌ [27](linux-fedora.md#fedora-27-) | ✔️ 2.1        | ❌ 3.1        | ❌ 5.0 Preview |

Die folgenden Versionen von .NET Core werden nicht mehr unterstützt. Die Downloads dafür bleiben weiterhin veröffentlicht:

- 3.0
- 2.2
- 2.0

## <a name="how-to-install-other-versions"></a>Installieren anderer Versionen

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="fedora-32-"></a>Fedora 32 ✔️

NET Core 3.1 in den Standardpaketrepositorys für Fedora 32 verfügbar.

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="fedora-31-"></a>Fedora 31 ✔️

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/31/prod.repo
```

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="fedora-30-"></a>Fedora 30 ❌

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/30/prod.repo
```

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="fedora-29-"></a>Fedora 29 ❌

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/29/prod.repo
```

[!INCLUDE [linux-dnf-install-30](includes/linux-install-30-dnf.md)]

## <a name="fedora-28-"></a>Fedora 28 ❌

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/28/prod.repo
```

[!INCLUDE [linux-dnf-install-20](includes/linux-install-20-dnf.md)]

## <a name="fedora-27-"></a>Fedora 27 ❌

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/27/prod.repo
```

[!INCLUDE [linux-dnf-install-20](includes/linux-install-20-dnf.md)]

## <a name="troubleshoot-the-package-manager"></a>Problembehandlung des Paket-Managers

Dieser Abschnitt enthält Informationen zu häufigen Fehlern, die bei der Verwendung des Paket-Managers zur Installation von .NET Core auftreten können.

### <a name="failed-to-fetch"></a>Fehler beim Abrufen

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="snap"></a>Snap

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a>Abhängigkeiten

[!INCLUDE [linux-install-dependencies](includes/linux-install-dependencies.md)]

## <a name="scripted-install"></a>Per Skript gesteuerte Installation

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a>Manuelle Installation

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a>Nächste Schritte

- [Tutorial: Erstellen einer Konsolenanwendung mit dem .NET Core SDK in Visual Studio Code](../tutorials/with-visual-studio-code.md)
