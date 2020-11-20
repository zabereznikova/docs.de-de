---
title: 'Installieren von .NET unter RHEL: .NET'
description: In diesem Artikel werden verschiedene Möglichkeiten veranschaulicht, das .NET SDK und die NET-Runtime für RHEL zu installieren.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: cb03f84cf84557d467f0a067b8d5629a843ec7e3
ms.sourcegitcommit: c38bf879a2611ff46aacdd529b9f2725f93e18a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2020
ms.locfileid: "94594580"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-rhel"></a>Installieren des .NET SDK oder der .NET-Runtime unter RHEL

.NET wird unter RHEL unterstützt. In diesem Artikel wird beschrieben, wie Sie .NET unter RHEL installieren.

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="register-your-red-hat-subscription"></a>Registrieren Ihres Red Hat-Abonnements

Sie müssen sich zuerst mit dem Red Hat-Abonnement-Manager registrieren, um .NET von Red Hat unter RHEL installieren zu können. Wenn Sie dies auf Ihrem System noch nicht getan haben oder Sie unsicher sind, finden Sie weitere Informationen in der [Red Hat-Produktdokumentation für .NET](https://access.redhat.com/documentation/net/5.0/).

## <a name="supported-distributions"></a>Unterstützte Distributionen

Die folgende Tabelle enthält die derzeit unter RHEL 7 und RHEL 8 unterstützten .NET-Releases. Diese Versionen werden weiterhin unterstützt, bis entweder die Version von [.NET das Ende des Supports](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) erreicht oder die Version von RHEL nicht mehr unterstützt wird.

- ✔️ gibt an, dass die Version von RHEL oder .NET weiterhin unterstützt wird.
- ❌ gibt an, dass die Version von RHEL oder .NET in diesem RHEL-Release nicht unterstützt wird.
- Wenn sowohl eine Version von RHEL als auch eine Version von .NET mit ✔️ markiert sind, wird diese Kombination aus Betriebssystem und .NET unterstützt.

| RHEL                     | .NET Core 2.1 | .NET Core 3.1 | .NET 5.0 |
|--------------------------|---------------|---------------|----------------|
| ✔️ [8](#rhel-8-)        | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ✔️ [7](#rhel-7--net-50) | ✔️ 2.1        | ✔️ [3.1](#rhel-7--net-core-31)        | ✔️ [5.0](#rhel-7--net-50) |

Die folgenden Versionen von .NET werden nicht mehr unterstützt. Die Downloads dafür bleiben weiterhin veröffentlicht:

- 3.0
- 2.2
- 2.0

## <a name="how-to-install-other-versions"></a>Installieren anderer Versionen

Konsultieren Sie die [Red Hat-Dokumentation zu .NET](https://access.redhat.com/documentation/net/5.0/) hinsichtlich der Schritte, die zur Installation anderer Releases von .NET erforderlich sind.

## <a name="rhel-8-"></a>RHEL 8 ✔️

> [!TIP]
> .NET 5.0 ist in den AppStream-Repositorys noch nicht verfügbar, .NET Core 3.1 dahingegen schon. Verwenden Sie zur Installation von .NET Core 3.1 den `dnf install`-Befehl mit entsprechendem Paket, z. B. `aspnetcore-runtime-3.1` oder `dotnet-sdk-3.1`. Die folgenden Anweisungen beziehen sich auf .NET 5.0.

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/rhel/8/prod.repo
```

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="rhel-7--net-50"></a>RHEL 7 ✔️ .NET 5.0

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/rhel/7/prod.repo
```

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-yum.md)]

## <a name="rhel-7--net-core-31"></a>RHEL 7 ✔️ .NET Core 3.1

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

Red Hat empfiehlt nicht die dauerhafte Aktivierung von `rh-dotnet31`, da dies andere Programme beeinträchtigen könnte. So enthält beispielsweise `rh-dotnet31` eine Version von `libcurl`, die sich von der Basisversion von RHEL unterscheidet. Dies kann zu Problemen in Programmen führen, die keine andere Version von `libcurl` erwarten. Wenn Sie `rh-dotnet` dauerhaft aktivieren möchten, fügen Sie der Datei _~/.bashrc_ die folgende Zeile hinzu.

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

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="scripted-install"></a>Per Skript gesteuerte Installation

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a>Manuelle Installation

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a>Nächste Schritte

- [Tutorial: Erstellen einer Konsolenanwendung mit dem .NET SDK in Visual Studio Code](../tutorials/with-visual-studio-code.md)
