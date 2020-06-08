---
title: Grundlagen des verwalteten Threadings
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- multiple threads
- threading [.NET Framework], multiple threads
- threading [.NET Framework], about threading
- managed threading
ms.assetid: b2944911-0e8f-427d-a8bb-077550618935
ms.openlocfilehash: 4d2a96619fd1c48c79b5590efdb52c307d29710c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291005"
---
# <a name="managed-threading-basics"></a>Grundlagen des verwalteten Threadings

Die ersten fünf Themen in diesem Abschnitt sollen Ihnen helfen, zu bestimmen, wann Sie verwaltetes Threading verwenden sollten, und einige grundlegende Funktionen erläutern. Informationen zu den Klassen, die zusätzliche Funktionen bereitstellen, finden Sie unter [Threadingobjekte und -funktionen](threading-objects-and-features.md) und [Übersicht über Synchronisierungsprimitiven](overview-of-synchronization-primitives.md).  
  
 Bei den übrigen Themen in diesem Abschnitt handelt es sich um erweiterte Themen einschließlich der Interaktion verwalteten Threadings mit dem Windows-Betriebssystem.  
  
> [!NOTE]
> In .NET Framework 4 stellen die Task Parallel Library und PLINQ APIs für Aufgaben- und Datenparallelität in Multithreadprogrammen bereit. Weitere Informationen finden Sie unter [Parallel Programming in the .NET Framework (Parallele Programmierung in .NET Framework)](../parallel-programming/index.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt

 [Threads and Threading (Threads und Threading)](threads-and-threading.md)  
 Erläutert die Vor- und Nachteile von mehreren Threads und beschreibt die Szenarien, in denen Sie Threads erstellen oder Threads aus Threadpools verwenden sollten.  
  
 [Ausnahmen in verwalteten Threads](exceptions-in-managed-threads.md)  
 Beschreibt das Verhalten der nicht behandelten Ausnahmen in Threads für verschiedene Versionen von .NET Framework, insbesondere die Situationen, in denen sie zum Beenden der Anwendung führen.  
  
 [Datensynchronisierung für Multithreading](synchronizing-data-for-multithreading.md)  
 Beschreibt Strategien zum Synchronisieren von Daten in Klassen, die mit mehreren Threads verwendet werden.  
  
 [Vordergrund- und Hintergrundthreads](foreground-and-background-threads.md)  
 Erläutert die Unterschiede zwischen Vordergrund-und Hintergrundthreads.  
  
 [Verwaltetes und nicht verwaltetes Threading in Windows](managed-and-unmanaged-threading-in-windows.md)  
 Beschreibt die Beziehung zwischen verwaltetem und nicht verwaltetem Threading, listet verwaltete Entsprechungen für Windows-Threading-APIs auf und erläutert die Interaktion von COM-Apartments und verwalteten Threads.  
  
 [Threadlokaler Speicher: Threadbezogene statische Felder und Datenslots](thread-local-storage-thread-relative-static-fields-and-data-slots.md)  
 Beschreibt threadbezogene Speichermechanismen.  
  
## <a name="reference"></a>Verweis

 <xref:System.Threading.Thread>  
 Stellt die Referenzdokumentation für die **Thread**-Klasse bereit, die einen verwalteten Thread repräsentiert, und zwar unabhängig davon, ob er von nicht verwaltetem Code stammt oder in einer verwalteten Anwendung erstellt wurde.  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 Bietet eine sichere Möglichkeit zum Implementieren von Multithreading in Verbindung mit Benutzeroberflächenobjekten.  
  
## <a name="related-sections"></a>Verwandte Abschnitte

 [Übersicht über Synchronisierungsprimitiven](overview-of-synchronization-primitives.md)  
 Beschreibt die verwalteten Klassen, die zum Synchronisieren mehrerer Threads verwendet werden.  
  
 [Empfohlene Vorgehensweise für das verwaltete Threading](managed-threading-best-practices.md)  
 Beschreibt allgemeine Probleme mit Multithreading und Strategien zur Vermeidung von Problemen.  
  
 [Parallele Programmierung](../parallel-programming/index.md)  
 Beschreibt Task Parallel Library und PLINQ, die das Erstellen von asynchronen und Multithreaded-.NET Framework-Anwendungen erheblich vereinfachen.
