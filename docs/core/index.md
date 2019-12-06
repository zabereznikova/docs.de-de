---
title: Leitfaden für .NET Core
description: .NET Core ist eine modulare, hochleistungsfähige Implementierung von .NET zur Erstellung von Windows-, Linux- und Mac-Apps. Erfahren Sie mehr über .NET Core, und legen Sie los.
author: richlander
ms.date: 12/04/2019
ms.custom: updateeachrelease
ms.openlocfilehash: b2622dba53d64c9dcf58e852d57de117fe79eb2e
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837011"
---
# <a name="net-core-guide"></a>Leitfaden für .NET Core

[.NET Core](about.md) ist eine universelle [Open Source](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT)-Entwicklungsplattform, die von Microsoft und der .NET-Community auf [GitHub](https://github.com/dotnet/core) gepflegt wird. Sie ist plattformübergreifend (d.h., sie unterstützt Windows, macOS und Linux) und kann lokal verwendet werden, um Geräte-, Cloud- und IoT-Anwendungen zu erstellen.

In den [weiteren Informationen zu .NET Core](about.md) erfahren Sie mehr über .NET Core, einschließlich den Eigenschaften, den unterstützten Sprachen und Frameworks sowie Schlüssel-APIs.

Sehen Sie sich die [.NET Core-Tutorials](tutorials/index.md) an. Dort erfahren Sie, wie Sie eine einfache .NET Core-Anwendung erstellen. Es dauert nur wenige Minuten, bis Ihre erste App einsatzbereit ist. Wenn Sie .NET Core in Ihrem Browser ausprobieren möchten, sehen Sie sich das Onlinetutorial [Zahlen in C#](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml) an.

## <a name="download-net-core"></a>Herunterladen von .NET Core

Laden Sie das [.NET Core SDK](https://www.microsoft.com/net/download) herunter, um .NET Core auf Ihrem Windows-, macOS- oder Linux-Computer zu testen. Wenn Sie lieber Docker-Container verwenden möchten, besuchen Sie [.NET Core Docker Hub](https://hub.docker.com/_/microsoft-dotnet-core/).

Alle .NET Core-Versionen sind unter den [.NET Core-Downloads](https://dotnet.microsoft.com/download/dotnet-core) verfügbar, wenn Sie nach einer anderen .NET Core-Version suchen.

## <a name="net-core-31"></a>.NET Core 3.1

.NET Core 3.1 ist die neueste Version. Darin enthalten sind geringfügige Verbesserungen im Vergleich zu .NET Core 3.0. Allerdings ist .NET Core 3.1 ein langfristig unterstütztes Release. Weitere Informationen zum .NET Core 3.1-Release finden Sie unter [Neuerungen in .NET Core 3.1](./whats-new/dotnet-core-3-1.md).

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

.NET Core wird von [Microsoft auf Windows, macOS und Linux unterstützt](https://dotnet.microsoft.com/platform/support/policy). Die Plattform wird aus Sicherheits- und Qualitätsgründen mehrmals im Jahr (normalerweise monatlich) aktualisiert.

Binäre .NET Core-Verteilungen werden unter Azure auf von Microsoft verwalteten Servern erstellt und getestet und genauso wie jedes andere Produkt von Microsoft unterstützt.

[Red Hat unterstützt .NET Core](http://redhatloves.net/) auf Red Hat Enterprise Linux 7 (RHEL). Red Hat erstellt .NET Core aus einer Quelle und stellt es in den [Red Hat Software Collections](https://developers.redhat.com/products/softwarecollections/overview/) zur Verfügung. Red Hat und Microsoft arbeiten eng zusammen, um sicherzustellen, dass .NET Core ebenso auf RHEL funktioniert.
