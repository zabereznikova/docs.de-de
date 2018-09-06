---
title: Leitfaden für .NET Core
description: .NET Core ist eine modulare, hochleistungsfähige Implementierung von .NET zur Erstellung von Windows-, Linux- und Mac-Apps. Erfahren Sie mehr über .NET Core, und legen Sie los.
author: richlander
ms.author: mairaw
ms.date: 08/01/2018
ms.custom: updateeachrelease
ms.openlocfilehash: cfa7c27871204b808c9d753a970d5abb907a183e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43512840"
---
# <a name="net-core-guide"></a>Leitfaden für .NET Core

[.NET Core](about.md) ist eine universelle [Open Source](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT)-Entwicklungsplattform, die von Microsoft und der .NET-Community auf [GitHub](https://github.com/dotnet/core) gepflegt wird. Sie ist plattformübergreifend, d.h., sie unterstützt Windows, macOS und Linux und kann lokal, in der Cloud und in IoT-Anwendungen verwendet werden.

In den [weiteren Informationen zu .NET Core](about.md) erfahren Sie mehr über .NET Core, einschließlich den Eigenschaften, den unterstützten Sprachen und Frameworks sowie Schlüssel-APIs.

Sehen Sie sich die [.NET Core-Tutorials](tutorials/index.md) an. Dort erfahren Sie, wie Sie eine einfache .NET Core-Anwendung erstellen. Es dauert nur wenige Minuten, bis Ihre erste App einsatzbereit ist. Wenn Sie .NET Core in Ihrem Browser ausprobieren möchten, sehen Sie sich den Schnellstart [„Hello World“ in C#](https://docs.microsoft.com/dotnet/csharp/quick-starts/hello-world) an.

## <a name="download-net-core-21"></a>.NET Core 2.1 herunterladen

Laden Sie das [.NET Core 2.1-SDK](https://www.microsoft.com/net/download) herunter, um .NET Core auf Ihrem Windows-, macOS- oder Linux-Computer zu testen. Besuchen Sie [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/), wenn Sie lieber Docker-Container verwenden möchten.

Alle .NET Core-Versionen sind unter den [.NET Core-Downloads](https://www.microsoft.com/net/download/archives) verfügbar, wenn Sie nach einer anderen .NET Core-Version suchen.

## <a name="net-core-21"></a>.NET Core 2.1

[.NET Core 2.1](whats-new/dotnet-core-2-1.md) ist die neueste Version. Neue Features sind unter anderem: globale Tools, Hochleistungs-APIs (z.B. <xref:System.Span%601?displayProperty=nameWithType>), mehrstufige JIT-Kompilierung, Leistungsverbesserungen für [Build](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/) und [Runtime](https://blogs.msdn.microsoft.com/dotnet/2018/04/18/performance-improvements-in-net-core-2-1/) sowie Unterstützung für Alpine und ARM32.

## <a name="create-your-first-application"></a>Erstellen Ihrer ersten Anwendung

Öffnen Sie nach der Installation von .NET Core SDK eine Eingabeaufforderung. Geben Sie die folgenden `dotnet`-Befehle ein, um eine C#-Anwendung zu erstellen und zu veröffentlichen:

```console
dotnet new console
dotnet run
```

Die folgende Ausgabe wird angezeigt:

```console
Hello World!
```

## <a name="support"></a>Unterstützung

.NET Core wird von [Microsoft auf Windows, Mac OS und Linux unterstützt](https://www.microsoft.com/net/support/policy). Die Plattform wird aus Sicherheits- und Qualitätsgründen mehrmals im Jahr (normalerweise monatlich) aktualisiert.

Binäre .NET Core-Verteilungen werden unter Azure auf von Microsoft verwalteten Servern erstellt und getestet und genauso wie jedes andere Produkt von Microsoft unterstützt.

[Red Hat unterstützt .NET Core](http://redhatloves.net/) auf Red Hat Enterprise Linux 7 (RHEL). Red Hat erstellt .NET Core aus einer Quelle und stellt es in den [Red Hat Software Collections](https://developers.redhat.com/products/softwarecollections/overview/) zur Verfügung. Red Hat und Microsoft arbeiten eng zusammen, um sicherzustellen, dass .NET Core ebenso auf RHEL funktioniert.