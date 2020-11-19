---
title: Parallele Programmierung in .NET
description: Erfahren Sie mehr über die parallele Programmierung in .NET. Verwenden Sie eine .NET-Runtime, Klassenbibliothekstypen und Diagnosetools, um die .NET-Entwicklung zu vereinfachen.
ms.date: 09/12/2018
helpviewer_keywords:
- parallel programming
ms.assetid: 4d83c690-ad2d-489e-a2e0-b85b898a672d
ms.openlocfilehash: 4d141a6a8fd7b7bf1aad943f8b911c8b39267223
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94820357"
---
# <a name="parallel-programming-in-net"></a>Parallele Programmierung in .NET

Viele Personalcomputer und Arbeitsstationen verfügen über mehrere CPU-Kerne, die die gleichzeitige Ausführung mehrerer Threads ermöglichen. Um die Hardware nutzen zu können, kann der Code parallelisiert werden, um die Arbeit über mehrere Prozessoren zu verteilen.

Früher erforderte die Parallelisierung Änderungen von Threads und Sperren auf niedriger Ebene. Visual Studio und .NET verbessern die Unterstützung für die parallele Programmierung, indem sie eine Laufzeit, Klassenbibliothekstypen und Diagnosetools bereitstellen. Diese Features, die in .NET Framework 4 eingeführt wurden, vereinfachen die parallele Entwicklung. Sie können effizienten, differenzierten und skalierbaren parallelen Code in einer natürlichen Sprache schreiben, ohne direkt mit Threads oder dem Threadpool arbeiten zu müssen.

Die folgende Abbildung stellt in .NET eine allgemeine Übersicht der parallelen Programmierarchitektur bereit.

![.NET-Architektur für die parallele Programmierung](./media/tpl-architecture.png)

## <a name="related-topics"></a>Verwandte Themen

|Technologie|Beschreibung|
|----------------|-----------------|
|[Task Parallel Library (TPL)](task-parallel-library-tpl.md)|Stellt eine Dokumentation für die <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType>-Klasse, die parallele Versionen einer `For`-Schleife und einer `ForEach`-Schleife einschließt, sowie für die <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>-Klasse bereit. Dies ist die bevorzugte Methode, um asynchrone Vorgänge auszudrücken.|
|[Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](introduction-to-plinq.md)|Eine parallele Implementierung von LINQ to Objects, die die Leistung in vielen Szenarien deutlich verbessert.|
|[Datenstrukturen für die parallele Programmierung](data-structures-for-parallel-programming.md)|Stellt Links zu Dokumentationen über threadsichere Auflistungsklassen, einfache Synchronisierungstypen und Typen für verzögerte Initialisierung bereit.|
|[Diagnosetools für die parallele Ausführung](parallel-diagnostic-tools.md)|Stellt Links zu Dokumentation für Visual Studio-Debuggerfenster für Aufgaben und parallele Stapel sowie für [Concurrency Visualizer](/visualstudio/profiling/concurrency-visualizer) bereit.|
|[Benutzerdefinierte Partitionierer für PLINQ und TPL](custom-partitioners-for-plinq-and-tpl.md)|Beschreibt, wie Partitionierer funktionieren und wie die Standardpartitionierer konfiguriert bzw. wie ein neuer Partitionierer erstellt wird.|
|[Taskplaner](xref:System.Threading.Tasks.TaskScheduler)|Beschreibt, wie Planer funktionieren und wie die Standardplaner konfiguriert werden.|
|[Lambdaausdrücke in PLINQ und TPL](lambda-expressions-in-plinq-and-tpl.md)|Bietet einen kurzen Überblick über Lambaausdrücke in C# und Visual Basic und zeigt, wie sie in PLINQ und der Task Parallel Library verwendet werden.|
|[Weitere Informationen](for-further-reading-parallel-programming.md)|Stellt Links zu zusätzlichen Informationen und Beispielressourcen für die parallele Programmierung in .NET Framework bereit.|

## <a name="see-also"></a>Siehe auch

- [Async (Übersicht)](../async.md)
- [Verwaltetes Threading](../threading/index.md)
