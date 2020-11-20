---
title: 'Installieren von .NET für SLES: .NET'
description: In diesem Artikel werden verschiedene Möglichkeiten veranschaulicht, das .NET SDK und die .NET-Runtime für SLES zu installieren.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 558574116aac2a3c755481069641e81a435a2a43
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506868"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-sles"></a>Installieren des .NET SDK oder der .NET-Runtime für SLES

.NET wird unter SLES unterstützt. In diesem Artikel wird beschrieben, wie Sie .NET für SLES installieren.

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="supported-distributions"></a>Unterstützte Distributionen

Die folgende Tabelle enthält die derzeit unter SLES 12 SP2 und SLES 15 unterstützten .NET-Releases. Diese Versionen werden weiterhin unterstützt, bis entweder die Version von [.NET das Ende des Supports](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) erreicht oder die Version von SLES nicht mehr unterstützt wird.

- ✔️ gibt an, dass die Version von SLES oder .NET weiterhin unterstützt wird.
- ❌ gibt an, dass die Version von SLES oder .NET in diesem SLES-Release nicht unterstützt wird.
- Wenn sowohl eine Version von SLES als auch eine Version von .NET mit ✔️ markiert sind, wird diese Kombination aus Betriebssystem und .NET unterstützt.

| SLES                   | .NET Core 2.1 | .NET Core 3.1 | .NET 5.0 |
|------------------------|---------------|---------------|----------------|
| ✔️ [15](#sles-15-)     | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ✔️ [12 SP2](#sles-12-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |

Die folgenden Versionen von .NET Core werden nicht mehr unterstützt. Die Downloads dafür bleiben weiterhin veröffentlicht:

- 3.0
- 2.2
- 2.0

## <a name="how-to-install-other-versions"></a>Installieren anderer Versionen

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="sles-15-"></a>SLES 15 ✔️

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/15/packages-microsoft-prod.rpm
```

Das Setuppaket für das Microsoft-Repository „SLES 15“ installiert zurzeit die Datei *microsoft-prod.repo* im falschen Verzeichnis, sodass zypper die .NET-Pakete nicht finden kann. Erstellen Sie einen Symlink im richtigen Verzeichnis, um dieses Problem zu beheben.

```bash
sudo ln -s /etc/yum.repos.d/microsoft-prod.repo /etc/zypp/repos.d/microsoft-prod.repo
```

[!INCLUDE [linux-zyp-install-50](includes/linux-install-50-zyp.md)]

## <a name="sles-12-"></a>SLES 12 ✔️

.NET setzt für die SLES 12-Familie mindestens SP2 voraus.

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/12/packages-microsoft-prod.rpm
```

[!INCLUDE [linux-zyp-install-50](includes/linux-install-50-zyp.md)]

## <a name="troubleshoot-the-package-manager"></a>Problembehandlung des Paket-Managers

Dieser Abschnitt enthält Informationen zu häufigen Fehlern, die bei der Verwendung des Paket-Managers zur Installation von .NET auftreten können.

### <a name="failed-to-fetch"></a>Fehler beim Abrufen

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="dependencies"></a>Abhängigkeiten

Wenn die Installation mit einem Paket-Manager erfolgt, werden diese Bibliotheken für Sie installiert. Wenn Sie jedoch .NET manuell installieren oder eine eigenständige Anwendung veröffentlichen, müssen Sie sicherstellen, dass diese Bibliotheken installiert sind:

- krb5
- libicu
- libopenssl1_1

Wenn die OpenSSL-Version der Zielruntime-Umgebung 1.1 oder neuer ist, müssen Sie **compat-openssl10** installieren.

Weitere Informationen zu den Abhängigkeiten finden Sie unter [Eigenständige Linux-Apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).

Für .NET-Anwendungen, die die Assembly *System.Drawing.Common* verwenden, benötigen Sie außerdem die folgende Abhängigkeit:

- [libgdiplus (Version 6.0.1 oder höher)](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > Sie können eine neuere Version von *libgdiplus* installieren, indem Sie Ihrem System das Mono-Repository hinzufügen. Weitere Informationen finden Sie unter <https://www.mono-project.com/download/stable/>.

## <a name="scripted-install"></a>Per Skript gesteuerte Installation

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a>Manuelle Installation

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a>Nächste Schritte

- [Tutorial: Erstellen einer Konsolenanwendung mit dem .NET SDK in Visual Studio Code](../tutorials/with-visual-studio-code.md)
