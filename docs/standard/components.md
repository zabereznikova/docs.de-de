---
title: .NET-Architekturkomponenten
description: Beschreibt wichtige .NET-Architekturkomponenten wie z.B. die .NET-Standardbibliothek, .NET-Runtimes und Tools.
keywords: .NET, .NET-Standardbibliothek, .NET-Standard, .NET Core, .NET Framework, Xamarin, MSBuild, C#, F#, VB, Compiler
author: cartermp
ms.author: mairaw
ms.date: 11/16/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 2e38e9d9-8284-46ee-a15f-199adc4f26f4
translationtype: Human Translation
ms.sourcegitcommit: 7741df222250f3746abb1e3c359bd9e89e6a732c
ms.openlocfilehash: e93764ff4d3391110c79f73a34512bd073ce0499
ms.lasthandoff: 01/18/2017

---

# <a name="net-architectural-components"></a>.NET-Architekturkomponenten

.NET besteht aus einer Reihe von Hauptkomponenten.  Dazu gehört eine Standardbibliothek namens .NET-Standardbibliothek, die eine große Sammlung von APIs darstellt, die überall ausgeführt werden können.  Diese Standardbibliothek wird von drei .NET-Runtimes implementiert: .NET Framework, .NET Core und Mono für Xamarin.  Die .NET-Sprachen können auch in einer beliebigen .NET-Runtime verwendet werden.  Darüber hinaus stehen Tools auf jeder Plattform zur Verfügung, mit denen Sie Projekte erstellen können.  Diese Tools sind immer gleich – unabhängig von der ausgewählten Runtime.

Hier sehen Sie eine grafische Übersicht der zuvor erwähnten Komponenten von .NET und deren Beziehungen zueinander.

![Alle .NET-Architekturkomponenten zusammen](media/components.png)

Im Folgenden finden Sie eine kurze Erläuterung der einzelnen oben gezeigten Hauptkomponenten.  

## <a name="net-standard-library"></a>.NET-Standardbibliothek

Die .NET-Standardbibliothek ist ein Satz von APIs, die von einer .NET-Runtime implementiert werden.

Formeller gesehen, ist es eine Spezifikation von .NET-APIs, die eine einheitliche Gruppe von Verträgen bilden, für die Sie Code kompilieren.  Diese Verträge weisen zugrunde liegende Implementierungen für jede .NET-Runtime auf.  Dadurch wird Portabilität über verschiedene .NET-Runtimes ermöglicht, sodass der Code effektiv „überall“ ausgeführt werden kann.

Die .NET-Standardbibliothek ist auch ein Buildziel mit dem Namen „.NET Standard“.  Sie können derzeit .NET Standard 1.0 - 1.6 als Ziel nutzen.  Wenn Ihr Code auf eine Version von .NET Standard abzielt, ist sichergestellt, dass er auf einer beliebigen .NET-Runtime ausgeführt werden kann, die diese Version implementiert.

Weitere Informationen über die .NET-Standardbibliothek und die Verwendung von .NET Standard als Ziel finden Sie unter [.NET-Standardbibliothek](library.md).

## <a name="net-runtimes"></a>.NET-Runtimes

Es gibt drei primäre .NET-Runtimes, die Microsoft aktiv entwickelt und verwaltet: .NET Core, .NET Framework und Mono für Xamarin.

### <a name="net-core"></a>.NET Core

.NET Core ist eine plattformübergreifende Runtime, die für Serverarbeitsauslastungen optimiert wurde.  Sie implementiert die .NET-Standardbibliothek, sodass jeder Code, der auf .NET Standard abzielt, in .NET Core ausgeführt werden kann.  Sie ist die von ASP.NET Core und der universellen Windows-Plattform (UWP) verwendete Runtime.  .NET Core ist modern, effizient und wurde für die Verarbeitung umfangreicher Server- und Cloudarbeitsauslastungen entwickelt.

Weitere Informationen zu .NET Core finden Sie im [Leitfaden für .NET Core](../core/index.md).

### <a name="net-framework"></a>.NET Framework

.NET Framework ist die .NET Runtime, die bereits seit 2002 genutzt wird.  Es ist dasselbe .NET Framework, das .NET-Entwickler schon immer verwendet haben.  .NET Framework implementiert die .NET-Standardbibliothek, sodass jeder Code, der auf .NET Standard abzielt, in .NET Framework ausgeführt werden kann.  .NET Framework enthält zusätzliche Windows-spezifische APIs, wie z.B. APIs für die Windows-Desktopentwicklung mit Windows Forms und WPF.  .NET Framework wurde für das Erstellen von Windows-Desktopanwendungen optimiert.

Weitere Informationen zu .NET Framework finden Sie im [Leitfaden für .NET Framework](../framework/index.md).

### <a name="mono-for-xamarin"></a>Mono für Xamarin

Mono ist die Runtime, die von Xamarin-Apps verwendet wird.  Sie implementiert die .NET-Standardbibliothek, sodass jeder Code, der auf .NET Standard abzielt, in Xamarin-Apps ausgeführt werden kann.  Sie enthält zusätzliche APIs für iOS, Android, Xamarin.Forms und Xamarin.Mac.  Sie wurde für die Erstellung mobiler Anwendungen unter iOS und Android optimiert.

Weitere Informationen zu Mono finden Sie in der [Mono-Dokumentation](http://www.mono-project.com/docs/).

## <a name="net-tooling-and-common-infrastructure"></a>.NET-Tools und die allgemeine Infrastruktur

Die Tools für .NET sind ebenfalls für alle Implementierungen von .NET einheitlich.  Diese umfassen unter anderem folgende:

* Die .NET-Sprachen und deren Compiler
* Runtimekomponenten, z.B. JIT und Garbage Collector
* Das .NET-Projektsystem (wird auch als „csproj“, „vbproj“ oder „fsproj“ bezeichnet)
* MSBuild, das Buildmodul, das verwendet wird, um Projekte zu erstellen
* NuGet, der Paket-Manager von Microsoft für .NET
* Die .NET-CLI, eine plattformübergreifende Befehlszeilenschnittstelle zum Erstellen von .NET-Projekten
* Open-Source-Buildorchestrierungtools, z.B. CAKE und FAKE

Der wichtigste Punkt hier ist, dass es eine große Menge an Tools und eine Infrastruktur gibt, die für alle „Konfigurationen“ von .NET, die Sie zum Erstellen von Apps auswählen, einheitlich sind.

## <a name="next-steps"></a>Nächste Schritte

Weitere Informationen finden Sie unter:

* [.NET-Standardbibliothek](library.md)
* [Leitfaden für .NET Core](../core/index.md)
* [Leitfaden für .NET Framework](../framework/index.md)
* [Leitfaden für C#](../csharp/index.md)
* [Leitfaden für F#](../fsharp/index.md)
* [Leitfaden für VB.NET](../visual-basic/index.md)

