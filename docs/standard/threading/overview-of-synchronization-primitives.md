---
title: Übersicht über Synchronisierungsprimitiven
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- synchronization, threads
- threading [.NET Framework],synchronizing threads
- managed threading
ms.assetid: b782bcb8-da6a-4c6a-805f-2eb46d504309
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 37abcb6b3a8fdf4ef91d5e946a97db7ca1428ce8
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2018
ms.locfileid: "47204598"
---
# <a name="overview-of-synchronization-primitives"></a>Übersicht über Synchronisierungsprimitiven
<a name="top"></a> .NET Framework stellt eine Reihe von Synchronisierungsmechanismen zum Steuern der Interaktionen von Threads und zum Vermeiden von Racebedingungen bereit. Diese können grob in drei Kategorien eingeteilt werden: Sperren, Signalisieren und Interlocked-Vorgänge.  
  
 Diese Kategorien sind weder präzise noch klar definiert: Einige Synchronisierungsmechanismen weisen Merkmale mehrerer Kategorien auf. Ereignisse, die einen einzelnen Thread zu einem Zeitpunkt freigegeben, funktionieren wie Sperren. Die Freigabe einer Sperren kann als Signal betrachtet werden. und Interlocked-Vorgänge können verwendet werden, um Sperren zu erstellen. Die Kategorien sind jedoch trotzdem.  
  
 Es ist wichtig zu beachten, dass die Threadsynchronisierung kooperativ erfolgt. Wenn auch nur ein Thread einen Synchronisierungsmechanismus umgeht und direkt auf die geschützte Ressource zugreift, kann der Synchronisierungsmechanismus nicht effektiv sein.  
  
 Diese Übersicht enthält folgende Abschnitte:  
  
-   [Sperren](#locking)  
  
-   [Signaling](#signaling)  
  
-   [Einfache Synchronisierungstypen](#lightweight_synchronization_types)  
  
-   [SpinWait](#spinwait)  
  
-   [Interlocked-Vorgänge](#interlocked_operations)  
  
<a name="locking"></a>   
## <a name="locking"></a>Sperren  
 Sperren gewähren jeweils einem Thread oder einer angegebenen Anzahl von Threads die Kontrolle über eine  Ressource. Ein Thread, der eine exklusive Sperre anfordert, wenn die Sperre aktiv ist, wird gesperrt, bis die Sperre verfügbar wird.  
  
### <a name="exclusive-locks"></a>Exklusive Sperren  
 Die einfachste Form einer Sperre ist die `lock`-Anweisung in C# und die `SyncLock`-Anweisung in Visual Basic, die den Zugriff auf einen Codeblock steuert. So ein Block wird häufig als kritischer Abschnitt bezeichnet. Die `lock`-Anweisung wird mithilfe der <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType>- und <xref:System.Threading.Monitor.Exit%2A?displayProperty=nameWithType>-Methode implementiert und verwendet den `try…finally`-Block, um sicherzustellen, dass die Sperre aufgehoben wird.  
  
 Im Allgemeinen ist die Verwendung der `lock`- oder `SyncLock`-Anweisung zum Schützen kleiner Codeblöcke, die nie mehr als eine einzelne Methode umfassen, die beste Verwendung der <xref:System.Threading.Monitor>-Klasse. Die <xref:System.Threading.Monitor>-Klasse ist zwar leistungsstark, aber anfällig für verwaiste Sperren und Deadlocks.  
  
#### <a name="monitor-class"></a>Monitor-Klasse  
 Die <xref:System.Threading.Monitor>-Klasse bietet zusätzliche Funktionen, die in Verbindung mit der `lock`-Anweisung verwendet werden können:  
  
-   Die <xref:System.Threading.Monitor.TryEnter%2A>-Methode ermöglicht es einem Thread, der blockiert ist, zu warten, bis die Ressource nach einem angegebenen Intervall freigegeben wird. Es gibt einen booleschen Wert, der Erfolg oder Fehler angibt und der verwendet werden kann, um potenzielle Deadlocks zu erkennen und zu vermeiden.  
  
-   Die <xref:System.Threading.Monitor.Wait%2A>-Methode wird von einem Thread in einem kritischen Abschnitt aufgerufen. Sie gibt die Steuerung der Ressource auf und blockiert, bis die Ressource wieder verfügbar ist.  
  
-   Die Methoden <xref:System.Threading.Monitor.Pulse%2A> und <xref:System.Threading.Monitor.PulseAll%2A> lassen einen Thread zu, der die Sperre freigibt, oder rufen <xref:System.Threading.Monitor.Wait%2A> auf, um an einen oder mehrere Threads in die Warteschlange einzufügen, sodass diese die Sperre erhalten können.  
  
 Mithilfe von Timeouts für <xref:System.Threading.Monitor.Wait%2A>-Methodenüberladungen können wartende Threads in die Bereitschaftswarteschlange versetzt werden.  
  
 Die <xref:System.Threading.Monitor>-Klasse kann in mehreren Anwendungsdomänen Sperren bereitstellen, wenn das für die Sperre verwendete Objekt von <xref:System.MarshalByRefObject> abgeleitet ist.  
  
 <xref:System.Threading.Monitor> weist Threadaffinität auf. Das heißt, ein Thread im Monitor muss ihn durch Aufrufen von <xref:System.Threading.Monitor.Exit%2A> oder <xref:System.Threading.Monitor.Wait%2A> verlassen.  
  
 Die <xref:System.Threading.Monitor>-Klasse kann nicht instanziiert werden. Ihre Methoden sind statisch (`Shared` in Visual Basic) und reagieren auf ein instanziierbares Sperrobjekt.  
  
 Eine grundlegende Übersicht finden Sie unter [Monitore](https://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db).  
  
#### <a name="mutex-class"></a>Mutex-Klasse  
 Threads fordern eine <xref:System.Threading.Mutex> durch Aufruf einer Überladung der <xref:System.Threading.WaitHandle.WaitOne%2A>-Methode an. Überladungen mit Timeouts werden bereitgestellt, damit Threads den Wartevorgang aufgeben können. Im Gegensatz zur <xref:System.Threading.Monitor>-Klasse kann ein Mutex lokal oder global sein. Globale Mutexe, auch als benannte Mutexe bezeichnet, sind im gesamten Betriebssystem sichtbar und können verwendet werden, um Threads in mehreren Anwendungsdomänen oder Prozessen zu synchronisieren. Lokale Mutexe stammen von <xref:System.MarshalByRefObject> ab und können über Anwendungsdomänengrenzen hinweg verwendet werden.  
  
 Darüber hinaus wird <xref:System.Threading.Mutex> von <xref:System.Threading.WaitHandle> abgeleitet, was bedeutet, dass sie mit Signalisierungsmechanismen verwendet werden kann, die von <xref:System.Threading.WaitHandle> bereitgestellt werden, wie z. B. die Methoden <xref:System.Threading.WaitHandle.WaitAll%2A>, <xref:System.Threading.WaitHandle.WaitAny%2A> und <xref:System.Threading.WaitHandle.SignalAndWait%2A>.  
  
 Wie <xref:System.Threading.Monitor> weist auch <xref:System.Threading.Mutex> Threadaffinität auf. Im Gegensatz zu <xref:System.Threading.Monitor> kann <xref:System.Threading.Mutex>-Objekt instanziiert werden.  
  
 Eine grundlegende Übersicht finden Sie unter [Mutexe](../../../docs/standard/threading/mutexes.md).  
  
#### <a name="spinlock-class"></a>SpinLock-Klasse  
 Beginnend mit [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] können Sie die <xref:System.Threading.SpinLock>-Klasse verwenden, wenn der von <xref:System.Threading.Monitor> erforderte Aufwand die Leistung beeinträchtigt. Wenn <xref:System.Threading.SpinLock> auf einen gesperrten kritischen Abschnitt stößt, bleibt sie einfach in einer Schleife, bis die Sperre verfügbar wird. Wenn die Sperre für eine sehr kurze Zeit aufrechterhalten wird, bieten Spinvorgänge eine bessere Leistung als das Blockieren. Wenn aber die Sperre für mehr als einige Zehntel Zyklen aufrechterhalten wird, ist die Leistung von <xref:System.Threading.SpinLock> genauso gut wie von <xref:System.Threading.Monitor>, verwendet aber mehr CPU-Zyklen und kann so die Leistung von anderen Threads oder Prozessen beeinträchtigen.  
  
### <a name="other-locks"></a>Andere Sperren  
 Sperren müssen nicht exklusiv sein. Es ist häufig nützlich, eine begrenzte Anzahl von Threads gleichzeitigen Zugriff auf eine Ressource zu ermöglichen. Semaphoren und Lese-/Schreibsperren sollen diese Art von Zugriff auf einen Ressourcenpool steuern.  
  
#### <a name="readerwriterlock-class"></a>ReaderWriterLock-Klasse  
 Die <xref:System.Threading.ReaderWriterLockSlim>-Klasse wird verwendet, wenn ein Thread, der Daten ändert (der Writer) exklusiven Zugriff auf eine Ressource haben muss. Wenn der Writer nicht aktiv ist, kann eine beliebige Anzahl Readern auf die Ressource zugreifen (z. B. durch Aufrufen der <xref:System.Threading.ReaderWriterLockSlim.EnterReadLock%2A>-Methode). Wenn ein Thread exklusiven Zugriff anfordert (z. B. durch Aufrufen der <xref:System.Threading.ReaderWriterLockSlim.EnterWriteLock%2A>-Methode), werden nachfolgende Readeranforderungen blockiert, bis alle vorhandenen Reader die Sperre beendet haben und der Writer die Sperre aktiviert und beendet hat.  
  
 <xref:System.Threading.ReaderWriterLockSlim> weist Threadaffinität auf.  
  
 Eine grundlegende Übersicht finden Sie unter [Lese-/Schreibsperren](../../../docs/standard/threading/reader-writer-locks.md).  
  
#### <a name="semaphore-class"></a>Semaphore-Klasse  
 Die <xref:System.Threading.Semaphore>-Klasse ermöglicht einer festgelegten Anzahl von Threads den Zugriff auf eine Ressource. Zusätzliche Threads fordern den Ressourcenblock an, bis ein Thread das Semaphor freigibt.  
  
 Wie die <xref:System.Threading.Mutex>-Klasse wird auch <xref:System.Threading.Semaphore> von <xref:System.Threading.WaitHandle> abgeleitet. Wie <xref:System.Threading.Mutex> kann auch <xref:System.Threading.Semaphore> entweder lokal oder global sein. Diese Klasse kann über Anwendungsdomänengrenzen hinweg verwendet werden.  
  
 Im Gegensatz zu <xref:System.Threading.Monitor>, <xref:System.Threading.Mutex> und <xref:System.Threading.ReaderWriterLock> weist <xref:System.Threading.Semaphore> keine Threadaffinität auf. Das heißt, sie kann in Szenarien verwendet werden, in denen ein Thread das Semaphor erhält und ein anderer es freigibt.  
  
 Eine grundlegende Übersicht finden Sie unter [Semaphore und SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md).  
  
 <xref:System.Threading.SemaphoreSlim?displayProperty=nameWithType> ist ein einfaches Semaphor für die Synchronisierung innerhalb einer einzelnen Prozessgrenze.  
  
 [Zurück zum Anfang](#top)  
  
<a name="signaling"></a>   
## <a name="signaling"></a>Signaling  
 Die einfachste Möglichkeit, auf ein Signal von einem anderen Thread zu warten, ist das Aufrufen der <xref:System.Threading.Thread.Join%2A>-Methode, die blockiert, bis der andere Thread abgeschlossen ist. <xref:System.Threading.Thread.Join%2A> verfügt über zwei Überladungen, die es einem blockierten Thread ermöglichen, den Wartevorgang nach ein angegebenen Intervall zu verlassen.  
  
 Wait-Handles stellen viel umfangreichere Warte- und Signalfunktionen bereit.  
  
### <a name="wait-handles"></a>Wait-Handles  
 Wait-Handles stammen von der <xref:System.Threading.WaitHandle>-Klasse ab, die wiederum von <xref:System.MarshalByRefObject> abstammt. Folglich können Wait-Handles verwendet werden, um die Aktivitäten von Threads über Anwendungsdomänengrenzen hinweg zu synchronisieren.  
  
 Threads blockieren Wait-Handles durch Aufrufen der Instanzmethode <xref:System.Threading.WaitHandle.WaitOne%2A> oder einer der statischen Methoden <xref:System.Threading.WaitHandle.WaitAll%2A>, <xref:System.Threading.WaitHandle.WaitAny%2A> oder <xref:System.Threading.WaitHandle.SignalAndWait%2A>. Wie sie freigegeben werden, hängt von der aufgerufenen Methode sowie von der Art des Wait-Handles ab.  
  
 Eine grundlegende Übersicht finden Sie unter [Wait-Handle](https://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489).  
  
#### <a name="event-wait-handles"></a>Ereignis-Wait-Handles  
 Ereignis-Wait-Handles schließen die <xref:System.Threading.EventWaitHandle>-Klasse und die abgeleiteten Klassen <xref:System.Threading.AutoResetEvent> und <xref:System.Threading.ManualResetEvent> ein. Threads werden von einem Ereignis-Wait-Handle freigegeben, wenn das Ereignis-Wait-Handle durch Aufrufen der <xref:System.Threading.EventWaitHandle.Set%2A>-Methode oder mithilfe der <xref:System.Threading.WaitHandle.SignalAndWait%2A>-Methode signalisiert wird.  
  
 Ereignis-Wait-Handles setzen sich entweder selbst automatisch zurück (wie ein Drehkreuz, das bei jedem Signalisieren nur einen Thread durchlässt) oder müssen manuell zurückgesetzt werden (wie ein Tor, das bis zum Signal geschlossen und dann geöffnet wird, bis es jemand wieder schließt. Wie die Namen bereits andeuten stellen <xref:System.Threading.AutoResetEvent> und <xref:System.Threading.ManualResetEvent> die beiden genannten Handles dar. <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> ist ein einfaches Ereignis für die Synchronisierung innerhalb einer einzelnen Prozessgrenze.  
  
 Ein <xref:System.Threading.EventWaitHandle> kann beide Ereignistypen darstellen und entweder lokal oder global sein. Die abgeleiteten Klassen <xref:System.Threading.AutoResetEvent> und <xref:System.Threading.ManualResetEvent> sind immer lokal.  
  
 Ereignis-Wait-Handles weisen keine Threadaffinität auf. Jeder Thread kann einem Ereignis-Wait-Handle signalisiert.  
  
 Eine grundlegende Übersicht finden Sie unter [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md).  
  
#### <a name="mutex-and-semaphore-classes"></a>Mutex- und Semaphore-Klassen  
 Da die Klassen <xref:System.Threading.Mutex> und <xref:System.Threading.Semaphore> von <xref:System.Threading.WaitHandle> abgeleitet werden, können sie mit den statischen Methoden von <xref:System.Threading.WaitHandle> verwendet werden. Ein Thread kann z. B. mithilfe der <xref:System.Threading.WaitHandle.WaitAll%2A>-Methode warten, bis alle drei der folgenden Bedingungen erfüllt sind: ein <xref:System.Threading.EventWaitHandle> wird signalisiert, ein <xref:System.Threading.Mutex> wird freigegeben und ein <xref:System.Threading.Semaphore> wird freigegeben. Ebenso kann ein Thread mithilfe der <xref:System.Threading.WaitHandle.WaitAny%2A>-Methode warten, bis eine dieser Bedingungen erfüllt ist.  
  
 Für ein <xref:System.Threading.Mutex> oder ein <xref:System.Threading.Semaphore> bedeutet Signalisierung, freigegeben zu werden. Wenn einer der Typen als erstes Argument der <xref:System.Threading.WaitHandle.SignalAndWait%2A>-Methode verwendet wird, wird er freigegeben. Im Fall eines <xref:System.Threading.Mutex>, der Threadaffinität aufweist, wird eine Ausnahme ausgelöst, wenn der aufrufende Thread das Mutex nicht besitzt. Wie bereits erwähnt, weisen Semaphore keine Threadaffinität auf.  
  
#### <a name="barrier"></a>Barriere  
 Die <xref:System.Threading.Barrier>-Klasse bietet eine Möglichkeit, mehrere Threads zyklisch zu synchronisieren, sodass sie gleichzeitig am gleichen Punkt blocken und warten, bis alle anderen Threads abgeschlossen sind. Eine Barriere ist nützlich, wenn ein oder mehrere Threads die Ergebnisse eines anderen Threads benötigen, um mit der nächsten Phase eines Algorithmus fortzufahren. Weitere Informationen finden Sie unter [Barrier](../../../docs/standard/threading/barrier.md).  
  
 [Zurück zum Anfang](#top)  
  
<a name="lightweight_synchronization_types"></a>   
## <a name="lightweight-synchronization-types"></a>Einfache Synchronisierungstypen  
 Ab [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] können Sie Synchronisierungsprimitiven verwenden, die schnelle Leistung durch Vermeiden teurer Abhängigkeiten von Win32-Kernelobjekten bereitstellen, wie z. B. Wait-Handles (sofern möglich). Im Allgemeinen sollten Sie diese Typen verwenden, wenn die Wartezeiten kurz sind und nur dann, wenn die ursprünglichen Synchronisierungstypen ausprobiert und als unzureichend eingestuft wurden. Die einfachen Typen können nicht in Szenarien verwendet werden, die prozessübergreifende Kommunikation erfordern.  
  
-   <xref:System.Threading.SemaphoreSlim?displayProperty=nameWithType> ist eine einfache Version von <xref:System.Threading.Semaphore?displayProperty=nameWithType>.  
  
-   <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> ist eine einfache Version von <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>.  
  
-   <xref:System.Threading.CountdownEvent?displayProperty=nameWithType> stellt ein Ereignis dar, das signalisiert wird, wenn die Anzahl null ist.  
  
-   <xref:System.Threading.Barrier?displayProperty=nameWithType> ermöglicht die Synchronisierung mehrerer Threads miteinander, ohne dass die Steuerung durch einen Master-Thread erforderlich ist. Eine Barriere verhindert, dass jeder Thread fortgesetzt wird, bis alle Threads einen bestimmten Punkt erreicht haben.  
  
 [Zurück zum Anfang](#top)  
  
<a name="spinwait"></a>   
## <a name="spinwait"></a>SpinWait  
 Ab [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] können Sie die <xref:System.Threading.SpinWait?displayProperty=nameWithType>-Struktur verwenden, wenn ein Thread warten muss, bis ein Ereignis signalisiert oder eine Bedingung erfüllt wird, außer wenn die tatsächliche Wartezeit voraussichtlich kürzer als die erforderliche Wartezeit beim Verwenden eines Wait-Handles oder einer anderen Blockierung des aktuellen Threads ist. Mithilfe von <xref:System.Threading.SpinWait> können Sie einen kurzen Wartezeitraum angeben und danach nur dann auslösen (z. B. durch Warten oder Ruhezustand), wenn die Bedingung nicht in der angegebenen Zeit erfüllt wurde.  
  
 [Zurück zum Anfang](#top)  
  
<a name="interlocked_operations"></a>   
## <a name="interlocked-operations"></a>Interlocked-Vorgänge  
 Interlocked-Vorgänge sind einfache atomare Operationen auf einen Speicherbereich durch statische Methoden der <xref:System.Threading.Interlocked>-Klasse. Diese atomaren Operationen umfassen Addition, Inkrementieren und Dekrementieren, Austausch, bedingter Austausch je nach Vergleich und Lesevorgänge für 64-Bit-Werte auf 32-Bit-Plattformen.  
  
> [!NOTE]
>  Die Garantie der Unteilbarkeit gilt nur für einzelne Vorgänge. Wenn mehrere Vorgänge als Einheit ausgeführt werden müssen, muss ein gröberer Synchronisierungsmechanismus verwendet werden.  
  
 Obwohl keine dieser Vorgänge Sperren oder Signale sind, können sie zum Erstellen von Sperren und Signalen verwendet werden. Da sie systemeigene Vorgänge des Windows-Betriebssystems sind, sind Interlocked-Vorgänge äußerst schnell.  
  
 Interlocked-Vorgänge können mit Garantien für flüchtigen Speicher verwendet werden, um Anwendungen zu schreiben, die leistungsstarke nicht blockierende Parallelität ermöglichen. Allerdings benötigen sie ausgefeilte, systemnahe Programmierung, sodass in den meisten Fällen einfache Sperren besser geeignet sind.  
  
 Eine grundlegende Übersicht finden Sie unter [Interlock-Vorgänge](../../../docs/standard/threading/interlocked-operations.md).  
  
## <a name="see-also"></a>Siehe auch

- [Datensynchronisierung für Multithreading](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)  
- [Monitore](https://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db)  
- [Mutexe](../../../docs/standard/threading/mutexes.md)  
- [Semaphore and SemaphoreSlim (Semaphore und SemaphoreSlim)](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)  
- [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
- [Wait-Handles](https://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
- [Interlocked-Vorgänge](../../../docs/standard/threading/interlocked-operations.md)  
- [Lese-/Schreibsperren](../../../docs/standard/threading/reader-writer-locks.md)  
- [Barrier](../../../docs/standard/threading/barrier.md)  
- [SpinWait](../../../docs/standard/threading/spinwait.md)  
- [SpinLock](../../../docs/standard/threading/spinlock.md)
