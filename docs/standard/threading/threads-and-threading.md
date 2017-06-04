---
title: "Threads and Threading | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "multiple threads"
  - "threading [.NET Framework]"
  - "threading [.NET Framework], multiple threads"
ms.assetid: 5baac3aa-e603-4fa6-9f89-0f2c1084e6b1
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# Threads and Threading
Zur Trennung der verschiedenen Anwendungen, die durch ein Betriebssystem ausgeführt werden, dienen Prozesse.  Die Basiseinheit für die Zuordnung von CPU\-Zeit durch das Betriebssystem stellen die Threads dar. Innerhalb eines Prozesses kann mehr als ein Thread Code ausführen.  Jeder Thread verfügt über Ausnahmehandler, eine Priorität für die Ablaufplanung und eine Gruppe von Strukturen, um den Kontext bis zur Aufnahme des Threads in den Ablaufplan zu speichern.  Der Threadkontext beinhaltet alle Informationen, die der Thread zur nahtlosen Wiederaufnahme der Ausführung im Adressbereich des Hostprozesses des Threads benötigt, einschließlich des zugehörigen Satzes von CPU\-Registern und Stapeln.  
  
 Darüber hinaus unterteilt .NET Framework einen Betriebssystemprozess in einfache verwaltete Unterprozesse, so genannte Anwendungsdomänen, die durch <xref:System.AppDomain?displayProperty=fullName> dargestellt werden.  Ein oder mehrere verwaltete Threads \(dargestellt durch <xref:System.Threading.Thread?displayProperty=fullName>\) können in beliebiger Anzahl von Anwendungsdomänen innerhalb desselben verwalteten Prozesses ausgeführt werden.   Obwohl jede Anwendungsdomäne mit einem einzigen Thread gestartet wird, kann der Code in dieser Anwendungsdomäne zusätzliche Anwendungsdomänen und weitere Threads erstellen.  Dadurch kann sich ein verwalteter Thread frei zwischen Anwendungsdomänen innerhalb desselben verwalteten Prozesses bewegen. Gegebenenfalls kann es einen einzelnen Thread geben, der sich zwischen verschiedenen Anwendungsdomänen bewegt.  
  
 Ein Betriebssystem, das präemptives Multitasking unterstützt, kann mehrere Threads von verschiedenen Prozessen gleichzeitig ausführen.  Das geschieht, indem die verfügbare CPU\-Zeit unter den Threads aufgeteilt wird. Dabei wird nacheinander jedem Thread ein Anteil der CPU\-Zeit zugeordnet.  Läuft der jeweilige Zeitanteil ab, wird der momentan ausführende Thread unterbrochen und ein anderer Thread gestartet.  Beim Wechsel von einem Thread zu einem anderen wird der Threadkontext des vorhergehenden Threads vom System gespeichert und der gespeicherte Threadkontext des nächsten Threads in die Threadwarteschlange geladen.  
  
 Die Länge eines Zeitabschnitts ist von Betriebssystem und Prozessor abhängig.  Da die einzelnen Zeitanteile klein sind, entsteht der Eindruck, dass mehrere Threads gleichzeitig ausgeführt werden, auch wenn nur ein Prozessor vorhanden ist.  Dies ist bei Systemen mit mehreren Prozessoren auch tatsächlich der Fall, bei denen die ausführbaren Threads unter den verfügbaren Prozessoren aufgeteilt werden.  
  
## Wann werden mehrere Threads verwendet?  
 Software, die auf Interaktion mit dem Benutzer ausgerichtet ist, muss möglichst schnell auf Benutzeraktivitäten reagieren können, um optimale Ergebnisse zu liefern.  Gleichzeitig muss jedoch auch die notwendige Rechenleistung erbracht werden, damit die Daten dem Benutzer auf schnellstem Wege zur Verfügung stehen.  Wenn Sie beim Ausführen einer Anwendung nur einen einzelnen Thread verwenden, können Sie [asynchrone Programmierung](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md) mit [.NET Framework Remoting](http://msdn.microsoft.com/de-de/eccb1d31-0a22-417a-97fd-f4f1f3aa4462) oder [XML\-Webdiensten](http://msdn.microsoft.com/de-de/1e64af78-d705-4384-b08d-591a45f4379c) kombinieren, die mit ASP.NET erstellt wurden. Dadurch kann die Verarbeitungszeit anderer Computer zusätzlich zu der Ihres Computers genutzt werden, was die Ansprechempfindlichkeit der Anwendung gegenüber Benutzeraktivitäten erhöht und die Zeit für die Datenverarbeitung verkürzt.  Bei der Durchführung intensiver Eingabe\-\/Ausgabearbeiten können Sie auch E\/A\-Komplettierungsports verwenden, um die Ansprechempfindlichkeit der Anwendung zu steigern.  
  
### Vorteile der Verwendung mehrerer Threads  
 Die Verwendung mehrerer Threads ist die effektivste Methode, um die Ansprechempfindlichkeit zu steigern und nahezu zeitgleich die notwendigen Daten zu verarbeiten.  Bei einem Computer mit nur einem Prozessor kann der Einsatz mehrerer Threads diesen Effekt hervorrufen, indem die kleinen Zeitintervalle zwischen den Benutzerereignissen zur Datenverarbeitung im Hintergrund genutzt werden.  Ein Benutzer kann beispielsweise ein Arbeitsblatt bearbeiten, während ein anderer Thread andere Teile des Arbeitsblatts innerhalb derselben Anwendung neu berechnet.  
  
 Ohne weitere Veränderungen würde dieselbe Anwendung auf einem Computer mit mehreren Prozessoren noch weitaus bessere Ergebnisse liefern.  Eine einzelne Anwendungsdomäne kann mehrere Threads zur Ausführung folgender Aufgaben verwenden:  
  
-   Kommunikation über ein Netzwerk, mit einem Webserver und mit einer Datenbank.  
  
-   Durchführen zeitaufwendiger Operationen.  
  
-   Unterscheiden von Aufgaben nach unterschiedlicher Priorität.  Ein Thread mit hoher Priorität übernimmt beispielsweise Aufgaben mit hoher Dringlichkeitsstufe, während ein Thread mit niedriger Priorität andere Aufgaben ausführt.  
  
-   Aufrechterhalten der Benutzeroberflächen\-Reaktivität, während Hintergrundaufgaben bearbeitet werden.  
  
### Nachteile der Verwendung mehrerer Threads  
 Es empfiehlt sich, so wenig Threads wie möglich zu verwenden, um die Beanspruchung von Betriebssystemressourcen zu minimieren und somit die Leistung zu steigern.  Beim Entwurf einer Anwendung müssen bezüglich des Threadings sowohl Ressourcenanforderungen als auch potenzielle Konflikte in Betracht gezogen werden.  Die Ressourcenanforderungen lauten wie folgt:  
  
-   Das System nimmt Arbeitsspeicher für die Kontextinformationen in Anspruch, die für Prozesse, **AppDomain**\-Objekte und Threads erforderlich sind.  Deshalb ist die Anzahl der Prozesse, **AppDomain**\-Objekte und Threads, die erstellt werden können, durch den verfügbaren Arbeitsspeicher begrenzt.  
  
-   Eine große Anzahl von Threads nimmt einen beträchtlichen Teil der CPU\-Zeit in Anspruch.  Bei zu vielen Threads kann die Ausführung der meisten nur ungenügend vorankommen.  Wenn sich die meisten der aktuellen Threads in einem Prozess befinden, werden Threads in anderen Prozessen weniger häufig in den Ablaufplan aufgenommen.  
  
-   Das Steuern der Codeausführung mit vielen Threads ist sehr komplex und kann viele Fehler verursachen.  
  
-   Das Löschen von Threads erfordert Kenntnisse über mögliche Auswirkungen und deren Behandlung.  
  
 Der Zugriff auf gemeinsam genutzte Ressourcen kann zu Konflikten führen.  Durch Steuerung oder Synchronisierung des Zugriffs auf gemeinsame Ressourcen können solche Konflikte vermieden werden.  Fehler bei der Synchronisierung des Zugriffs \(innerhalb derselben oder in verschiedenen Anwendungsdomänen\) können Probleme wie z. B. Deadlocks \(dabei wird die Ausführung zweier Threads beendet, weil jeder auf den anderen Thread warten muss, um die eigene Ausführung zu beenden\) und Racebedingungen \(bei Auftreten eines abweichenden Ergebnisses infolge einer unerwarteten kritischen Abhängigkeit vom zeitlichen Ablauf zweier Ereignisse\) auftreten.  Das System stellt Synchronisierungsobjekte bereit, die zur Koordination gemeinsamer Ressourcennutzung mehrerer Threads verwendet werden können.  Wird die Anzahl der Threads verringert, erleichtert dies das Synchronisieren von Ressourcen.  
  
 Bei folgenden Ressourcen ist eine Synchronisierung erforderlich:  
  
-   Systemressourcen \(z. B. Kommunikationsanschlüsse\).  
  
-   Ressourcen, die von mehreren Prozessen gemeinsam genutzt werden \(z. B. von Dateihandles\).  
  
-   Ressourcen einer einzelnen Anwendungsdomäne \(z. B. globale, statische und Instanzfelder\), auf die durch mehrere Threads zugegriffen wird.  
  
### Entwurf von Threading und Anwendungen  
 Normalerweise ist die Verwendung der <xref:System.Threading.ThreadPool>\-Klasse die einfachste Methode zur Behandlung mehrerer Threads für relativ kurze Aufgaben, durch die andere Threads nicht blockiert werden und für die keine bestimmte Planung der Aufgaben vorgesehen ist.   Es gibt jedoch eine Reihe von Gründen, eigene Threads zu erstellen:  
  
-   Wenn eine Aufgabe eine bestimmte Priorität haben soll.  
  
-   Wenn eine Aufgabe über einen längeren Zeitraum ausgeführt werden soll und dadurch andere Aufgaben blockiert.  
  
-   Wenn Threads innerhalb eines Singlethread\-Apartments platziert werden müssen \(alle **ThreadPool**\-Threads befinden sich im Multithread\-Apartment\).  
  
-   Wenn dem Thread eine stabile Identität zugeordnet werden soll.  Durch einen eigens erstellten Thread können Sie beispielsweise diesen Thread abbrechen, unterbrechen oder anhand des Namens ausfindig machen.  
  
-   Wenn Sie Hintergrundthreads ausführen möchten, die mit der Benutzeroberfläche interagieren, steht Ihnen in .NET Framework, Version 2.0 eine <xref:System.ComponentModel.BackgroundWorker>\-Komponente zur Verfügung, die mithilfe von Ereignissen kommuniziert, wobei über Threadgrenzen hinausgehende Marshallingvorgänge für den Benutzeroberflächenthread ausgeführt werden.  
  
### Threading und Ausnahmen  
 Behandeln Sie Ausnahmen in Threads.  Unbehandelte Ausnahmen in Threads, sogar in Hintergrundthreads, beenden den Prozess im Allgemeinen.  Für diese Regel gelten jedoch die folgenden drei Ausnahmen:  
  
-   In einem Thread wird eine <xref:System.Threading.ThreadAbortException> ausgelöst, da <xref:System.Threading.Thread.Abort%2A> aufgerufen wurde.  
  
-   In einem Thread wird eine <xref:System.AppDomainUnloadedException> ausgelöst, da die Anwendungsdomäne entladen wird.  
  
-   Der Prozess wurde durch die Common Language Runtime oder einen Hostprozess beendet.  
  
 Weitere Informationen finden Sie unter [Exceptions in Managed Threads](../../../docs/standard/threading/exceptions-in-managed-threads.md).  
  
> [!NOTE]
>  In den .NET Framework\-Versionen 1.0 und 1.1 erfasst die Common Language Runtime einige Ausnahmen, z. B. in Threadpoolthreads, automatisch.  Dies kann den Anwendungszustand beschädigen und dazu führen, dass die Anwendung nicht mehr reagiert. Das Debuggen kann erhebliche Schwierigkeiten bereiten.  
  
## Siehe auch  
 <xref:System.Threading.ThreadPool>   
 <xref:System.ComponentModel.BackgroundWorker>   
 [Synchronizing Data for Multithreading](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)   
 [The Managed Thread Pool](../../../docs/standard/threading/the-managed-thread-pool.md)