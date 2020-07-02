---
title: Erste Schritte mit .NET Framework
description: Beginnen Sie mit der Verwendung von .NET, der Runtimeumgebung für die Verwaltung von Apps. Diese enthält eine Common Language Runtime (CLR) und eine umfangreiche Klassenbibliothek.
ms.custom: updateeachrelease
ms.date: 04/02/2019
helpviewer_keywords:
- .NET Framework, getting started
- getting started [.NET Framework]
ms.assetid: c693fd34-88fe-4d90-b332-19eeadf3b7e7
ms.openlocfilehash: b6ad74d2984443a3b8345c2261996e7ab30acdff
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621651"
---
# <a name="get-started-with-net-framework"></a>Erste Schritte mit .NET Framework

.NET Framework ist eine Ausführungsumgebung für die Laufzeit, die Apps für .NET Framework verwaltet. Sie besteht aus der Common Language Runtime, die Speicherverwaltung und andere Systemdienste bereitstellt, und einer umfangreichen Klassenbibliothek, die Programmierern stabilen, zuverlässigen Code für alle wesentlichen Bereiche der App-Entwicklung zur Verfügung stellt.

> [!NOTE]
> .NET Framework ist ausschließlich auf Windows-Systemen verfügbar. Sie können [.NET Core](../../core/index.yml) verwenden, um Apps unter Windows, macOS und Linux zu entwickeln und auszuführen.

## <a name="what-is-net-framework"></a>Was ist .NET Framework?

.NET Framework ist eine verwaltete Ausführungsumgebung für Windows, die eine Vielzahl von Diensten für die darin ausgeführten Apps bereitstellt. Sie besteht aus zwei Hauptkomponenten: der CLR (Common Language Runtime), die als Ausführungs-Engine die ausgeführten Apps behandelt, und der .NET Framework-Klassenbibliothek, einer Bibliothek mit getestetem, wiederverwendbarem Code, den Entwickler in ihren eigenen Apps aufrufen können. Zu den Diensten, die .NET Framework für ausgeführte Apps bereitstellt, gehören:

- Speicherverwaltung. Bei vielen Programmiersprachen sind die Programmierer für das Zuordnen und Freigeben von Arbeitsspeicher und das Behandeln der Objektlebensdauer zuständig. In .NET Framework-Apps stellt die CLR diese Dienste für die Apps zur Verfügung.

- Ein allgemeines Typsystem. In herkömmlichen Programmiersprachen werden grundlegende Typen durch den Compiler definiert. Dies erschwert die sprachübergreifende Interoperabilität. In .NET Framework werden grundlegende Typen durch das .NET Framework-Typsystem definiert und werden von allen von .NET Framework unterstützten Sprachen verwendet.

- Eine umfangreiche Klassenbibliothek. Statt große Mengen von Code schreiben zu müssen, um allgemeine Programmiervorgänge auf niedriger Ebene zu behandeln, greifen Programmierer in der .NET Framework-Klassenbibliothek auf eine sofort verfügbare Bibliothek von Typen und deren Member zu.

- Entwicklungsframeworks und -Technologien. .NET Framework enthält Bibliotheken für bestimmte Bereiche der App-Entwicklung, beispielsweise ASP.NET für Web-Apps, ADO.NET für den Datenzugriff, Windows Communication Foundation für dienstorientierte Apps und Windows Presentation Foundation für Windows-Desktop-Apps.

- Sprachinteroperabilität. Sprachcompiler für .NET Framework geben einen temporären Code namens CIL (Common Intermediate Language) aus, der zur Laufzeit wiederum von der Common Language Runtime kompiliert wird. Mit dieser Funktion sind die Routinen, die in einer Sprache geschrieben werden, für andere Sprachen verfügbar, und Programmierer können sich auf das Erstellen von Apps in ihren bevorzugten Sprachen konzentrieren.

- Versionskompatibilität. Mit wenigen Ausnahmen können Apps, die mit einer bestimmten Version von .NET Framework entwickelt wurden, ohne Änderungen unter einer höheren Version ausgeführt werden.

- Parallele Ausführung. .NET Framework unterstützt das Lösen von Versionskonflikten, da mehrere Versionen der Common Language Runtime gleichzeitig auf dem gleichen Computer vorhanden sein können. Dies bedeutet, dass mehrere Versionen von Apps gleichzeitig vorhanden sein können, und dass eine App unter der Version von .NET Framework ausgeführt werden kann, mit der sie erstellt wurde. Die parallele Ausführung gilt für die .NET Framework-Versionsgruppen 1.0/1.1, 2.0/3.0/3.5 und 4/4.5.x/4.6.x/4.7.x/4.8.

- Festlegung von Zielversionen. Da Entwickler [.NET Standard](../../standard/net-standard.md) als Ziel verwenden, erstellen sie Klassenbibliotheken, die auf mehreren .NET Framework-Plattformen funktionieren, die von .NET Standard unterstützt werden. Beispielsweise können Bibliotheken, die .NET Standard 2.0 als Ziel verwenden, von Apps verwendet werden, die .NET Framework 4.6.1, .NET Core 2.0 und UWP 10.0.16299 als Ziel verwenden.

<a name="ForUsers"></a>
## <a name="the-net-framework-for-users"></a>.NET Framework für Benutzer

Wenn Sie .NET Framework-Apps nicht entwickeln, sondern sie nur verwenden, müssen Sie sich nicht mit .NET Framework oder der Arbeitsweise von .NET Framework auskennen. Der größte Teil von .NET Framework ist für Benutzer vollständig transparent.

Wenn Sie Windows als Betriebssystem verwenden, ist .NET Framework möglicherweise bereits auf dem Computer installiert. Wenn Sie eine App installieren, die .NET Framework erfordert, installiert das Setupprogramm der App möglicherweise eine bestimmte Version des Frameworks auf dem Computer. In einigen Fällen wird möglicherweise ein Dialogfeld angezeigt, in dem Sie aufgefordert werden, .NET Framework zu installieren. Wenn Sie gerade versucht haben, eine App auszuführen, und dieses Dialogfeld angezeigt wird, können Sie, sofern Sie über Internetzugang verfügen, zu einer Website wechseln, über die Sie die fehlende .NET Framework-Version installieren können. Weitere Informationen finden Sie im [Installationshandbuch](../install/index.md).

Im Allgemeinen sollten Sie keine der .NET Framework-Versionen deinstallieren, die auf Ihrem Computer installiert sind. Hierfür gibt es zwei Gründe:

- Wenn eine App, die Sie verwenden, von einer bestimmten Version von .NET Framework abhängt, können Fehler in dieser App entstehen, wenn diese Version entfernt wird.

- Einige Versionen von .NET Framework sind direkte Updates früherer Versionen. So ist z. B. .NET Framework 3.5 ein direktes Update für Version 2.0 und .NET Framework 4.8 ein direktes Update für die Versionen 4 bis 4.7.2. Weitere Informationen finden Sie unter [.NET Framework-Versionen und -Abhängigkeiten](../migration-guide/versions-and-dependencies.md).

Wenn Sie .NET Framework unter Windows-Versionen vor Windows 8 entfernen möchten, verwenden Sie immer **Programme und Funktionen** in der Systemsteuerung, um das Framework zu deinstallieren. Entfernen Sie .NET Framework-Versionen nie manuell. Unter Windows 8 und höher ist .NET Framework eine Komponente des Betriebssystems und kann nicht separat deinstalliert werden.

Mehrere Versionen von .NET Framework können gleichzeitig auf einem Computer vorhanden sein. Dies bedeutet, dass Sie ältere Versionen nicht deinstallieren müssen, um eine höhere Version zu installieren.

## <a name="net-framework-for-developers"></a>.NET Framework für Entwickler

Wenn Sie ein Entwickler sind, können Sie Apps in jeder beliebigen Programmiersprache erstellen, die .NET Framework unterstützt. Da .NET Framework Sprachenunabhängigkeit und Sprachinteroperabilität bietet, ist die Interaktion mit allen anderen .NET Framework-Apps und -Komponenten möglich, unabhängig davon, in welcher Sprache sie entwickelt wurden.

Gehen Sie beim Entwickeln von .NET Framework-Apps oder -Komponenten folgendermaßen vor:

1. Wenn sie nicht bereits auf dem Betriebssystem vorinstalliert ist, installieren Sie die für die App erforderliche Version von .NET Framework. Die neueste Produktionsversion ist .NET Framework 4.8. Diese Version ist beim Windows 10-Update vom Mai 2019 vorinstalliert und steht für ältere Versionen des Windows-Betriebssystems zum Download zur Verfügung. Informationen zu den Systemanforderungen von .NET Framework finden Sie unter [Systemanforderungen](system-requirements.md). Informationen zum Installieren anderer Versionen von .NET Framework finden Sie im [Installationshandbuch](../install/guide-for-developers.md). Zusätzliche .NET Framework-Pakete werden Out-of-Band freigegeben, das bedeutet, dass sie auf fortlaufender Basis außerhalb aller regulären oder geplanten Freigabezyklen freigegeben werden. Weitere Informationen zu diesen Paketen finden Sie unter [.NET Framework und Out-of-Band-Releases](the-net-framework-and-out-of-band-releases.md).

2. Wählen Sie die von der .NET Framework-Version unterstützten Sprachen aus, die Sie zur Entwicklung von Apps verwenden möchten. Es stehen mehrere Sprachen zur Verfügung, darunter [Visual Basic](../../visual-basic/index.yml), [C#](../../csharp/index.yml), [F#](../../fsharp/index.yml) und [C++/CLI](/cpp/dotnet/dotnet-programming-with-cpp-cli-visual-cpp) von Microsoft. (Programmiersprachen, die Ihnen ermöglichen, Apps für .NET Framework zu entwickeln, erfüllen die [CLI-Spezifikation](https://visualstudio.microsoft.com/license-terms/ecma-c-common-language-infrastructure-standards/).)

3. Wählen Sie die Entwicklungsumgebung aus, die Sie zum Erstellen der Apps verwenden möchten und die von der von Ihnen gewählten Programmiersprachen unterstützt werden, und installieren Sie sie. Die integrierte Microsoft-Entwicklungsumgebung (IDE) für .NET Framework-Apps ist [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link). Es stehen verschiedene Editionen zur Verfügung.

Weitere Informationen zum Entwickeln von Apps, die auf .NET Framework ausgerichtet sind, finden Sie im [Entwicklungshandbuch](../development-guide.md).

## <a name="related-articles"></a>Verwandte Artikel

| Titel | Beschreibung |
| ----- |------------ |
| [Übersicht](overview.md) | Enthält ausführliche Informationen für Entwickler, die Apps für .NET Framework erstellen. |
| [Installationshandbuch](../install/index.md) | Stellt Informationen zum Installieren von .NET Framework bereit. |  
| [.NET Framework und Out-of-Band-Releases](the-net-framework-and-out-of-band-releases.md) | Beschreibt die Out-of-Band-Releases von .NET Framework und ihre Verwendung in der App. |
| [Systemanforderungen](system-requirements.md) | Führt die Hardware- und Softwareanforderungen für das Ausführen von .NET Framework auf. |
| [.NET Core und Open-Source](net-core-and-open-source.md) | Beschreibt .NET Core in Bezug auf .NET Framework, und wie Sie auf die Open-Source-Projekte von .NET Core zugreifen können. |
| [.NET Core-Dokumentation](../../core/index.yml) | Stellt die konzeptionelle und API-Referenzdokumentation für .NET Core bereit. |
| [.NET-Standard](../../standard/net-standard.md) | Erläutert .NET Standard, eine Spezifikation mit Versionsangabe, die von einzelnen .NET-Implementierungen unterstützt wird, um sicherzustellen, dass die gleichen APIs auf mehreren Plattformen verfügbar sind.

## <a name="see-also"></a>Siehe auch

- [NET Framework-Dokumentation](../index.yml)
- [Neuigkeiten](../whats-new/index.md)
- [.NET API-Browser](../../../api/index.md)
- [Entwicklungshandbuch für .NET Framework](../development-guide.md)
