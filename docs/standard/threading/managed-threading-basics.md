---
title: Grundlagen des verwalteten Threadings
description: In diesem Artikel finden Sie Links zu anderen Artikeln über verwaltetes Threading, in denen unter anderem Themen wie Ausnahmen, das Synchronisieren von Daten, Vordergrund- und Hintergrundthreads und lokaler Speicher behandelt werden.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- multiple threads
- threading [.NET], multiple threads
- threading [.NET], about threading
- managed threading
ms.assetid: b2944911-0e8f-427d-a8bb-077550618935
ms.openlocfilehash: ca3073cca9887265b4bacb4f8dfeb01203f82621
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2020
ms.locfileid: "93189133"
---
# <a name="managed-threading-basics"></a>Grundlagen des verwalteten Threadings

Die ersten fünf Artikel in diesem Abschnitt sollen Ihnen helfen, zu bestimmen, wann Sie verwaltetes Threading verwenden sollten, und einige grundlegende Features erläutern. Informationen zu den Klassen, die zusätzliche Funktionen bereitstellen, finden Sie unter [Threadingobjekte und -funktionen](threading-objects-and-features.md) und [Übersicht über Synchronisierungsprimitiven](overview-of-synchronization-primitives.md).  
  
 Die restlichen Artikel in diesem Abschnitt behandeln erweiterte Themen einschließlich der Interaktion verwalteten Threadings mit dem Windows-Betriebssystem.  
  
> [!NOTE]
> Ab .NET Framework 4 stellen die Task Parallel Library und PLINQ APIs für Task- und Datenparallelität in Multithreadprogrammen bereit. Weitere Informationen finden Sie unter [Parallel Programming in the .NET Framework (Parallele Programmierung in .NET Framework)](../parallel-programming/index.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt

 [Threads and Threading (Threads und Threading)](threads-and-threading.md)  
 Erläutert die Vor- und Nachteile von mehreren Threads und beschreibt die Szenarien, in denen Sie Threads erstellen oder Threads aus Threadpools verwenden sollten.  
  
 [Ausnahmen in verwalteten Threads](exceptions-in-managed-threads.md)  
 In diesem Artikel wird das Verhalten der Ausnahmefehler in Threads für verschiedene Versionen von .NET beschrieben, insbesondere die Situationen, in denen sie zum Beenden der Anwendung führen.  
  
 [Datensynchronisierung für Multithreading](synchronizing-data-for-multithreading.md)  
 Beschreibt Strategien zum Synchronisieren von Daten in Klassen, die mit mehreren Threads verwendet werden.  
  
 [Vordergrund- und Hintergrundthreads](foreground-and-background-threads.md)  
 Erläutert die Unterschiede zwischen Vordergrund-und Hintergrundthreads.  
  
 [Verwaltetes und nicht verwaltetes Threading in Windows](managed-and-unmanaged-threading-in-windows.md)  
 Beschreibt die Beziehung zwischen verwaltetem und nicht verwaltetem Threading, listet verwaltete Entsprechungen für Windows-Threading-APIs auf und erläutert die Interaktion von COM-Apartments und verwalteten Threads.  
  
 [Threadlokaler Speicher: Threadbezogene statische Felder und Datenslots](thread-local-storage-thread-relative-static-fields-and-data-slots.md)  
 Beschreibt threadbezogene Speichermechanismen.  
  
## <a name="reference"></a>Referenz

 <xref:System.Threading.Thread>  
 Stellt die Referenzdokumentation für die **Thread** -Klasse bereit, die einen verwalteten Thread repräsentiert, und zwar unabhängig davon, ob er von nicht verwaltetem Code stammt oder in einer verwalteten Anwendung erstellt wurde.  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 Bietet eine sichere Möglichkeit zum Implementieren von Multithreading in Verbindung mit Benutzeroberflächenobjekten.  
  
## <a name="related-sections"></a>Verwandte Abschnitte

 [Übersicht über Synchronisierungsprimitiven](overview-of-synchronization-primitives.md)  
 Beschreibt die verwalteten Klassen, die zum Synchronisieren mehrerer Threads verwendet werden.  
  
 [Empfohlene Vorgehensweise für das verwaltete Threading](managed-threading-best-practices.md)  
 Beschreibt allgemeine Probleme mit Multithreading und Strategien zur Vermeidung von Problemen.  
  
 [Parallele Programmierung](../parallel-programming/index.md)  
 In diesem Artikel werden die Task Parallel Library und PLINQ beschrieben, die das Erstellen von asynchronen und Multithread-.NET-Anwendungen erheblich vereinfachen.
