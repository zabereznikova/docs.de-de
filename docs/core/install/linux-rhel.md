---
title: Installieren von .NET Core unter RHEL (.NET Core)
description: Veranschaulicht verschiedene Möglichkeiten, das .NET Core SDK und die NET Core-Runtime unter RHEL zu installieren.
author: thraka
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 7ae55f881cd0c877cf1db24be7a4ee23320e21a8
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602795"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-rhel"></a>Installieren des .NET Core SDK oder der .NET Core-Runtime unter RHEL

.NET Core wird unter RHEL unterstützt. In diesem Artikel wird beschrieben, wie Sie .NET Core unter RHEL installieren.

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="register-your-red-hat-subscription"></a>Registrieren Ihres Red Hat-Abonnements

Sie müssen sich zuerst mit dem Red Hat-Abonnement-Manager registrieren, um .NET Core von Red Hat auf RHEL zu installieren. Wenn Sie dies auf Ihrem System noch nicht getan haben oder Sie unsicher sind, finden Sie weitere Informationen in der [Red Hat-Produktdokumentation für .NET Core](https://access.redhat.com/documentation/net_core/).

## <a name="supported-distributions"></a>Unterstützte Distributionen

Die folgende Tabelle ist eine Liste der derzeit unter RHEL 7 und RHEL 8 unterstützten .NET Core-Versionen. Diese Versionen werden weiterhin unterstützt, bis entweder die Version von [.NET Core das Ende des Supports](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) erreicht oder die Version von RHEL nicht mehr unterstützt wird.

- ✔️ gibt an, dass die Version von RHEL oder .NET Core weiterhin unterstützt wird.
- ❌ gibt an, dass die Version von RHEL oder .NET Core in dieser RHEL-Version nicht unterstützt wird.
- Wenn sowohl eine Version von RHEL als auch eine Version von .NET Core über ✔️ verfügen, wird diese Kombination aus Betriebssystem und .NET unterstützt.

| RHEL                   | .NET Core 2.1 | .NET Core 3.1 | .NET 5 Preview (nur manuelle Installation) |
|--------------------------|---------------|---------------|----------------|
| ✔️ [8](#rhel-8-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 Preview |
| ✔️ [7](#rhel-7-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 Preview |

Die folgenden Versionen von .NET Core werden nicht mehr unterstützt. Die Downloads dafür bleiben weiterhin veröffentlicht:

- 3.0
- 2.2
- 2.0

## <a name="how-to-install-other-versions"></a>Installieren anderer Versionen

Konsultieren Sie die [Red Hat-Dokumentation zu .NET Core](https://access.redhat.com/documentation/net_core/) hinsichtlich der Schritte, die zur Installation anderer Versionen von .NET Core erforderlich sind.

## <a name="rhel-8-"></a>RHEL 8 ✔️

NET Core ist in den AppStream-Repositorys für RHEL 8 enthalten.

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="rhel-7-"></a>RHEL 7 ✔️

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

Mit dem folgenden Befehl wird das Paket `scl-utils` installiert:

```bash
sudo yum install scl-utils
```

### <a name="install-the-sdk"></a>Installieren des SDKs

Das .NET Core SDK ermöglicht Ihnen die Entwicklung von Apps mit .NET Core. Wenn Sie das .NET Core SDK installieren, müssen Sie die entsprechende Runtime nicht installieren. Führen Sie die folgenden Befehle aus, um das .NET Core SDK zu installieren:

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31 -y
scl enable rh-dotnet31 bash
```

Red Hat empfiehlt nicht die dauerhafte Aktivierung von `rh-dotnet31`, da dies andere Programme beeinträchtigen könnte. `rh-dotnet31` enthält beispielsweise eine Version von `libcurl`, die sich von der Basisversion von RHEL unterscheidet. Dies kann zu Problemen in Programmen führen, die keine andere Version von `libcurl` erwarten. Wenn Sie `rh-dotnet` dauerhaft aktivieren möchten, fügen Sie der Datei _~/.bashrc_ die folgende Zeile hinzu.

```bash
source scl_source enable rh-dotnet31
```

### <a name="install-the-runtime"></a>Installieren der Runtime

Die .NET Core-Runtime ermöglicht Ihnen die Ausführung von Apps, die mit .NET Core erstellt wurden und die Runtime nicht enthalten. Die folgenden Befehle installieren die ASP.NET Core-Runtime, die die kompatibelste Runtime für .NET Core ist. Führen Sie in Ihrem Terminal die folgenden Befehle aus.

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-aspnetcore-runtime-3.1 -y
scl enable rh-dotnet31-aspnetcore-runtime-3.1 bash
```

Red Hat empfiehlt nicht die dauerhafte Aktivierung von `rh-dotnet31-aspnetcore-runtime-3.1`, da dies andere Programme beeinträchtigen könnte. So enthält beispielsweise `rh-dotnet31-aspnetcore-runtime-3.1` eine Version von `libcurl`, die sich von der Basisversion von RHEL unterscheidet. Dies kann zu Problemen in Programmen führen, die keine andere Version von `libcurl` erwarten. Wenn Sie `rh-dotnet31-aspnetcore-runtime-3.1` dauerhaft aktivieren möchten, fügen Sie der Datei _~/.bashrc_ die folgende Zeile hinzu.

```bash
source scl_source enable rh-dotnet31-aspnetcore-runtime-3.1
```

Als Alternative zur ASP.NET Core-Runtime können Sie die .NET Core-Runtime installieren, die keine ASP.NET Core-Unterstützung bietet. Ersetzen Sie im obigen Befehl `rh-dotnet31-aspnetcore-runtime-3.1` durch `rh-dotnet31-dotnet-runtime-3.1`.

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
