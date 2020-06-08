---
title: 'Übersicht über Common Language Runtime (CLR): .NET Framework'
ms.date: 04/02/2019
ms.technology: dotnet-standard
helpviewer_keywords:
- compiling source code, runtime functionality
- code, execution
- managed data
- runtime
- common language runtime
- metadata, runtime functionality
- .NET Framework, common language runtime
- language compilers
- managed code
- source code execution
- code, runtime functionality
ms.assetid: 059a624e-f7db-4134-ba9f-08b676050482
ms.custom: updateeachrelease
ms.openlocfilehash: 74421f79c18f32e121d51c47f3eb32f3c2ed71fd
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289245"
---
# <a name="common-language-runtime-clr-overview"></a>Übersicht: Common Language Runtime (CLR)

.NET Framework stellt eine als Common Language Runtime bezeichnete Laufzeitumgebung bereit, die Code ausführt und Dienste für die Erleichterung des Entwicklungsprozesses bereitstellt.

Compiler und Tools machen die Funktionen der Common Language Runtime verfügbar und ermöglichen das Schreiben von Code, mit dem die Vorteile dieser verwalteten Ausführungsumgebung genutzt werden können. Mit einem Sprachcompiler für die Common Language Runtime entwickelter Code wird "verwalteter Code" genannt. Dieser nutzt Features wie sprachübergreifende Integration, sprachübergreifende Ausnahmebehandlung, erhöhte Sicherheit, Unterstützung bei der Versionserstellung und Bereitstellung, ein vereinfachtes Modell für die Interaktion von Komponenten sowie Debug- und Profilerstellungsdienste.

> [!NOTE]
> Compiler und Tools sind in der Lage, eine von der Common Language Runtime nutzbare Ausgabe zu erzeugen, da sowohl das Typsystem, das Format der Metadaten als auch die Laufzeitumgebung (das virtuelle Ausführungssystem) von einem öffentlichen Standard definiert werden, dem ECMA-Standard für die Common Language Infrastructure. Weitere Informationen finden Sie unter [ECMA C# und Common Language Infrastructure Standards](https://visualstudio.microsoft.com/license-terms/ecma-c-common-language-infrastructure-standards/).

Damit die Common Language Runtime Dienste für verwalteten Code bereitstellen kann, müssen Sprachcompiler Metadaten ausgeben, mit denen die Typen, Member und Verweise im Code beschrieben werden. Metadata werden gemeinsam mit dem Code gespeichert. Jede PE (Portable Executable)-Datei der Common Language Runtime, die geladen werden kann, enthält Metadaten. Die Laufzeit verwendet Metadaten zum Suchen und Laden von Klassen, Anordnen von Instanzen im Speicher, Auflösen von Methodenaufrufen, Generieren von systemeigenem Code, Erzwingen von Sicherheit und zum Festlegen von Begrenzungen im Laufzeitkontext.

Die Laufzeit behandelt automatisch das Objektlayout und verwaltet Verweise auf Objekte. Diese werden nach Verwendung freigegeben. Objekte, deren Lebensdauer auf diese Weise verwaltet wird, werden als verwaltete Daten bezeichnet. Durch die Garbage Collection werden Speicherverluste sowie einige weitere verbreitete Programmierfehler vermieden. Wenn verwalteter Code verwendet wird, können in einer .NET Framework-Anwendung verwaltete Daten, nicht verwaltete Daten oder beides gleichzeitig verwendet werden. Da Sprachcompiler ihre eigenen Typen, z. B. primitive Typen, bereitstellen, wissen Sie möglicherweise nicht (oder müssen nicht wissen), ob die Daten verwaltet werden.

Die Common Language Runtime erleichtert das Entwerfen von Komponenten und Anwendungen, deren Objekte sprachübergreifend interagieren. In unterschiedlichen Sprachen geschriebene Objekte können miteinander kommunizieren. Ihr Verhalten kann in hohem Maße integriert werden. Sie können z. B. eine Klasse definieren und dann in einer anderen Sprache eine Klasse von der ursprünglichen Klasse ableiten oder eine Methode für diese aufrufen. Sie können außerdem eine Instanz einer Klasse an die in einer anderen Sprache geschriebene Methode einer Klasse übergeben. Diese sprachübergreifende Integration wird durch die Verwendung eines von der Common Language Runtime definierten allgemeinen Typsystems durch Sprachcompiler und Tools für die Common Language Runtime ermöglicht. Hierbei werden die Regeln der Common Language Runtime für die Definition neuer Typen, das Erstellen, Verwenden und Beibehalten von Typen sowie für die Typenbindung befolgt.

Sämtliche verwalteten Komponenten enthalten als Teil der jeweiligen Metadaten Informationen über die Komponenten und Ressourcen, für die sie erstellt wurden. Mit diesen Informationen stellt die Common Language Runtime sicher, dass die Komponente oder Anwendung über die angegebenen Versionen aller erforderlichen Elemente verfügt. Dadurch kommt es seltener zu einer Unterbrechung der Ausführung des Codes aufgrund einer Abhängigkeit, deren Voraussetzungen nicht erfüllt sind. Registrierungsinformationen und Zustandsdaten werden nicht mehr in der Registrierung gespeichert, in der sie möglicherweise schwierig zu erstellen und zu verwalten sind. Stattdessen werden Informationen über die definierten Typen sowie deren Abhängigkeiten gemeinsam mit dem Code als Metadaten gespeichert, wodurch die Replikation und das Entfernen von Komponenten wesentlich vereinfacht werden.

Die Funktionen der Laufzeit werden durch Sprachcompiler und Tools auf eine Weise verfügbar gemacht, dass sie von Entwicklern einfach und intuitiv verwendet werden können. Dies hat zur Folge, dass einige Features der Laufzeit möglicherweise in unterschiedlichen Umgebungen unterschiedlich wahrgenommen werden. Die Wahrnehmung der Laufzeit hängt von den verwendeten Sprachcompilern und Tools ab. Visual Basic-Entwickler werden z. B. bemerken, dass die Sprache Visual Basic mit der Common Language Runtime über mehr zusätzliche objektorientierte Features als ohne sie verfügt. In Folgenden sind einige Vorteile der Common Language Runtime aufgeführt:

- Leistungsverbesserungen.

- Die problemlose Verwendung in anderen Sprachen entwickelter Komponenten.

- Erweiterbare Typen, die von einer Klassenbibliothek bereitgestellt werden.

- Neue Sprachfunktionen wie Vererbung, Schnittstellen und Überladen für objektorientiertes Programmieren.

- Unterstützung für explizites Freethreading zum Erstellen skalierbarer Multithreadanwendungen.

- Unterstützung für strukturierte Ausnahmebehandlung.

- Unterstützung für benutzerdefinierte Attribute.

- Garbage Collection.

- Verwendung von Delegaten anstelle von Funktionszeigern zur Verbesserung der Typsicherheit. Weitere Informationen zu Delegaten finden Sie unter [Allgemeines Typsystem](base-types/common-type-system.md).

## <a name="clr-versions"></a>CLR-Versionen

Die Versionsnummer von .NET Framework entspricht nicht unbedingt der Versionsnummer der enthaltenen CLR. Eine Liste der Versionen von .NET Framework und der dazugehörigen CLR-Versionen finden Sie unter [.NET Framework-Versionen und -Abhängigkeiten](../framework/migration-guide/versions-and-dependencies.md). .NET Core-Releases verfügen über eine einzelne Produktversion, d. h. es gibt keine getrennte CLR-Version. Eine Liste von .NET Core-Versionen finden Sie unter [Herunterladen von .NET Core](https://dotnet.microsoft.com/download/dotnet-core).

## <a name="related-topics"></a>Verwandte Themen

|Titel|Beschreibung|
|-----------|-----------------|
|[Der verwaltete Ausführungsprozess](managed-execution-process.md)|Enthält eine Beschreibung der Schritte, die erforderlich sind, um die Vorteile der Common Language Runtime nutzen zu können.|
|[Automatische Speicherverwaltung](automatic-memory-management.md)|Erläutert, wie Sie den Garbage Collector zum Belegen und Freigeben von Arbeitsspeicher verwenden können.|
|[Übersicht über .NET Framework](../framework/get-started/overview.md)|Beschreibt die wichtigsten Konzepte von .NET Framework, z. B. das allgemeine Typsystem, sprachübergreifende Interoperabilität, verwaltete Ausführung, Anwendungsdomänen und Assemblys.|
|[Allgemeines Typsystem](./base-types/common-type-system.md)|Enthält eine Beschreibung der Deklaration, Verwendung und Verwaltung von Typen in der Laufzeit für die Unterstützung einer sprachübergreifenden Integration.|
