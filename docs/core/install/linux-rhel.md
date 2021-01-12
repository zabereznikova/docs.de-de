---
title: 'Installieren von .NET unter RHEL: .NET'
description: In diesem Artikel werden verschiedene Möglichkeiten veranschaulicht, das .NET SDK und die NET-Runtime für RHEL zu installieren.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: d585017919507a8fdcbb24778a0ff3ab3d9049c2
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970797"
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

## <a name="remove-preview-versions"></a>Entfernen von Vorschauversionen

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="rhel-8-"></a>RHEL 8 ✔️

.NET ist in den AppStream-Repositorys für RHEL 8 enthalten.

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="rhel-7--net-50"></a>RHEL 7 ✔️ .NET 5.0

Mit dem folgenden Befehl wird das Paket `scl-utils` installiert:

```bash
sudo yum install scl-utils
```

### <a name="install-the-sdk"></a>Installieren des SDKs

Das .NET SDK ermöglicht Ihnen die Entwicklung von Apps mit .NET. Wenn Sie das .NET SDK installieren, müssen Sie die entsprechende Runtime nicht installieren. Führen Sie die folgenden Befehle aus, um das .NET SDK zu installieren:

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet50 -y
scl enable rh-dotnet50 bash
```

Red Hat empfiehlt nicht die dauerhafte Aktivierung von `rh-dotnet50`, da dies andere Programme beeinträchtigen könnte. Wenn Sie `rh-dotnet` dauerhaft aktivieren möchten, fügen Sie der Datei _~/.bashrc_ die folgende Zeile hinzu.

```bash
source scl_source enable rh-dotnet50
```

### <a name="install-the-runtime"></a>Installieren der Runtime

Die .NET-Runtime ermöglicht Ihnen die Ausführung von Apps, die mit .NET erstellt wurden und die Runtime nicht enthalten. Die folgenden Befehle installieren die ASP.NET Core-Runtime, die die kompatibelste Runtime für .NET Core ist. Führen Sie in Ihrem Terminal die folgenden Befehle aus.

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet50-aspnetcore-runtime-5.0 -y
scl enable rh-dotnet50 bash
```

Red Hat empfiehlt nicht die dauerhafte Aktivierung von `rh-dotnet50`, da dies andere Programme beeinträchtigen könnte. Wenn Sie `rh-dotnet50` dauerhaft aktivieren möchten, fügen Sie der Datei _~/.bashrc_ die folgende Zeile hinzu.

```bash
source scl_source enable rh-dotnet50
```

Als Alternative zur ASP.NET Core-Runtime können Sie die .NET-Runtime installieren, die keine ASP.NET Core-Unterstützung bietet. Ersetzen Sie hierzu im obigen Befehl `rh-dotnet50-aspnetcore-runtime-5.0` durch `rh-dotnet50-dotnet-runtime-5.0`.

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
scl enable rh-dotnet31 bash
```

Red Hat empfiehlt nicht die dauerhafte Aktivierung von `rh-dotnet31`, da dies andere Programme beeinträchtigen könnte. So enthält beispielsweise `rh-dotnet31` eine Version von `libcurl`, die sich von der Basisversion von RHEL unterscheidet. Dies kann zu Problemen in Programmen führen, die keine andere Version von `libcurl` erwarten. Wenn Sie `rh-dotnet31` dauerhaft aktivieren möchten, fügen Sie der Datei _~/.bashrc_ die folgende Zeile hinzu.

```bash
source scl_source enable rh-dotnet31
```

Als Alternative zur ASP.NET Core-Runtime können Sie die .NET Core-Runtime installieren, die keine ASP.NET Core-Unterstützung bietet. Ersetzen Sie im obigen Befehl `rh-dotnet31-aspnetcore-runtime-3.1` durch `rh-dotnet31-dotnet-runtime-3.1`.

## <a name="dependencies"></a>Abhängigkeiten

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="how-to-install-other-versions"></a>Installieren anderer Versionen

Konsultieren Sie die [Red Hat-Dokumentation zu .NET](https://access.redhat.com/documentation/net/5.0/) hinsichtlich der Schritte, die zur Installation anderer Releases von .NET erforderlich sind.

## <a name="next-steps"></a>Nächste Schritte

- [Aktivieren der Vervollständigung mit der TAB-TASTE für die .NET-CLI](../tools/enable-tab-autocomplete.md)
- [Tutorial: Erstellen einer Konsolenanwendung mit dem .NET SDK in Visual Studio Code](../tutorials/with-visual-studio-code.md)
