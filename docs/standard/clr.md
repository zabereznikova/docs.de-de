---
title: 'Übersicht: Common Language Runtime (CLR) – .NET'
titleSuffix: ''
description: Führen Sie die ersten Schritte mit der Common Language Runtime (CLR), der .NET-Laufzeitumgebung, durch. Die CLR führt Code aus und stellt Dienste bereit, um den Entwicklungsprozess zu vereinfachen.
ms.date: 10/22/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- compiling source code, runtime functionality
- code, execution
- managed data
- runtime
- common language runtime
- metadata, runtime functionality
- .NET, common language runtime
- language compilers
- managed code
- source code execution
- code, runtime functionality
ms.assetid: 059a624e-f7db-4134-ba9f-08b676050482
ms.custom: updateeachrelease
ms.openlocfilehash: 39543a511e8f405d9205df2697bcf4fd1194bd7a
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92687505"
---
# <a name="common-language-runtime-clr-overview"></a>Übersicht: Common Language Runtime (CLR)

.NET stellt eine als Common Language Runtime bezeichnete Laufzeitumgebung bereit, die Code ausführt und Dienste zum Vereinfachen des Entwicklungsprozesses bereitstellt.

Compiler und Tools machen die Funktionen der Common Language Runtime verfügbar und ermöglichen das Schreiben von Code, mit dem die Vorteile dieser verwalteten Ausführungsumgebung genutzt werden können. Code, den Sie mit einem Sprachcompiler für die Runtime entwickeln, wird als verwalteter Code bezeichnet. Der verwaltete Code profitiert von Features wie der sprachübergreifenden Integration, der sprachübergreifenden Ausnahmebehandlung, erhöhter Sicherheit, der Unterstützung bei der Versionserstellung und der Bereitstellung, einem vereinfachten Modell für die Interaktion von Komponenten sowie Debug- und Profilerstellungsdiensten.

> [!NOTE]
> Compiler und Tools sind in der Lage, eine von der Common Language Runtime nutzbare Ausgabe zu erzeugen, da sowohl das Typsystem, das Format der Metadaten als auch die Laufzeitumgebung (das virtuelle Ausführungssystem) von einem öffentlichen Standard definiert werden, dem Standard für die Common Language Infrastructure von Ecma International. Weitere Informationen finden Sie unter [ECMA C# und Common Language Infrastructure Standards](https://visualstudio.microsoft.com/license-terms/ecma-c-common-language-infrastructure-standards/).

Damit die Common Language Runtime Dienste für verwalteten Code bereitstellen kann, müssen Sprachcompiler Metadaten ausgeben, mit denen die Typen, Member und Verweise im Code beschrieben werden. Metadata werden gemeinsam mit dem Code gespeichert. Jede PE (Portable Executable)-Datei der Common Language Runtime, die geladen werden kann, enthält Metadaten. Die Laufzeit verwendet Metadaten zum Suchen und Laden von Klassen, Anordnen von Instanzen im Speicher, Auflösen von Methodenaufrufen, Generieren von systemeigenem Code, Erzwingen von Sicherheit und zum Festlegen von Begrenzungen im Laufzeitkontext.

Die Laufzeit behandelt automatisch das Objektlayout und verwaltet Verweise auf Objekte. Diese werden nach Verwendung freigegeben. Objekte, deren Lebensdauer auf diese Weise verwaltet wird, werden als verwaltete Daten bezeichnet. Durch die Garbage Collection werden Speicherverluste sowie einige weitere verbreitete Programmierfehler vermieden. Wenn verwalteter Code verwendet wird, können in einer .NET-Anwendung verwaltete Daten, nicht verwaltete Daten oder beides gleichzeitig verwendet werden. Da Sprachcompiler ihre eigenen Typen, z. B. primitive Typen, bereitstellen, wissen Sie möglicherweise nicht (oder müssen nicht wissen), ob die Daten verwaltet werden.

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

Releases von .NET Core und .NET 5 und höher verfügen über nur eine Produktversion, d. h. es gibt keine separate CLR-Version. Eine Liste von .NET Core-Versionen finden Sie unter [Herunterladen von .NET Core](https://dotnet.microsoft.com/download/dotnet-core).

Die Versionsnummer von .NET Framework entspricht jedoch nicht unbedingt der Versionsnummer der enthaltenen CLR. Eine Liste der Versionen von .NET Framework und der dazugehörigen CLR-Versionen finden Sie unter [.NET Framework-Versionen und -Abhängigkeiten](../framework/migration-guide/versions-and-dependencies.md).

## <a name="related-topics"></a>Verwandte Themen

|Titel|Beschreibung|
|-----------|-----------------|
|[Der verwaltete Ausführungsprozess](managed-execution-process.md)|Enthält eine Beschreibung der Schritte, die erforderlich sind, um die Vorteile der Common Language Runtime nutzen zu können.|
|[Automatische Speicherverwaltung](automatic-memory-management.md)|Erläutert, wie Sie den Garbage Collector zum Belegen und Freigeben von Arbeitsspeicher verwenden können.|
|[Übersicht über .NET Framework](../framework/get-started/overview.md)|Beschreibt die wichtigsten Konzepte von .NET Framework, z. B. das allgemeine Typsystem, die sprachübergreifende Interoperabilität, die verwaltete Ausführung, Anwendungsdomänen und Assemblys|
|[Allgemeines Typsystem](./base-types/common-type-system.md)|Enthält eine Beschreibung der Deklaration, Verwendung und Verwaltung von Typen in der Laufzeit für die Unterstützung einer sprachübergreifenden Integration.|
