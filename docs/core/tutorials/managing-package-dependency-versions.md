---
title: "So verwalten Sie Paketabhängigkeitsversionen für .NET Core 1.0"
description: "Erfahren Sie mehr zur Versionsverwaltung der Paketabhängigkeit für Ihre .NET Core-Bibliotheken und Apps."
keywords: .NET, .NET Core
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 4424a947-bdf9-4775-8d48-dc350a4e0aee
ms.openlocfilehash: b0d4082d020da782b334a5b3999905f7de744e64
ms.sourcegitcommit: 5d0e069655439984862a835f400058b7e8bbadc6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2017
---
# <a name="how-to-manage-package-dependency-versions-for-net-core-10"></a>So verwalten Sie Paketabhängigkeitsversionen für .NET Core 1.0

Dieser Artikel beschreibt, was Sie über Paketversionen für Ihre .NET Core-Bibliotheken und Apps wissen müssen.

## <a name="glossary"></a>Glossar

**Korrigieren** – Das Korrigieren von Abhängigkeiten bedeutet, dass Sie dieselbe Paket-„Familie“ verwenden, die auf NuGet für .NET Core 1.0 erschienen ist.

**Metapaket** – ein NuGet-Paket, dass eine Reihe NuGet-Pakete darstellt.

**Trimmen** – Entfernen der Pakete, von denen Sie nicht von einem Metapaket abhängig sind.  Dies ist nur für Autoren von NuGet-Paketen relevant.  Weitere Informationen finden Sie unter [Reducing Package Dependencies with project.json (Reduzieren von Paketabhängigkeiten mit project.json)](../deploying/reducing-dependencies.md). 

## <a name="fix-your-dependencies-to-net-core-10"></a>Korrigieren Ihrer Abhängigkeiten zu .NET Core 1.0

Um zuverlässig Pakete wiederherzustellen und zuverlässigen Code zu schreiben, ist es wichtig, dass Sie Ihre Abhängigkeiten zu der Paketversionen korrigieren, die zusammen mit .NET Core 1.0 versendet werden.  Dies bedeutet, dass jedes Paket über eine einzelne Version ohne zusätzlichen Qualifizierer verfügen muss.

**Beispiele für Pakete, die zu 1.0 korrigiert wurden**

`"System.Collections":"4.0.11"`

`"NETStandard.Library":"1.6.0"`

`"Microsoft.NETCore.App":"1.0.0"`

**Beispiele für Pakete, die NICHT zu 1.0 korrigiert wurden**

`"Microsoft.NETCore.App":"1.0.0-rc4-00454-00"`

`"System.Net.Http":"4.1.0-*"`

`"System.Text.RegularExpressions":"4.0.10-rc3-24021-00"`

### <a name="why-does-this-matter"></a>Warum ist das wichtig?

Wir garantieren, dass wenn Sie die Abhängigkeiten für welche Schiffe zusammen mit .NET Core 1.0 korrigieren, diese Pakete alle zusammenarbeiten. Diese Garantie verfällt, wenn Sie Pakete verwenden, die nicht auf diese Weise korrigiert wurden.

### <a name="scenarios"></a>Szenarien

Es gibt zwar eine umfangreiche Liste aller Pakete und deren Versionen, die mit .NET Core 1.0 veröffentlicht wurden, jedoch müssen Sie diese möglicherweise nicht durchgehen, wenn Ihr Code unter bestimmte Szenarios fällt.

**Sind Sie ausschließlich von** `NETStandard.Library` **abhängig?**

Wenn also, Sie beheben sollten Ihre `NETStandard.Library` Paket auf Version `1.6`.  Da es sich um ein geordnetes Metapaket handelt, wird dessen Paketabschluss ebenso auf 1.0 festgelegt.

**Sind Sie ausschließlich von** `Microsoft.NETCore.App` **abhängig?**

Wenn also, Sie beheben sollten Ihre `Microsoft.NETCore.App` Paket auf Version `1.0.0`.  Da es sich um ein geordnetes Metapaket handelt, wird dessen Paketabschluss ebenso auf 1.0 festgelegt.

**[Trimmen](../deploying/reducing-dependencies.md) Sie Ihre** `NETStandard.Library` **oder** `Microsoft.NETCore.App` **-Metapaketabhängigkeiten?**

Wenn dies der Fall ist, gehen Sie sicher, dass das Metapaket, mit dem Sie beginnen, zu 1.0 korrigiert wurde.  Die einzelnen Pakete, von denen Sie nach dem Trimmen abhängig sind, werden auch zu 1.0 korrigiert.

**Sind Sie von Paketen außerhalb der** `NETStandard.Library` **oder** `Microsoft.NETCore.App` **-Metapakete abhängig?**

Wenn dies der Fall ist, müssen Sie Ihre anderen Abhängigkeiten zu 1.0 korrigieren.  Sehen Sie sich die richtigen Paketversionen und Buildnummern am Ende dieses Artikels an.

### <a name="a-note-on-using-a-splat-string--when-versioning"></a>Hinweis zur Verwendung einer Splat-Zeichenfolge (\*) bei der Versionskontrolle

Sie haben womöglich ein Muster bei der Versionskontrolle übernommen, bei dem eine Splat-Zeichenfolge (\*) wie etwa die folgende verwendet wird: `"System.Collections":"4.0.11-*"`.

**Dies sollten Sie nicht tun**.  Die Verwendung einer Splat-Zeichenfolge könnte zum Wiederherstellen von Paketen aus verschiedenen Builds führen. Einige davon gehen dann möglicherweise über .NET Core 1.0 hinaus.  Dies kann dazu führen, dass einige Pakete inkompatibel werden.

## <a name="packages-and-version-numbers-organized-by-metapackage"></a>Von Metapaketen organisierte Pakete und Versionsnummern

[List of all .NET Standard packages and their versions for 1.0 (Liste aller Pakete von .NET Standard und deren Versionen für 1.0)](https://github.com/dotnet/versions/blob/master/build-info/dotnet/corefx/release/1.0.0/Latest_Packages.txt).

[Liste aller Laufzeitpakete und deren Versionen für 1.0](https://github.com/dotnet/versions/blob/master/build-info/dotnet/coreclr/release/1.0.0/LKG_Packages.txt).

[Liste aller .NET Core-Anwendungspakete und deren Versionen für 1.0](https://github.com/dotnet/versions/blob/master/build-info/dotnet/core-setup/release/1.0.0/Latest_Packages.txt).
