---
title: Installieren von .NET unter CentOS – .NET
description: In diesem Artikel werden verschiedene Möglichkeiten veranschaulicht, das .NET SDK und die .NET-Runtime unter CentOS zu installieren.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 7e73f90a1f1f7e11e592b1b074f243c9f5b32ced
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970862"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-centos"></a>Installieren des .NET SDK oder der .NET-Runtime unter CentOS

.NET wird unter CentOS unterstützt. In diesem Artikel wird beschrieben, wie Sie .NET unter CentOS installieren.

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a>Unterstützte Distributionen

Die folgende Tabelle enthält die derzeit unter CentOS 7 und CentOS 8 unterstützten .NET-Releases. Diese Versionen werden weiterhin unterstützt, bis entweder die Version von [.NET das Ende des Supports](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) erreicht oder die Version von CentOS nicht mehr unterstützt wird.

- Das Häkchen ✔️ gibt an, dass die Version von CentOS oder .NET weiterhin unterstützt wird.
- Das ❌ gibt an, dass die Version von CentOS oder .NET in diesem CentOS-Release nicht unterstützt wird.
- Wenn sowohl eine Version von CentOS als auch eine Version von .NET mit ✔️ markiert sind, wird diese Kombination aus einem Betriebssystem und .NET unterstützt.

| CentOS                   | .NET Core 2.1 | .NET Core 3.1 | .NET 5.0 |
|--------------------------|---------------|---------------|----------------|
| ✔️ [8](#centos-8-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ✔️ [7](#centos-7-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |

Die folgenden Versionen von .NET werden nicht mehr unterstützt. Die Downloads dafür bleiben weiterhin veröffentlicht:

- 3.0
- 2.2
- 2.0

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="remove-preview-versions"></a>Entfernen von Vorschauversionen

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="centos-8-"></a>CentOS 8 ✔️

.NET 5.0 ist in den Standardpaketrepositorys für CentOS 8 verfügbar.

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="centos-7-"></a>CentOS 7 ✔️

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/centos/7/packages-microsoft-prod.rpm
```

[!INCLUDE [linux-yum-install-50](includes/linux-install-50-yum.md)]

## <a name="how-to-install-other-versions"></a>Installieren anderer Versionen

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a>Problembehandlung des Paket-Managers

Dieser Abschnitt enthält Informationen zu häufigen Fehlern, die bei der Verwendung des Paket-Managers zur Installation von .NET auftreten können.

### <a name="unable-to-find-package"></a>Paket konnte nicht gefunden werden

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="failed-to-fetch"></a>Fehler beim Abrufen

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="dependencies"></a>Abhängigkeiten

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="next-steps"></a>Nächste Schritte

- [Aktivieren der Vervollständigung mit der TAB-TASTE für die .NET-CLI](../tools/enable-tab-autocomplete.md)
- [Tutorial: Erstellen einer Konsolenanwendung mit dem .NET SDK in Visual Studio Code](../tutorials/with-visual-studio-code.md)
