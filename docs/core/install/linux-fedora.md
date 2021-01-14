---
title: 'Installieren von .NET unter Fedora: .NET'
description: In diesem Artikel werden verschiedene Möglichkeiten veranschaulicht, das .NET SDK und die .NET-Runtime für Fedora zu installieren.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 9dd8c6264831e2a9382960be505639f1eba95151
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970823"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-fedora"></a>Installieren des .NET SDK oder der .NET-Runtime unter Fedora

.NET wird unter Fedora unterstützt. In diesem Artikel wird beschrieben, wie Sie .NET unter Fedora installieren. Wenn für eine Fedora-Version kein Support mehr geboten wird, wird .NET mit dieser Version nicht mehr unterstützt.

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="install-net-50"></a>Installieren von .NET 5.0

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

**Fedora 32**

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/32/prod.repo
```

**Fedora 33**

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/33/prod.repo
```

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="install-net-core-31"></a>Installieren von .NET Core 3.1

Die neueste in den Standardpaketrepositorys für Fedora verfügbare Version von .NET ist .NET Core 3.1.

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="supported-distributions"></a>Unterstützte Distributionen

Die folgende Tabelle enthält die derzeit unterstützten .NET-Releases und Versionen von Fedora, unter denen sie unterstützt werden. Diese Versionen werden weiterhin unterstützt, bis entweder die Version von [.NET das Ende des Supports](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) oder die Version von [Fedora das Ende ihrer Lebensdauer erreicht](https://fedoraproject.org/wiki/End_of_life).

- ✔️ gibt an, dass die Version von Fedora oder .NET weiterhin unterstützt wird.
- ❌ gibt an, dass die Version von Fedora oder .NET in diesem Fedora-Release nicht unterstützt wird.
- Wenn sowohl eine Version von Fedora als auch eine Version von .NET mit ✔️ markiert sind, wird diese Kombination aus Betriebssystem und .NET unterstützt.

| .NET-Version  | Fedora 33 ✔️ | 32 ✔️ | 31 ❌ | 30 ❌ | 29 ❌ | 28 ❌ | 27 ❌ |
| ------------  | ---------: | --: | --: | --: | --: | --: | --: |
| .NET 5.0      | ✔️        | ✔️ | ❌|❌ |❌ |❌  |❌ |
| .NET Core 3.1 | ✔️        | ✔️ | ✔️|✔️ |✔️ |❌  |❌ |
| .NET Core 2.1 | ✔️        | ✔️ | ✔️|✔️ |✔️ |✔️  |✔️ |

Die folgenden Versionen von .NET werden nicht mehr unterstützt. Die Downloads dafür bleiben weiterhin veröffentlicht:

- 3.0
- 2.2
- 2.0

## <a name="remove-preview-versions"></a>Entfernen von Vorschauversionen

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="dependencies"></a>Abhängigkeiten

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="install-on-older-distributions"></a>Installieren unter älteren Distributionen

Bei älteren Versionen von Fedora ist .NET Core nicht in den Standardpaketrepositorys enthalten. Sie können .NET mit [Snap](linux-snap.md), über das [_dotnet-install.sh_-Skript](linux-scripted-manual.md#scripted-install) oder über das Microsoft-Repository für die Installation von .NET installieren:

01. Fügen Sie zunächst den Microsoft-Signaturschlüssel zur Liste der vertrauenswürdigen Schlüssel hinzu.

    ```bash
    sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
    ```

02. Fügen Sie als Nächstes das Microsoft-Paketrepository hinzu. Die Quelle des Repositorys basiert auf Ihrer Fedora-Version.

    | Fedora-Version | Paketrepository |
    | -------------- | ------- |
    | 31             | `https://packages.microsoft.com/config/fedora/31/prod.repo` |
    | 30             | `https://packages.microsoft.com/config/fedora/30/prod.repo` |
    | 29             | `https://packages.microsoft.com/config/fedora/29/prod.repo` |
    | 28             | `https://packages.microsoft.com/config/fedora/28/prod.repo` |
    | 27             | `https://packages.microsoft.com/config/fedora/27/prod.repo` |

    ```bash
    sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/31/prod.repo
    ```

[!INCLUDE [linux-dnf-install-31](./includes/linux-install-31-dnf.md)]

## <a name="how-to-install-other-versions"></a>Installieren anderer Versionen

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a>Problembehandlung des Paket-Managers

Dieser Abschnitt enthält Informationen zu häufigen Fehlern, die bei der Verwendung des Paket-Managers zur Installation von .NET oder .NET Core auftreten können.

### <a name="unable-to-find-package"></a>Paket konnte nicht gefunden werden

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="failed-to-fetch"></a>Fehler beim Abrufen

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="next-steps"></a>Nächste Schritte

- [Aktivieren der Vervollständigung mit der TAB-TASTE für die .NET-CLI](../tools/enable-tab-autocomplete.md)
- [Tutorial: Erstellen einer Konsolenanwendung mit dem .NET SDK in Visual Studio Code](../tutorials/with-visual-studio-code.md)
