---
title: "Portieren auf .NET Core – Analysieren der Abhängigkeiten von Drittanbietern | Microsoft-Dokumentation"
description: "Portieren auf .NET Core – Analysieren der Abhängigkeiten von Drittanbietern"
keywords: .NET, .NET Core
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: b446e9e0-72f6-48f6-92c6-70ad0ce3f86a
ms.translationtype: Human Translation
ms.sourcegitcommit: 9cd469dfd4f38605f1455c008388ad04c366e484
ms.openlocfilehash: c4c97f7f1aa6f574e4acae91320c92c2a76147ea
ms.contentlocale: de-de
ms.lasthandoff: 06/20/2017

---

<a id="porting-to-net-core---analyzing-your-third-party-party-dependencies" class="xliff"></a>

# Portieren auf .NET Core – Analysieren der Abhängigkeiten von Drittanbietern

Der erste Schritt bei der Portierung besteht darin, die Abhängigkeiten von Drittanbietern zu verstehen.  Sie müssen herausfinden, welche gegebenenfalls noch nicht unter .NET Core ausgeführt werden und für diese einen Notfallplan entwickeln.

<a id="prerequisites" class="xliff"></a>

## Erforderliche Komponenten

In diesem Artikel wird davon ausgegangen, dass Sie Windows und Visual Studio sowie Code verwenden, der derzeit auf .NET Framework ausgeführt wird.

<a id="analyzing-nuget-packages" class="xliff"></a>

## Analysieren von NuGet-Paketen

Die Analyse von NuGet-Paketen für Portabilität ist sehr einfach.  Da ein NuGet-Paket selbst eine Reihe von Ordnern darstellt, die plattformspezifische Assemblys enthalten, müssen Sie lediglich überprüfen, ob ein Ordner mit einer .NET Core-Assembly vorhanden ist.

Am einfachsten überprüfen Sie die NuGet-Paket-Ordner mit dem Tool [NuGet-Paket-Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer).  Und so gehen Sie dabei vor.

1. Laden Sie den NuGet-Paket-Explorer herunter, und öffnen Sie ihn.
2. Klicken Sie auf „Open package from online feed“ (Paket im Online-Feed öffnen).
3. Suchen Sie nach dem Namen des Pakets.
4. Erweitern Sie den Ordner „Lib“ auf der rechten Seite, und suchen Sie in den Ordnernamen.

Unter [nuget.org](https://www.nuget.org/) können Sie im Abschnitt **Dependencies** (Abhängigkeiten) der Seite für dieses Paket auch sehen, was von einem Paket unterstützt wird.

In beiden Fällen müssen Sie unter [nuget.org](https://www.nuget.org/) nach einem Ordner oder Eintrag mit einem der folgenden Namen suchen:

```
netstandard1.0
netstandard1.1
netstandard1.2
netstandard1.3
netstandard1.4
netstandard1.5
netstandard1.6
netcoreapp1.0
portable-net45-win8
portable-win8-wpa8
portable-net451-win81
portable-net45-win8-wpa8-wpa81
```

Hierbei handelt es sich um Target Framework Moniker (TFM), die den Versionen der [.NET-Standardbibliothek](../../standard/net-standard.md) und den herkömmlichen PCL-Profilen (Portable Class Library) zugeordnet sind, die mit .NET Core kompatibel sind.  Beachten Sie, dass `netcoreapp1.0` zwar kompatibel ist, jedoch nicht für Bibliotheken, sondern für Anwendungen verwendet wird.  Sie können zwar eine `netcoreapp1.0`-basierte Bibliothek verwenden, diese wird jedoch von anderen `netcoreapp1.0`-Anwendungen möglicherweise für nichts *anderes* als für den Verbrauch verwendet.

Es gibt auch einige ältere TFMs, die in Vorabversionen von .NET Core verwendet wurden, die möglicherweise ebenfalls kompatibel sind:

```
dnxcore50
dotnet5.0
dotnet5.1
dotnet5.2
dotnet5.3
dotnet5.4
dotnet5.5
```

**Die Wahrscheinlichkeit ist hoch, dass diese mit Ihrem Code funktionieren, eine Garantie für die Kompatibilität besteht jedoch nicht**.  Pakete mit diesen TFMs wurden mit der Vorabversion von .NET Core-Paketen erstellt.  Achten Sie darauf, wann (oder ob) Pakete wie dieses so aktualisiert werden, dass sie auf `netstandard` basieren.

> [!NOTE]
> Wenn Sie ein Paket auf eine herkömmliche PCL oder Vorabversion von .NET Core ausrichten möchten, müssen Sie die `imports`-Anweisung in Ihrer `project.json`-Datei verwenden.

<a id="what-to-do-when-your-nuget-package-dependency-doesnt-run-on-net-core" class="xliff"></a>

### Vorgehensweise, wenn die NuGet-Paket-Abhängigkeit unter .NET Core nicht ausgeführt wird

Es gibt einige Dinge, die Sie tun können, wenn ein NuGet-Paket, auf das Sie angewiesen sind, unter .NET Core nicht ausgeführt wird.

1. Wenn es sich um ein Open Source-Projekt handelt, das beispielsweise von GitHub gehostet wird, können Sie sich direkt an den oder die Entwickler wenden.
2. Über [nuget.org](https://www.nuget.org/) können Sie sich direkt an den Entwickler wenden, indem Sie nach dem Paket suchen und links auf der Seite des Pakets auf „Contact Owners“ (An Besitzer wenden) klicken.
3. Sie können nach einem anderen Paket suchen, das unter .NET Core ausgeführt wird und denselben Zweck erfüllt wie das Paket, das Sie bisher verwendet haben.
4. Sie können den vom Paket ausgeführten Code selbst schreiben.
5. Sie können die Abhängigkeit für das Paket eliminieren, indem Sie die Funktionalität Ihrer Anwendung ändern, zumindest bis eine kompatible Version des Pakets verfügbar ist.

Denken Sie daran, dass Betreiber von Open Source-Projekten und Herausgeber von NuGet-Paketen häufig ehrenamtlich tätig sind, sich kostenlos um einen bestimmten Bereich kümmern, und ansonsten einer anderen Tätigkeit nachgehen. Wenn Sie bei ihnen anfragen, sollten Sie mit einer positiven Äußerung zu der Bibliothek beginnen, bevor Sie um Unterstützung bei .NET Core bitten.

Wenn es Ihnen mit den genannten Vorschlägen nicht gelingt, Ihr Problem zu beheben, müssen Sie sich mit dem Portieren auf .NET Core noch etwas gedulden.

Das .NET-Team würde gerne wissen, welche Bibliotheken als Nächstes von .NET Core unterstützt werden sollten. Sie können uns gerne per E-Mail an dotnet@microsoft.com mitteilen, welche Bibliotheken Sie gerne verwenden würden.

<a id="analyzing-dependencies-which-arent-nuget-packages" class="xliff"></a>

## Analysieren von Abhängigkeiten, bei denen es sich nicht um NuGet-Pakete handelt

Möglicherweise verfügen Sie über eine Abhängigkeit, bei der es sich nicht um ein NuGet-Paket, sondern beispielsweise um eine DLL im Dateisystem handelt.  Wenn Sie feststellen möchten, ob diese Abhängigkeit portiert werden kann, haben Sie nur die Möglichkeit, das Tool [ApiPort](https://github.com/Microsoft/dotnet-apiport/blob/master/docs/HowTo/) auszuführen.

<a id="next-steps" class="xliff"></a>

## Nächste Schritte

Wenn Sie eine Bibliothek portieren, lesen Sie [Portieren von Bibliotheken](libraries.md).

