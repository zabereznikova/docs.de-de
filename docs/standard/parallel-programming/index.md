---
title: Parallele Programmierung in .NET Framework | Microsoft-Dokumentation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parallel programming
ms.assetid: 4d83c690-ad2d-489e-a2e0-b85b898a672d
caps.latest.revision: 19
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: c50b3e328998b65ec47efe6d7457b36116813c77
ms.openlocfilehash: 6a163776f358691c0f61c90dce98c15bebe4052a
ms.lasthandoff: 04/08/2017

---
# <a name="parallel-programming-in-the-net-framework"></a>Parallele Programmierung in .NET Framework
Viele Personalcomputer und Arbeitsstationen verfügen über zwei oder vier Kerne (d. h. CPUs), die die gleichzeitige Ausführung mehrerer Threads ermöglichen. Schon in naher Zukunft werden Computer vermutlich über deutlich mehr Kerne verfügen. Um sowohl aktuelle als auch künftige Hardware nutzen zu können, kann der Code parallelisiert werden, um die Arbeit über mehrere Prozessoren zu verteilen. Früher erforderte die Parallelisierung Änderungen von Threads und Sperren auf niedriger Ebene. [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)] und [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] verbessern die Unterstützung für parallele Programmierung, indem sie eine neue Laufzeit, neue Klassenbibliothekstypen und neue Diagnosetools bereitstellen. Durch diese Funktionen wird die parallele Entwicklung vereinfacht, sodass sie effizienten, differenzierten und skalierbaren parallelen Code in einer natürlichen Sprache schreiben können, ohne direkt mit Threads oder dem Threadpool arbeiten zu müssen. Die folgende Abbildung stellt in [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] eine allgemeine Übersicht der parallelen Programmierarchitektur bereit.  
  
 ![.NET-Architektur für die parallele Programmierung](../../../docs/standard/parallel-programming/media/tpl-architecture.png "TPL_Architecture")  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|Technologie|Beschreibung|  
|----------------|-----------------|  
|[Task Parallel Library (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)|Stellt eine Dokumentation für die <xref:System.Threading.Tasks.Parallel?displayProperty=fullName>-Klasse, die parallele Versionen einer `For`-Schleife und einer `ForEach`-Schleife einschließt, sowie für die <xref:System.Threading.Tasks.Task?displayProperty=fullName>-Klasse bereit. Dies ist die bevorzugte Methode, um asynchrone Vorgänge auszudrücken.|  
|[Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)|Eine parallele Implementierung von LINQ to Objects, die die Leistung in vielen Szenarien deutlich verbessert.|  
|[Datenstrukturen für die parallele Programmierung](../../../docs/standard/parallel-programming/data-structures-for-parallel-programming.md)|Stellt Links zu Dokumentationen über threadsichere Auflistungsklassen, einfache Synchronisierungstypen und Typen für verzögerte Initialisierung bereit.|  
|[Diagnosetools für die parallele Ausführung](../../../docs/standard/parallel-programming/parallel-diagnostic-tools.md)|Stellt Links zu Dokumentationen über Visual Studio-Debuggerfenster für Aufgaben und parallele Stapel und die [Nebenläufigkeitsschnellansicht](http://msdn.microsoft.com/library/ae5879a0-1e1a-455a-ba72-148e57f59289) bereit, die aus einer Gruppe von Ansichten im [!INCLUDE[vsprvsts](../../../includes/vsprvsts-md.md)]-Profiler besteht, mit dem paralleler Code debuggt und dessen Leistung optimiert werden kann.|  
|[Benutzerdefinierte Partitionierer für PLINQ und TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)|Beschreibt, wie Partitionierer funktionieren und wie die Standardpartitionierer konfiguriert bzw. wie ein neuer Partitionierer erstellt wird.|  
|[Taskplaner](http://msdn.microsoft.com/library/638f8ea5-21db-47a2-a934-86e1e961bf65)|Beschreibt, wie Planer funktionieren und wie die Standardplaner konfiguriert werden.|  
|[Lambdaausdrücke in PLINQ und TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)|Bietet einen kurzen Überblick über Lambaausdrücke in C# und Visual Basic und zeigt, wie sie in PLINQ und der Task Parallel Library verwendet werden.|  
|[Weitere Informationen](../../../docs/standard/parallel-programming/for-further-reading-parallel-programming.md)|Stellt Links zu zusätzlichen Dokumentationen und Beispielressourcen für parallele Programmierung in .NET Framework bereit.|  
  
## <a name="see-also"></a>Siehe auch  
 [Muster für die parallele Programmierung: Begreifen und Anwenden von parallelen Mustern mit .NET Framework 4](http://go.microsoft.com/fwlink/?LinkID=185142)   
 [Beispiele für die parallele Programmierung mit .NET Framework](http://code.msdn.microsoft.com/Samples-for-Parallel-b4b76364)
