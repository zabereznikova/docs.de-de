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
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b57cac34009e13c27c6d34a0ab402f9ecbe08305
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="threads-and-threading"></a>Threads und Threading
Betriebssysteme verwenden Prozesse, um die verschiedenen Anwendungen zu trennen, die sie ausgeführt werden. Threads sind die Grundeinheit, zu der ein älteres Betriebssystem Prozessorzeit reserviert, und mehr als ein Thread kann Code in diesem Prozess ausgeführt werden. Jeder Thread beibehält Ausnahmehandler, eine Planungspriorität und einen Satz von Strukturen, die das System verwendet, um den Kontext des Threads zu speichern, bis sie geplant ist. Der Kontext des Threads enthält alle Informationen, die der Thread die Ausführung, einschließlich des Threads Satz von CPU-Registern und zum Stack, im Adressraum des Hostprozesses des Threads nahtlos fortgesetzt werden muss.  
  
 .NET Framework Weitere Betriebssystemprozess eine in einfache verwaltete Unterprozesse, so genannte Anwendungsdomänen, dargestellt durch <xref:System.AppDomain?displayProperty=nameWithType>. Eine oder mehrere verwaltete Threads (dargestellt durch <xref:System.Threading.Thread?displayProperty=nameWithType>) können in beliebiger Anzahl von Anwendungsdomänen innerhalb eines verwalteten Prozesses ausgeführt. Obwohl jede Anwendungsdomäne mit einem einzelnen Thread gestartet wird, kann Code in der Anwendungsdomäne zusätzliche Anwendungsdomänen und zusätzliche Threads erstellen. Das Ergebnis ist, dass ein verwalteter Thread frei zwischen Anwendungsdomänen innerhalb desselben verwalteten Prozesses verschieben kann. Sie müssen möglicherweise nur ein Thread mehrere Anwendungsdomänen navigieren.  
  
 Ein Betriebssystem, präemptives Multitasking unterstützt, erstellt die Auswirkung der gleichzeitige Ausführung mehrerer Threads aus mehreren Prozessen. Dies geschieht durch Dividieren die verfügbare CPU-Zeit bei der Threads, die sie benötigen, Zuordnen von einem Prozessor Zeitscheibe für jeden Thread nach dem anderen. Der gerade ausgeführte Thread wird angehalten, wenn seine Zeitanteil und einem anderen thread gestartet. Wenn das System von einem Thread zu einem anderen gewechselt wird, wird der Threadkontext des vorhergehenden Threads und lädt die gespeicherte Threadkontext des nächsten Threads in der Warteschlange des Threads.  
  
 Die Länge der Zeitscheibe hängt davon ab, das Betriebssystem und Prozessor. Da jede Zeitscheibe klein ist, werden mehrere Threads als zur gleichen Zeit ausgeführt werden angezeigt, selbst wenn nur ein Prozessor vorhanden ist. Dies ist tatsächlich die Groß-/Kleinschreibung auf Systemen mit mehreren Prozessoren, dabei werden die ausführbaren Threads auf verfügbaren Prozessoren verteilt.  
  
## <a name="when-to-use-multiple-threads"></a>Wenn mehrere Threads verwenden.  
 Software, die eine Benutzereingabe erfordert muss so schnell wie möglich, eine leistungsstarke, optimierte Benutzeroberfläche bereitzustellen auf die Aktivitäten des Benutzers reagieren. Allerdings müssen diese Berechnungen zum Präsentieren von Daten für den Benutzer so schnell wie möglich zur gleichen Zeit durchführen. Wenn Ihre Anwendung nur einen Thread der Ausführung verwendet, können Sie kombinieren [asynchrone Programmierung](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md) mit[.NET Framework Remoting](http://msdn.microsoft.com/en-us/eccb1d31-0a22-417a-97fd-f4f1f3aa4462) oder [XML-Webdienste](http://msdn.microsoft.com/en-us/1e64af78-d705-4384-b08d-591a45f4379c) mit ASP erstellt .NET die Verarbeitungszeit der anderen Computer darüber hinaus mit Ihren eigenen erhöhen Reaktionsfähigkeit für den Benutzer und verringern die Datenverarbeitungszeit Ihrer Anwendung verwenden. Wenn Sie ressourcenintensive e/a arbeiten, können Sie auch e/a-Abschlussports verwenden, Reaktionsfähigkeit der Anwendung erhöhen.  
  
### <a name="advantages-of-multiple-threads"></a>Vorteile von mehreren Threads  
 Mit mehr als einem Thread, ist jedoch die leistungsstärkste Verfahren, die Reaktionszeit für den Benutzer zu erhöhen und Verarbeiten von Daten erforderlich sind, um die Aufgabe zu erledigen zur nahezu gleichen Zeit zur Verfügung. Auf einem Computer mit einem Prozessor kann mehrere Threads dieser Effekt, nutzen die kleine Zeiträume zwischen Benutzerereignisse zum Verarbeiten der Daten im Hintergrund erstellen. Beispielsweise kann ein Benutzer ein Arbeitsblatt bearbeiten, während ein anderer Thread andere Teile der Kalkulationstabelle innerhalb derselben Anwendung neu berechnet.  
  
 Ohne Änderung würde die gleiche Anwendung Benutzerzufriedenheit bei Ausführung auf einem Computer mit mehr als ein Prozessor erheblich erhöhen. Eine einzelne Anwendungsdomäne kann mehrere Threads verwenden, die folgenden Aufgaben ausgeführt:  
  
-   Kommunikation über ein Netzwerk an einen Webserver, und klicken Sie in einer Datenbank.  
  
-   Vorgänge, die eine große Menge an Zeit dauern.  
  
-   Zu unterscheiden Sie Aufgaben, die mit unterschiedlichen Priorität. Angenommen, ein Thread mit hoher Priorität verwaltet zeitkritische Aufgaben und ein Thread mit niedriger Priorität andere Aufgaben ausführt.  
  
-   Ermöglichen Sie die Benutzeroberfläche reaktionsfähig, bleiben beim belegen von Hintergrundaufgaben.  
  
### <a name="disadvantages-of-multiple-threads"></a>Nachteile von mehreren Threads  
 Es wird empfohlen, dass Sie so wenig Threads als möglich, minimieren dadurch die Verwendung von Betriebssystemressourcen und Verbessern der Leistung verwenden. Threading verfügt auch über ressourcenanforderungen und mögliche Konflikte beim Entwerfen Ihrer Anwendung berücksichtigt werden. Die ressourcenanforderungen lauten folgendermaßen:  
  
-   Das System nutzt Arbeitsspeicher für die Kontextinformationen erforderlich sind, von Prozessen, **AppDomain** Objekte und Threads. Aus diesem Grund wird die Anzahl von Prozessen, **AppDomain** Objekte und der Threads, die erstellt werden können durch den verfügbaren Speicher beschränkt ist.  
  
-   Nachverfolgen der eine große Anzahl von Threads beansprucht erhebliche Prozessorzeit. Wenn zu viele Threads vorhanden sind, werden die meisten von ihnen nicht signifikante Fortschritte. Wenn die meisten der aktuellen Threads in einem Prozess sind, werden Threads in anderen Prozessen weniger häufig geplant.  
  
-   Steuern der Ausführung von Code mit vielen Threads ist komplex und kann viele Fehler von Quelle sein.  
  
-   Zerstören von Threads ist erforderlich, zu wissen, was passieren kann, und diese Probleme zu behandeln.  
  
 Die Freigabe des Zugriffs auf Ressourcen kann zu Konflikten führen. Um Konflikte zu vermeiden, müssen Sie zu synchronisieren oder das Aktivieren des Zugriffs auf freigegebene Ressourcen. Fehler beim Synchronisieren des Zugriffs (in der gleichen oder anderen Anwendungsdomänen) ordnungsgemäß kann zu Problemen wie Deadlocks (in der zwei Threads reagieren, während jede andere abgeschlossen wartet) führen und Racebedingungen (tritt ein anormales Ergebnis aufgrund ein unerwarteter kritische Abhängigkeit die zeitliche Abfolge der beiden Ereignisse). Das System stellt die Synchronisierungsobjekte, die verwendet werden können, zum Koordinieren der Ressourcenfreigabe zwischen mehreren Threads bereit. Reduzierung der Anzahl von Threads erleichtert es zur Synchronisierung von Ressourcen.  
  
 Ressourcen, die eine Synchronisierung erfordern, gehören:  
  
-   Systemressourcen (z. B. Kommunikationsanschlüsse).  
  
-   Ressourcen von mehreren Prozessen (z. B. Dateihandles).  
  
-   Die Ressourcen einer einzelnen Anwendungsdomäne (z. B. globale, statische und Instanzfelder) durch mehrere Threads zugegriffen.  
  
### <a name="threading-and-application-design"></a>Threading und Anwendung entwerfen  
 Im Allgemeinen ist die Verwendung der <xref:System.Threading.ThreadPool> Klasse ist die einfachste Möglichkeit, mehrere Threads für relativ kurze Aufgaben, die andere Threads nicht blockiert werden und wenn Sie nicht erwarten keine bestimmte Planung der Aufgaben, zu behandeln. Es gibt jedoch eine Reihe von Gründen, eigene Threads erstellen:  
  
-   Wenn Sie eine Aufgabe auf einer bestimmten Priorität benötigen.  
  
-   Wenn Sie eine Aufgabe verfügen, die möglicherweise eine lange Laufzeit (und blockieren daher den anderen Aufgaben).  
  
-   Wenn Sie Threads in einem Singlethread Apartment einfügen müssen (alle **ThreadPool** Threads befinden sich im Multithread-Apartment).  
  
-   Wenn Sie eine stabile Identität, die dem Thread zugeordneten benötigen. Beispielsweise sollten Sie einen dedizierten Thread verwenden, diesen Thread Abbrechen, angehalten oder nach Namen zu ermitteln.  
  
-   Wenn Sie Hintergrundthreads, die Interaktion mit der Benutzeroberfläche ausführen müssen, bietet der .NET Framework Version 2.0 einer <xref:System.ComponentModel.BackgroundWorker> Komponente, die mithilfe von Ereignissen, mit der Marshallingvorgänge für den Benutzeroberflächenthread kommuniziert.  
  
### <a name="threading-and-exceptions"></a>Threading und Ausnahmen  
 Behandeln Sie Ausnahmen in Threads. Nicht behandelte Ausnahmen in Threads, sogar Hintergrundthreads, werden im Allgemeinen den Prozess beenden. Für diese Regel gelten jedoch die folgenden drei Ausnahmen:  
  
-   Ein <xref:System.Threading.ThreadAbortException> in einem Thread ausgelöst wird, da <xref:System.Threading.Thread.Abort%2A> aufgerufen wurde.  
  
-   Ein <xref:System.AppDomainUnloadedException> in einem Thread ausgelöst wird, da die Anwendungsdomäne entladen wird.  
  
-   Der Prozess wurde durch die Common Language Runtime oder einen Hostprozess beendet.  
  
 Weitere Informationen finden Sie unter [Ausnahmen in verwalteten Threads](../../../docs/standard/threading/exceptions-in-managed-threads.md).  
  
> [!NOTE]
>  In der .NET Framework-Versionen 1.0 und 1.1 fängt die common Language Runtime im Hintergrund einige Ausnahmen, z. B. in Threads im Threadpool. Dies kann Anwendungszustand beschädigen und dazu führen, dass die Anwendung nicht mehr reagiert, die möglicherweise sehr schwer zu beheben.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Threading.ThreadPool>  
 <xref:System.ComponentModel.BackgroundWorker>  
 [Datensynchronisierung für Multithreading](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)  
 [Der verwaltete Threadpool](../../../docs/standard/threading/the-managed-thread-pool.md)
