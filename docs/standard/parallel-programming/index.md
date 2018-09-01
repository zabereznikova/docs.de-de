---
title: Parallele Programmierung in .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- parallel programming
ms.assetid: 4d83c690-ad2d-489e-a2e0-b85b898a672d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 372ffd7e17f60b8045cd5f89d52456c5f9655de1
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43408161"
---
# <a name="parallel-programming-in-net"></a>Parallele Programmierung in .NET

Viele Personalcomputer und Arbeitsstationen verfügen über mehrere Kerne (d. h. CPUs), die die gleichzeitige Ausführung mehrerer Threads ermöglichen. Schon in naher Zukunft werden Computer vermutlich über deutlich mehr Kerne verfügen. Um sowohl aktuelle als auch künftige Hardware nutzen zu können, kann der Code parallelisiert werden, um die Arbeit über mehrere Prozessoren zu verteilen. Früher erforderte die Parallelisierung Änderungen von Threads und Sperren auf niedriger Ebene. Visual Studio 2010 und .NET Framework 4 verbessern die Unterstützung für die parallele Programmierung, indem sie eine neue Laufzeit, neue Klassenbibliothekstypen und neue Diagnosetools bereitstellen. Durch diese Funktionen wird die parallele Entwicklung vereinfacht, sodass sie effizienten, differenzierten und skalierbaren parallelen Code in einer natürlichen Sprache schreiben können, ohne direkt mit Threads oder dem Threadpool arbeiten zu müssen. Die folgende Abbildung zeigt eine allgemeine Übersicht der parallelen Programmierarchitektur in .NET Framework 4.

 ![.NET-Architektur für die parallele Programmierung](./media/tpl-architecture.png "TPL_Architecture")

## <a name="related-topics"></a>Verwandte Themen

|Technologie|Beschreibung |
|----------------|-----------------|
|[Task Parallel Library (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)|Stellt eine Dokumentation für die <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType>-Klasse, die parallele Versionen einer `For`-Schleife und einer `ForEach`-Schleife einschließt, sowie für die <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>-Klasse bereit. Dies ist die bevorzugte Methode, um asynchrone Vorgänge auszudrücken.|
|[Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)|Eine parallele Implementierung von LINQ to Objects, die die Leistung in vielen Szenarien deutlich verbessert.|
|[Datenstrukturen für die parallele Programmierung](../../../docs/standard/parallel-programming/data-structures-for-parallel-programming.md)|Stellt Links zu Dokumentationen über threadsichere Auflistungsklassen, einfache Synchronisierungstypen und Typen für verzögerte Initialisierung bereit.|
|[Diagnosetools für die parallele Ausführung](../../../docs/standard/parallel-programming/parallel-diagnostic-tools.md)|Stellt Links zu Dokumentation für Visual Studio-Debuggerfenster für Aufgaben und parallele Stapel sowie für [Concurrency Visualizer](/visualstudio/profiling/concurrency-visualizer) bereit.|
|[Benutzerdefinierte Partitionierer für PLINQ und TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)|Beschreibt, wie Partitionierer funktionieren und wie die Standardpartitionierer konfiguriert bzw. wie ein neuer Partitionierer erstellt wird.|
|[Taskplaner](https://msdn.microsoft.com/library/638f8ea5-21db-47a2-a934-86e1e961bf65)|Beschreibt, wie Planer funktionieren und wie die Standardplaner konfiguriert werden.|
|[Lambdaausdrücke in PLINQ und TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)|Bietet einen kurzen Überblick über Lambaausdrücke in C# und Visual Basic und zeigt, wie sie in PLINQ und der Task Parallel Library verwendet werden.|
|[Weitere Informationen](../../../docs/standard/parallel-programming/for-further-reading-parallel-programming.md)|Stellt Links zu zusätzlichen Informationen und Beispielressourcen für die parallele Programmierung in .NET Framework bereit.|

## <a name="see-also"></a>Siehe auch

- [Async (Übersicht)](../async.md)
- [Verwaltetes Threading](../threading/index.md)
