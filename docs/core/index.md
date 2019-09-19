---
title: Leitfaden für .NET Core
description: .NET Core ist eine modulare, hochleistungsfähige Implementierung von .NET zur Erstellung von Windows-, Linux- und Mac-Apps. Erfahren Sie mehr über .NET Core, und legen Sie los.
author: richlander
ms.date: 08/01/2018
ms.custom: updateeachrelease
ms.openlocfilehash: a6112851a3d9b46f02c26313e6537170786df10b
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117081"
---
# <a name="net-core-guide"></a>Leitfaden für .NET Core

[.NET Core](about.md) ist eine universelle [Open Source](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT)-Entwicklungsplattform, die von Microsoft und der .NET-Community auf [GitHub](https://github.com/dotnet/core) gepflegt wird. Sie ist plattformübergreifend (d.h., sie unterstützt Windows, macOS und Linux) und kann lokal verwendet werden, um Geräte-, Cloud- und IoT-Anwendungen zu erstellen.

In den [weiteren Informationen zu .NET Core](about.md) erfahren Sie mehr über .NET Core, einschließlich den Eigenschaften, den unterstützten Sprachen und Frameworks sowie Schlüssel-APIs.

Sehen Sie sich die [.NET Core-Tutorials](tutorials/index.md) an. Dort erfahren Sie, wie Sie eine einfache .NET Core-Anwendung erstellen. Es dauert nur wenige Minuten, bis Ihre erste App einsatzbereit ist. Wenn Sie .NET Core in Ihrem Browser ausprobieren möchten, sehen Sie sich das Onlinetutorial [Zahlen in C#](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml) an.

## <a name="download-net-core-22"></a>Herunterladen von .NET Core 2.2

Laden Sie das [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download) herunter, um .NET Core auf Ihrem Windows-, macOS- oder Linux-Computer zu testen. Besuchen Sie [dotnet/core](https://hub.docker.com/_/microsoft-dotnet-core/), wenn Sie lieber Docker-Container verwenden möchten.

Alle .NET Core-Versionen sind unter den [.NET Core-Downloads](https://dotnet.microsoft.com/download/dotnet-core) verfügbar, wenn Sie nach einer anderen .NET Core-Version suchen.

## <a name="net-core-22"></a>.NET Core 2.2

[.NET Core 2.2](whats-new/dotnet-core-2-2.md) ist die neueste Version. Neue Features: frameworkabhängige Bereitstellungen, Starthooks, AAD-Authentifizierung mit Azure SQL und Unterstützung für Windows ARM32.

## <a name="create-your-first-application"></a>Erstellen Ihrer ersten Anwendung

Öffnen Sie nach der Installation von .NET Core SDK eine Eingabeaufforderung. Geben Sie die folgenden `dotnet`-Befehle ein, um eine C#-Anwendung zu erstellen und zu veröffentlichen:

```dotnetcli
dotnet new console
dotnet run
```

Die folgende Ausgabe wird angezeigt:

```output
Hello World!
```

## <a name="support"></a>Support

.NET Core wird von [Microsoft auf Windows, Mac OS und Linux unterstützt](https://dotnet.microsoft.com/platform/support/policy). Die Plattform wird aus Sicherheits- und Qualitätsgründen mehrmals im Jahr (normalerweise monatlich) aktualisiert.

Binäre .NET Core-Verteilungen werden unter Azure auf von Microsoft verwalteten Servern erstellt und getestet und genauso wie jedes andere Produkt von Microsoft unterstützt.

[Red Hat unterstützt .NET Core](http://redhatloves.net/) auf Red Hat Enterprise Linux 7 (RHEL). Red Hat erstellt .NET Core aus einer Quelle und stellt es in den [Red Hat Software Collections](https://developers.redhat.com/products/softwarecollections/overview/) zur Verfügung. Red Hat und Microsoft arbeiten eng zusammen, um sicherzustellen, dass .NET Core ebenso auf RHEL funktioniert.
