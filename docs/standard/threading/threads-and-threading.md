---
title: Threads und Threading
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- multiple threads
- threading [.NET Framework]
- threading [.NET Framework], multiple threads
ms.assetid: 5baac3aa-e603-4fa6-9f89-0f2c1084e6b1
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 114fb704a622d92ab8e92fa866fa0fc9bebf4e58
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="threads-and-threading"></a>Threads und Threading
Betriebssysteme verwenden Prozesse, um die verschiedenen ausgeführten Anwendungen voneinander zu trennen. Threads sind die Grundeinheit, der ein Betriebssystem Prozessorzeit zuweist, und mehrere Threads können gleichzeitig Code innerhalb dieses Prozesses ausführen. Jeder Thread unterhält Ausnahmehandler, eine Planungspriorität und eine Reihe von Strukturen, mit denen das System den Threadkontext speichert, bis er eingeplant ist. Der Threadkontext enthält alle Informationen, die der Thread benötigt, um die Ausführung nahtlos fortzusetzen. Dies schließt auch seine CPU-Register und seinen Stapel im Adressraum des Hostprozesses vom Thread ein.  
  
 Das .NET Framework unterteilt einen Betriebssystemprozess weiter in einfache, verwaltete Teilprozesse, sogenannte Anwendungsdomänen, die durch <xref:System.AppDomain?displayProperty=nameWithType> repräsentiert werden. Dabei können beliebig viele verwaltete Threads (repräsentiert durch <xref:System.Threading.Thread?displayProperty=nameWithType>) in einer beliebigen Anzahl von Anwendungsdomänen innerhalb desselben verwalteten Prozesses ausgeführt werden. Obwohl in jeder Anwendungsdomäne mit nur einem einzigen Thread begonnen wird, können mithilfe von Code in dieser Anwendungsdomäne zusätzliche Anwendungsdomänen und zusätzliche Threads erstellt werden. Infolgedessen kann sich ein verwalteter Thread frei zwischen Anwendungsdomänen innerhalb desselben verwalteten Prozesses bewegen. Möglicherweise ist auch nur ein Thread vorhanden, der sich zwischen mehreren Anwendungsdomänen bewegt.  
  
 Ein Betriebssystem, das präemptives Multitasking unterstützt, erzielt den Effekt der gleichzeitigen Ausführung mehrerer Threads aus mehreren Prozessen. Dazu wird die verfügbare Prozessorzeit auf die Threads aufgeteilt, die diese benötigen, und jedem Thread wird nacheinander ein Prozessorzeitsegment zugewiesen. Der aktuell ausgeführte Thread wird angehalten, wenn sein Zeitsegment abgelaufen ist, und ein anderer Thread wird wieder gestartet. Wenn das System von einem Thread zu einem anderen wechselt, speichert es den Threadkontext des vorzeitig angehaltenen Threads und lädt den gespeicherten Threadkontext des nächsten Threads in die Threadwarteschlange.  
  
 Die Länge des Zeitsegments hängt vom Betriebssystem und vom Prozessor ab. Da jedes Zeitsegment relativ klein ist, scheinen mehrere Threads gleichzeitig ausgeführt zu werden, selbst wenn es nur einen Prozessor gibt. Dies ist tatsächlich bei Multiprozessorsystemen der Fall, bei denen die ausführbaren Threads auf die verfügbaren Prozessoren verteilt sind.  
  
## <a name="when-to-use-multiple-threads"></a>Verwendung mehrerer Threads  
 Bei Software, mit der Benutzer interagieren, muss diese für ein optimales Benutzererlebnis schnellstmöglich auf die Aktivitäten des Benutzers reagieren. Gleichzeitig muss die Software aber auch die notwendigen Berechnungen durchführen, um dem Benutzer die Daten so schnell wie möglich zur Verfügung zu stellen. Wenn Ihre Anwendung nur einen einzigen Ausführungsthread verwendet, können Sie [asynchrone Programmierung](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md) mit [.NET Framework-Remoting](http://msdn.microsoft.com/library/eccb1d31-0a22-417a-97fd-f4f1f3aa4462) oder [XML-Webdiensten](http://msdn.microsoft.com/library/1e64af78-d705-4384-b08d-591a45f4379c) kombinieren, die mit ASP.NET erstellt wurden. So können Sie die Verarbeitungszeit anderer Computer zusätzlich zu der Ihres eigenen Computers nutzen, um die Reaktionsfähigkeit gegenüber dem Benutzer zu erhöhen und die Datenverarbeitungszeit Ihrer Anwendung zu verringern. Wenn Sie intensive Eingabe-/Ausgabeprozesse ausführen, können Sie auch E/A-Abschlussports verwenden, um die Reaktionsfähigkeit Ihrer Anwendung zu erhöhen.  
  
### <a name="advantages-of-multiple-threads"></a>Vorteile von mehreren Threads  
 Die Verwendung von mehr als einem Thread ist die leistungsfähigste verfügbare Technik, um die Reaktionsfähigkeit gegenüber dem Benutzer zu erhöhen und fast gleichzeitig die erforderliche Datenverarbeitung zu erledigen. Auf einem Computer mit einem Prozessor können mehrere Threads diesen Effekt erzielen, indem sie die kurzen Zeiträume zwischen den Benutzerereignissen nutzen, um die Daten im Hintergrund zu verarbeiten. Beispielsweise kann ein Benutzer eine Tabellenkalkulation bearbeiten, während ein anderer Thread andere Teile der Tabellenkalkulation innerhalb derselben Anwendung neu berechnet.  
  
 Ohne Modifikation würde die gleiche Anwendung die Benutzerzufriedenheit drastisch erhöhen, wenn sie auf einem Computer mit mehr als einem Prozessor ausgeführt wird. Ihre einzelne Anwendungsdomäne könnte mehrere Threads verwenden, um die folgenden Tasks abzuschließen:  
  
-   Kommunizieren über ein Netzwerk mit einem Webserver und einer Datenbank  
  
-   Ausführen von zeitaufwendigen Vorgängen  
  
-   Unterscheiden von Tasks unterschiedlicher Priorität. Beispielsweise verwaltet ein Thread mit hoher Priorität zeitkritische Tasks, und ein Thread mit niedriger Priorität führt andere Tasks aus.  
  
-   Gewährleisten einer reaktionsschnellen Benutzeroberfläche bei gleichzeitigem Zuweisen von Zeitsegmenten für im Hintergrund ausgeführten Tasks  
  
### <a name="disadvantages-of-multiple-threads"></a>Nachteile von mehreren Threads  
 Es wird empfohlen, möglichst wenige Threads zu verwenden, da dadurch die Nutzung der Betriebssystemressourcen minimiert und die Leistung verbessert wird. Zudem müssen Sie bei der Entwicklung Ihrer Anwendung für das Threading entsprechende Ressourcenanforderungen und potenzielle Konflikte berücksichtigen. Die Ressourcenanforderungen sehen wie folgt aus:  
  
-   Das System belegt Arbeitsspeicher für die Kontextinformationen, die von Prozessen, **AppDomain**-Objekten und Threads benötigt werden. Daher ist die Anzahl der Prozesse, **AppDomain**-Objekte und Threads, die erstellt werden können, durch den verfügbaren Arbeitsspeicher begrenzt.  
  
-   Die Verfolgung einer großen Anzahl von Threads verbraucht erhebliche Prozessorzeit. Wenn es zu viele Threads gibt, werden die meisten von ihnen keine nennenswerten Fortschritte machen. Befinden sich die meisten der aktuellen Threads in nur einem Prozess, werden Threads in anderen Prozessen seltener eingeplant.  
  
-   Die Steuerung der Codeausführung mit vielen Threads ist komplex und kann eine Quelle für viele Fehler sein.  
  
-   Wenn Sie Threads zerstören, müssen Sie wissen, welche Probleme auftreten können und wie Sie diese beheben.  
  
 Die Bereitstellung eines gemeinsamen Zugriffs auf Ressourcen kann zu Konflikten führen. Um Konflikte zu vermeiden, müssen Sie den Zugriff auf gemeinsam genutzte Ressourcen synchronisieren oder steuern. Wenn der Zugriff nicht korrekt synchronisiert wird (in den gleichen oder verschiedenen Anwendungsdomänen), kann es zu Problemen wie Deadlocks (in denen zwei Threads nicht mehr reagieren, während jeder auf den Abschluss des anderen wartet) und Racebedingungen kommen (wenn ein anomales Ergebnis aufgrund einer unerwarteten kritischen Abhängigkeit bei der zeitlichen Steuerung zweier Ereignisse auftritt). Das System stellt Synchronisierungsobjekte zur Verfügung, mit denen die gemeinsame Nutzung von Ressourcen zwischen mehreren Threads koordiniert werden können. Zudem wird die Synchronisierung von Ressourcen durch eine geringere Anzahl von Threads vereinfacht.  
  
 Für folgende Ressourcen ist eine Synchronisierung erforderlich:  
  
-   Systemressourcen (z.B. Kommunikationsanschlüsse)  
  
-   Von mehreren Prozessen (z.B. Dateihandles) verwendete Ressourcen  
  
-   Ressourcen einer einzelnen Anwendungsdomäne (z.B. globale, statische und Instanzfelder) mit Zugriff durch mehrere Threads  
  
### <a name="threading-and-application-design"></a>Threading und Anwendungsentwurf  
 Im Allgemeinen ist die Verwendung der <xref:System.Threading.ThreadPool>-Klasse der einfachste Weg, um mehrere Threads für relativ kurze Tasks zu steuern, die andere Threads nicht blockieren, sofern Sie keine besondere Planung der Tasks erwarten. Es gibt jedoch eine Reihe von Gründen, eigene Threads zu erstellen:  
  
-   Wenn Sie eine Task mit einer bestimmten Priorität benötigen.  
  
-   Wenn Sie eine Task verwenden, die wahrscheinlich längere Zeit ausgeführt wird (und deshalb andere Tasks blockiert).  
  
-   Wenn Sie Threads in einem Singlethread-Apartment platzieren müssen (alle **ThreadPool**-Threads befinden sich im Multithread-Apartment).  
  
-   Wenn Sie eine stabile Identität benötigen, die mit dem Thread verbunden ist. Zum Beispiel sollten Sie einen dedizierten Thread verwenden, um ihn abbrechen, anhalten oder anhand des Namens suchen zu können.  
  
-   Wenn Sie Hintergrundthreads ausführen müssen, die mit der Benutzeroberfläche interagieren. Hierfür bietet die .NET Framework Version 2.0 eine <xref:System.ComponentModel.BackgroundWorker>-Komponente, die Ereignisse verwendet, um über threadübergreifendes Marshalling mit dem Benutzeroberflächenthread zu kommunizieren.  
  
### <a name="threading-and-exceptions"></a>Threading und Ausnahmen  
 Behandeln Sie Ausnahmen in Threads. Unbehandelte Ausnahmen in Threads, selbst Hintergrundthreads, beenden in der Regel den Prozess. Für diese Regel gelten jedoch die folgenden drei Ausnahmen:  
  
-   In einem Thread wird eine <xref:System.Threading.ThreadAbortException> ausgelöst, da <xref:System.Threading.Thread.Abort%2A> aufgerufen wurde.  
  
-   In einem Thread wird eine <xref:System.AppDomainUnloadedException> ausgelöst, da die Anwendungsdomäne entladen wird.  
  
-   Der Prozess wurde durch die Common Language Runtime oder einen Hostprozess beendet.  
  
 Weitere Informationen finden Sie unter [Ausnahmen in verwalteten Threads](../../../docs/standard/threading/exceptions-in-managed-threads.md).  
  
> [!NOTE]
>  In den .NET Framework-Versionen 1.0 und 1.1 erfasst die Common Language Runtime automatisch einige Ausnahmen. z.B. in Threadpoolthreads. Dies kann den Anwendungszustand beschädigen und dazu führen, dass die Anwendung nicht mehr reagiert. Das Debuggen kann erhebliche Schwierigkeiten bereiten.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Threading.ThreadPool>  
 <xref:System.ComponentModel.BackgroundWorker>  
 [Datensynchronisierung für Multithreading](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)  
 [Der verwaltete Threadpool](../../../docs/standard/threading/the-managed-thread-pool.md)
