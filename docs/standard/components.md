---
title: .NET-Architekturkomponenten
description: Beschreibt .NET-Architekturkomponenten wie die .NET Standardbibliothek, .NET-Implementierungen sowie .NET-Runtimes und -Tools
author: cartermp
ms.author: mairaw
ms.date: 08/23/2017
ms.technology: dotnet-standard
ms.openlocfilehash: b55b2f9266477a0bb12c39840c9f2108a5c0f0c4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283920"
---
# <a name="net-architectural-components"></a>.NET-Architekturkomponenten

Eine .NET-App wird für *.NET-Implementierungen* entwickelt und wird in mindestens einer ausgeführt.  Implementierungen von .NET sind z.B. .NET Framework, .NET Core und Mono. Der .NET Standard ist die API-Spezifikation, die allen .NET-Implementierungen zugrunde liegt. Dieser Artikel bietet eine kurze Einführung in jedes dieser Konzepte.

## <a name="net-standard"></a>.NET-Standard

Der .NET Standard besteht aus einem Satz von APIs, die durch die Basisklassenbibliothek einer .NET-Implementierung implementiert werden. Formeller ausgedrückt ist es eine Spezifikation von .NET-APIs, die eine einheitliche Gruppe von Verträgen bilden, mit denen Sie Code kompilieren. Diese Verträge werden in jeder .NET-Implementierung implementiert. Dadurch wird Portabilität zwischen verschiedenen .NET-Implementierungen ermöglicht, sodass Ihr Code überall ausgeführt werden kann.

Der .NET Standard ist auch ein [Zielframework](glossary.md#target-framework). Wenn sich Ihr Code an eine Version des .NET Standards richtet, kann er auf jeder .NET-Implementierung ausgeführt werden, die diese Version des .NET Standards unterstützt.

Weitere Informationen zum .NET Standard und wie Sie dafür programmieren, finden Sie im Thema [.NET Standard](net-standard.md).

## <a name="net-implementations"></a>.NET-Implementierungen

Jede Implementierung von .NET umfasst die folgenden Komponenten:

- Mindestens eine Runtime. Beispiele: CLR für .NET Framework, CoreCLR und CoreRT für .NET Core.
- Eine Klassenbibliothek, die den .NET Standard und ggf. zusätzliche APIs implementiert. Beispiele: .NET Framework-Basisklassenbibliothek, .NET Core-Basisklassenbibliothek
- Optional mindestens ein Anwendungsframework. Beispiele: [ASP.NET](https://www.asp.net/), [Windows Forms](../framework/winforms/windows-forms-overview.md) und [Windows Presentation Foundation (WPF)](../framework/wpf/index.md) sind im .NET Framework und .NET Core enthalten.
- Optional Entwicklungstools. Einige Entwicklungstools werden zwischen mehreren Implementierungen freigegeben.

Es gibt vier primäre .NET-Implementierungen, die Microsoft aktiv entwickelt und wartet: .NET Core, .NET Framework, Mono und die universelle Windows-Plattform (UWP)

### <a name="net-core"></a>.NET Core

.NET Core ist eine plattformübergreifende Implementierung von .NET und wurde entwickelt, um Server- und Cloud-Arbeitsauslastungen nach Maß zu bewältigen. Es kann unter Windows, macOS und Linux ausgeführt werden. Damit wird der .NET Standard implementiert. Code, der auf den .NET Standard abzielt, kann also in .NET Core ausgeführt werden. [ASP.NET Core](https://dotnet.microsoft.com/learn/aspnet/what-is-aspnet-core), [Windows Forms](../framework/winforms/windows-forms-overview.md) und [Windows Presentation Foundation (WPF)](../framework/wpf/index.md) werden in .NET Core ausgeführt.

Weitere Informationen zu .NET Core finden Sie unter [Leitfaden für .NET Core](../core/index.md) und [Wahl zwischen .NET Core und .NET Framework für Server-Apps](choosing-core-framework-server.md).

### <a name="net-framework"></a>.NET Framework

Das 2002 auf den Markt gebrachte .NET Framework ist die ursprüngliche .NET-Implementierung. Dieses .NET Framework haben .NET-Entwickler seit jeher verwendet. .NET Framework 4.5 und spätere Versionen implementieren den .NET Standard. Code, der auf den .NET Standard abzielt, kann also in diesen .NET Framework-Versionen ausgeführt werden. .NET Framework enthält zusätzliche Windows-spezifische APIs, wie z.B. APIs für die Windows-Desktopentwicklung mit Windows Forms und WPF. Das .NET Framework wurde für das Erstellen von Windows-Desktopanwendungen optimiert.

Weitere Informationen zu .NET Framework finden Sie im [Leitfaden für .NET Framework](../framework/index.md).

### <a name="mono"></a>Mono

Bei Mono handelt es sich um eine .NET-Implementierung, die in erster Linie verwendet wird, wenn eine kleine Runtime erforderlich ist. Mono ist die Runtime für Xamarin-Anwendungen unter Android, Mac, iOS, tvOS und watchOS und ist hauptsächlich auf einen geringen Ressourcenbedarf ausgelegt. Mono treibt Spiele an, die mit der Unity-Engine erstellt wurden.

Außerdem unterstützt Mono alle derzeit veröffentlichten Versionen des .NET Standards.

In der Vergangenheit hat Mono die größere API des .NET Framework implementiert und einige der beliebtesten Funktionen unter Unix emuliert. Manchmal wird es zum Ausführen von .NET-Anwendungen verwendet, die auf diesen Unix-Funktionen basieren.

Mono wird in der Regel mit einem Just-In-Time-Compiler verwendet. Es enthält aber auch einen vollständig statischen Compiler (Ahead-of-time-Kompilierung), der auf Plattformen wie iOS verwendet wird.

Weitere Informationen zu Mono finden Sie in der [Mono-Dokumentation](https://www.mono-project.com/docs/).

### <a name="universal-windows-platform-uwp"></a>Universelle Windows-Plattform (UWP)

Die UWP ist eine Implementierung von .NET, mit der moderne Windows-Anwendungen für Touchscreengeräte und Software für das Internet der Dinge (Internet of Things, IoT) erstellt werden. Sie wurde als einheitliche Plattform entwickelt, um das Programmieren für ganz verschiedene Gerätetypen, von PCs, Tablets, Phablets über Smartphones bis hin zur Xbox, zu ermöglichen. Die UWP bietet viele Dienste, z.B. einen zentralen App Store, eine Ausführungsumgebung (AppContainer) und mehrere Windows-APIs, die anstelle von Win32 (WinRT) verwendet werden. Apps können auf dieser Plattform in C++, C#, VB.NET und JavaScript geschrieben werden. Die .NET-APIs für C# und VB.NET werden von .NET Core bereitgestellt.

Weitere Informationen zur UWP finden Sie unter [Einführung in die universelle Windows-Plattform](/windows/uwp/get-started/universal-application-platform-guide).

## <a name="net-runtimes"></a>.NET-Runtimes

Eine Laufzeit ist die Ausführungsumgebung eines verwalteten Programms. Das Betriebssystem ist Teil der Laufzeitumgebung, gehört jedoch nicht zur .NET-Runtime. Dies sind einige Beispiele für .NET-Runtimes:

- Die Common Language Runtime (CLR) für das .NET Framework
- Die Core Common Language Runtime (CoreCLR) für .NET Core
- .NET Native für die universelle Windows-Plattform 
- Die Mono-Runtime für Xamarin.iOS, Xamarin.Android, Xamarin.Mac und das Mono-Desktopframework

## <a name="net-tooling-and-common-infrastructure"></a>.NET-Tools und die allgemeine Infrastruktur

Es stehen verschiedene Tools und Infrastrukturkomponenten zur Verfügung, die in allen Implementierungen von .NET funktionieren, u.a.:

- Die .NET-Sprachen und deren Compiler
- Das .NET-Projektsystem, das auf *CSPROJ*-, *VBPROJ*- und *FSPROJ*-Dateien basiert)
- [MSBuild](/visualstudio/msbuild/msbuild), die Build-Engine, mit dem Projekte erstellt werden
- [NuGet](/nuget/), der Paket-Manager von Microsoft für .NET
- Open-Source-Buildorchestrierungtools, z.B. [CAKE](https://cakebuild.net/) und [FAKE](https://fake.build/)

## <a name="applicable-standards"></a>Anwendbare Standards

Die Spezifikationen für die Sprache C# und die CLI (Common Language Infrastructure) werden über [Ecma International®](https://www.ecma-international.org/) standardisiert. Die erste Ausgabe dieser Standards wurde von Ecma im Dezember 2001 veröffentlicht.

Nachfolgende Überarbeitungen der Standards wurden von den Arbeitsgruppen TC49-TG2 (C#) und TC49-TG3 (CLI) innerhalb des Programming Languages Technical Committee ([TC49](https://www.ecma-international.org/memento/tc49.htm)) entwickelt und von der Ecma General Assembly und anschließend von ISO/IEC JTC 1 im Rahmen des ISO Fast-Track-Prozesses übernommen.

### <a name="latest-standards"></a>Aktuelle Standards

Die folgenden offiziellen Ecma-Dokumente sind für [C#](http://www.ecma-international.org/publications/standards/Ecma-334.htm) und die [CLI](http://www.ecma-international.org/publications/standards/Ecma-335.htm) ([TR-84](http://www.ecma-international.org/publications/techreports/E-TR-084.htm)) verfügbar:

- **The C# Language Standard (version 5.0)** (Sprachstandard für C# [Version 5.0]): [ECMA-334.pdf](https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-334.pdf)
- **The Common Language Infrastructure** (Die Common Language Infrastructure): Das Dokument ist im [PDF](https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-335.pdf)- oder [ZIP](https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-335.zip)-Format verfügbar.
- **Information Derived from the Partition IV XML File** (Aus Partition IV der XML-Datei abgeleitete Informationen): Das Dokument ist im [PDF](https://www.ecma-international.org/publications/files/ECMA-TR/ECMA%20TR-084.pdf)- oder [ZIP](https://www.ecma-international.org/publications/files/ECMA-TR/TR-084.zip)-Format verfügbar.
 
Die offiziellen ISO/IEC-Dokumente sind auf der ISO/IEC-Seite [Publicly Available Standards](https://standards.iso.org/ittf/PubliclyAvailableStandards/) (Öffentlich verfügbare Standards) erhältlich. Diese Links stammen direkt von dieser Seite:

- **Information technology - Programming languages - C#** (Informationstechnologie – Programmiersprachen – C#): [ISO/IEC 23270:2018](https://standards.iso.org/ittf/PubliclyAvailableStandards/c075178_ISO_IEC_23270_2018.zip)
- **Information technology – Common Language Infrastructure (CLI) Partitions I to VI** (Informationstechnologie – Common Language Infrastructure (CLI), Partitionen I bis VI) [ISO/IEC 23271:2012](https://standards.iso.org/ittf/PubliclyAvailableStandards/c058046_ISO_IEC_23271_2012(E).zip)
- **Information technology – Common Language Infrastructure (CLI) – Technical Report on Information Derived from Partition IV XML File** (Informationstechnologie – Common Language Infrastructure (CLI) – Technischer Bericht zu Informationen, die aus Partition IV der XML-Datei abgeleitet sind): [ISO/IEC TR 23272:2011](https://standards.iso.org/ittf/PubliclyAvailableStandards/c057955_ISO_IEC_TR_23272_2011.zip)

## <a name="see-also"></a>Siehe auch

- [Wahl zwischen .NET Core und .NET Framework für Server-Apps](choosing-core-framework-server.md)
- [.NET-Standard](net-standard.md)
- [Leitfaden für .NET Core](../core/index.md)
- [Leitfaden für .NET Framework](../framework/index.md)
- [Leitfaden für C#](../csharp/index.yml)
- [Leitfaden für F#](../fsharp/index.md)
- [Leitfaden für VB.NET](../visual-basic/index.md)
