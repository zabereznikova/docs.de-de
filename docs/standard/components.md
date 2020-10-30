---
title: .NET-Architekturkomponenten
description: Hier werden .NET-Architekturkomponenten wie .NET Standard, .NET-Implementierungen, .NET-Runtimes und Tools beschrieben.
author: cartermp
ms.date: 10/05/2020
ms.technology: dotnet-standard
ms.openlocfilehash: 316063dbcfba5c92b4a9c6a17051e0a7fc178a3a
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2020
ms.locfileid: "92224387"
---
# <a name="net-architectural-components"></a>.NET-Architekturkomponenten

Eine .NET-App wird für *.NET-Implementierungen* entwickelt und wird in mindestens einer ausgeführt. Implementierungen von .NET sind z. B. das .NET Framework, .NET 5 (und .NET Core) und Mono. .NET Standard ist die API-Spezifikation, die mehreren .NET-Implementierungen zugrunde liegt. Dieser Artikel bietet eine kurze Einführung in jedes dieser Konzepte.

## <a name="net-standard"></a>.NET Standard

.NET Standard besteht aus einem Satz von APIs, die durch die Basisklassenbibliothek einer .NET-Implementierung implementiert werden. Formeller ausgedrückt ist es eine Spezifikation von .NET-APIs, die eine einheitliche Gruppe von Verträgen bilden, mit denen Sie Code kompilieren. Diese Verträge sind Teil mehrerer .NET-Implementierungen.

.NET Standard ist ein [Zielframework](glossary.md#target-framework). Wenn Ihr Code auf eine bestimmte .NET Standard-Version ausgerichtet ist, kann er auf jeder .NET-Implementierung ausgeführt werden, die diese .NET Standard-Version unterstützt.

.NET Standard wurde erstellt, um die Portabilität über verschiedene .NET-Implementierungen hinweg zu ermöglichen. Jetzt bietet allerdings .NET 5 eine bessere Möglichkeit, Code über mehrere Plattformen und Workloads hinweg gemeinsam zu nutzen. Weitere Informationen finden Sie unter [.NET 5 und .NET Standard](net-standard.md#net-5-and-net-standard).

## <a name="net-implementations"></a>.NET-Implementierungen

Jede Implementierung von .NET umfasst die folgenden Komponenten:

- Mindestens eine Runtime. z. B.: .NET Framework-CLR und .NET 5-CLR
- eine Klassenbibliothek, z. B. .NET Framework-Basisklassenbibliothek, .NET 5-Basisklassenbibliothek
- Optional mindestens ein Anwendungsframework. Beispiele: [ASP.NET](https://www.asp.net/), [Windows Forms](/dotnet/desktop/winforms/windows-forms-overview) und [Windows Presentation Foundation (WPF)](/dotnet/desktop/wpf/) sind im .NET Framework und in .NET 5 enthalten.
- Optional Entwicklungstools. Einige Entwicklungstools werden zwischen mehreren Implementierungen freigegeben.

Es gibt vier .NET-Implementierungen, die von Microsoft unterstützt werden:

- .NET 5 (und .NET Core) und höhere Versionen:
- .NET Framework
- Mono
- UWP

.NET 5 ist nun die primäre Implementierung, auf die aktuell bei der Entwicklung der Fokus gelegt wird. .NET 5 basiert auf einer einzelnen Codebasis, die mehrere Plattformen und viele Workloads unterstützt, z. B. Windows-Desktop-Apps und plattformübergreifende Konsolen-Apps, Cloud-Dienste und Websites.

### <a name="net-5"></a>.NET 5

.NET 5 ist eine plattformübergreifende Implementierung von .NET und wurde entwickelt, um größere Server- und Cloudworkloads zu verarbeiten. Außerdem werden andere Workloads unterstützt, einschließlich Desktop-Apps. Diese Implementierung kann unter Windows, macOS und Linux ausgeführt werden. Damit wird .NET Standard implementiert. Code, der auf .NET Standard ausgerichtet ist, kann also in .NET 5 ausgeführt werden. [ASP.NET Core](https://dotnet.microsoft.com/learn/aspnet/what-is-aspnet-core), [Windows Forms](/dotnet/desktop/winforms/windows-forms-overview) und [Windows Presentation Foundation (WPF)](/dotnet/desktop/wpf/) werden in .NET 5 ausgeführt.

Weitere Informationen finden Sie in den folgenden Ressourcen:

- [Einführung in .NET](../core/introduction.md)
- [.NET 5 für Server-Apps im Vergleich zum .NET Framework](choosing-core-framework-server.md)
- [.NET 5 und .NET Standard](net-standard.md#net-5-and-net-standard)

### <a name="net-framework"></a>.NET Framework

.NET Framework ist die ursprüngliche .NET-Implementierung, die 2002 auf den Markt gebracht wurde. .NET Framework 4.5 und höhere Versionen implementieren .NET Standard. Code, der auf .NET Standard abzielt, kann also in diesen .NET Framework-Versionen ausgeführt werden. .NET Framework enthält zusätzliche Windows-spezifische APIs, wie z.B. APIs für die Windows-Desktopentwicklung mit Windows Forms und WPF. .NET Framework wurde für das Erstellen von Windows-Desktopanwendungen optimiert.

Weitere Informationen finden Sie im [Leitfaden zum .NET Framework](../framework/index.yml).

### <a name="mono"></a>Mono

Bei Mono handelt es sich um eine .NET-Implementierung, die in erster Linie verwendet wird, wenn eine kleine Runtime erforderlich ist. Mono ist die Runtime für Xamarin-Anwendungen unter Android, macOS, iOS, tvOS und watchOS und ist hauptsächlich auf einen geringen Ressourcenbedarf ausgelegt. Mono treibt Spiele an, die mit der Unity-Engine erstellt wurden.

Außerdem unterstützt Mono alle derzeit veröffentlichten Versionen von .NET Standard.

In der Vergangenheit hat Mono die größere API des .NET Framework implementiert und einige der beliebtesten Funktionen unter Unix emuliert. Manchmal wird es zum Ausführen von .NET-Anwendungen verwendet, die auf diesen Unix-Funktionen basieren.

Mono wird in der Regel mit einem Just-In-Time-Compiler verwendet. Es enthält aber auch einen vollständig statischen Compiler (Ahead-of-time-Kompilierung), der auf Plattformen wie iOS verwendet wird.

Weitere Informationen finden Sie in der [Mono-Dokumentation](https://www.mono-project.com/docs/):

### <a name="universal-windows-platform-uwp"></a>Universelle Windows-Plattform (UWP)

Die UWP ist eine Implementierung von .NET, mit der moderne Windows-Anwendungen für Touchscreengeräte und Software für das Internet der Dinge (Internet of Things, IoT) erstellt werden. Sie wurde als einheitliche Plattform entwickelt, um das Programmieren für verschiedene Gerätetypen, von PCs, Tablets und Smartphones bis hin zur Xbox, zu ermöglichen. Die UWP bietet viele Dienste, z.B. einen zentralen App Store, eine Ausführungsumgebung (AppContainer) und mehrere Windows-APIs, die anstelle von Win32 (WinRT) verwendet werden. Apps können in C++, C#, Visual Basic und JavaScript geschrieben werden.

Weitere Informationen finden Sie in der [Einführung in die Universelle Windows-Plattform](/windows/uwp/get-started/universal-application-platform-guide).

## <a name="net-runtimes"></a>.NET-Runtimes

Eine Laufzeit ist die Ausführungsumgebung eines verwalteten Programms. Das Betriebssystem ist Teil der Laufzeitumgebung, gehört jedoch nicht zur .NET-Runtime. Dies sind einige Beispiele für .NET-Runtimes:

- Die Common Language Runtime (CLR) für das .NET Framework
- Die Common Language Runtime (CLR) für .NET 5
- .NET Native für die universelle Windows-Plattform
- Die Mono-Runtime für Xamarin.iOS, Xamarin.Android, Xamarin.Mac und das Mono-Desktopframework

## <a name="net-tooling-and-common-infrastructure"></a>.NET-Tools und die allgemeine Infrastruktur

Es stehen verschiedene Tools und Infrastrukturkomponenten zur Verfügung, die in allen Implementierungen von .NET funktionieren, Zu diesen Tools und Komponenten zählen:

- Die .NET-Sprachen und deren Compiler
- Das .NET-Projektsystem, das auf *CSPROJ* -, *VBPROJ* - und *FSPROJ* -Dateien basiert)
- [MSBuild](/visualstudio/msbuild/msbuild), die Build-Engine, mit dem Projekte erstellt werden
- [NuGet](/nuget/), der Paket-Manager von Microsoft für .NET
- Open-Source-Buildorchestrierungtools, z.B. [CAKE](https://cakebuild.net/) und [FAKE](https://fake.build/)

Weitere Informationen finden Sie unter [Tools und Produktivität](../core/introduction.md#tools-and-productivity).

## <a name="applicable-standards"></a>Anwendbare Standards

Die Spezifikationen für die Sprache C# und die CLI (Common Language Infrastructure) werden über [Ecma International&reg;](https://www.ecma-international.org/) standardisiert. Die erste Ausgabe dieser Standards wurde von Ecma im Dezember 2001 veröffentlicht.

Nachfolgende Überarbeitungen der Standards wurden von den Arbeitsgruppen TC49-TG2 (C#) und TC49-TG3 (CLI) innerhalb des Programming Languages Technical Committee ([TC49](https://www.ecma-international.org/memento/tc49.htm)) entwickelt und von der Ecma General Assembly und anschließend von ISO/IEC JTC 1 im Rahmen des ISO Fast-Track-Prozesses übernommen.

### <a name="latest-standards"></a>Aktuelle Standards

Die folgenden offiziellen Ecma-Dokumente sind für [C#](http://www.ecma-international.org/publications/standards/Ecma-334.htm) und die [CLI](http://www.ecma-international.org/publications/standards/Ecma-335.htm) ([TR-84](http://www.ecma-international.org/publications/techreports/E-TR-084.htm)) verfügbar:

- **The C# Language Standard (version 5.0)** (Sprachstandard für C# [Version 5.0]): [ECMA-334.pdf](https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-334.pdf)
- **The Common Language Infrastructure** (Die Common Language Infrastructure): Verfügbar im [PDF](https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-335.pdf)- oder [ZIP](https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-335.zip)-Format.
- **Information Derived from the Partition IV XML File** (Aus Partition IV der XML-Datei abgeleitete Informationen): Verfügbar im [PDF](https://www.ecma-international.org/publications/files/ECMA-TR/ECMA%20TR-084.pdf)- oder [ZIP](https://www.ecma-international.org/publications/files/ECMA-TR/TR-084.zip)-Format.

Die offiziellen ISO/IEC-Dokumente sind auf der ISO/IEC-Seite [Publicly Available Standards](https://standards.iso.org/ittf/PubliclyAvailableStandards/) (Öffentlich verfügbare Standards) erhältlich. Diese Links stammen direkt von dieser Seite:

- **Information technology - Programming languages - C#** (Informationstechnologie – Programmiersprachen – C#): [ISO/IEC 23270:2018](https://standards.iso.org/ittf/PubliclyAvailableStandards/c075178_ISO_IEC_23270_2018.zip)
- **Information technology – Common Language Infrastructure (CLI) Partitions I to VI** (Informationstechnologie – Common Language Infrastructure (CLI), Partitionen I bis VI) [ISO/IEC 23271:2012](https://standards.iso.org/ittf/PubliclyAvailableStandards/c058046_ISO_IEC_23271_2012(E).zip)
- **Information technology – Common Language Infrastructure (CLI) – Technical Report on Information Derived from Partition IV XML File** (Informationstechnologie – Common Language Infrastructure (CLI) – Technischer Bericht zu Informationen, die aus Partition IV der XML-Datei abgeleitet sind): [ISO/IEC TR 23272:2011](https://standards.iso.org/ittf/PubliclyAvailableStandards/c057955_ISO_IEC_TR_23272_2011.zip)

## <a name="see-also"></a>Siehe auch

- [Einführung in .NET](../core/introduction.md)
- [Einführung in .NET Standard](net-standard.md)
- [.NET 5 für Server-Apps im Vergleich zum .NET Framework](choosing-core-framework-server.md)
- [Leitfaden für .NET Framework](../framework/index.yml)
- [Leitfaden für C#](../csharp/index.yml)
- [Leitfaden für F#](../fsharp/index.yml)
- [Leitfaden für Visual Basic](../visual-basic/index.yml)
