---
title: EventWaitHandle
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], EventWaitHandle class
- EventWaitHandle class
- event wait handles [.NET Framework]
- threading [.NET Framework], cross-process synchronization
ms.assetid: 11ee0b38-d663-4617-b793-35eb6c64e9fc
ms.openlocfilehash: 80c90254978495a58d228c4302eda84d6165c800
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73138078"
---
# <a name="eventwaithandle"></a>EventWaitHandle
Die <xref:System.Threading.EventWaitHandle>-Klasse ermöglicht Threads, durch Signalisieren und Warten auf Signale miteinander zu kommunizieren. Ereignis-Wait-Handles (die auch einfach als „Ereignisse“ bezeichnet werden) sind Wait-Handles, die als Signale verwendet werden können, damit ein oder mehrere wartende Threads freigegeben werden. Nachdem ein Ereignis-Wait-Handle als Signal verwendet wurde, wird es entweder manuell oder automatisch zurückgesetzt. Die <xref:System.Threading.EventWaitHandle>-Klasse kann entweder ein lokales Ereignis-Wait-Handle (lokales Ereignis) darstellen oder ein Ereignis-Wait-Handle eines benannten Systems (benanntes Ereignis oder Systemereignis, für alle Prozesse sichtbar).  
  
> [!NOTE]
> Ereignis-Wait-Handles sind keine .NET-[Ereignisse](../events/index.md). Es sind keine Delegaten oder Ereignishandler beteiligt. Zur Beschreibung wird das Wort „Ereignis“ verwendet, weil diese Handles traditionell als Betriebssystemereignisse bezeichnet wurden und weil durch Verwenden eines Wait-Handles als Signal wartende Threads darüber informiert werden, dass ein Ereignis aufgetreten ist.  
  
 Sowohl lokale als auch benannte Ereignis-Wait-Handles verwenden Synchronisierungsobjekte des Systems, die durch <xref:Microsoft.Win32.SafeHandles.SafeWaitHandle>-Wrapper geschützt sind, um sicherzustellen, dass die Ressourcen freigegeben werden. Sie können die <xref:System.Threading.WaitHandle.Dispose%2A>-Methode verwenden, um die Ressourcen sofort freizugeben, nachdem die Verwendung des Objekts beendet wurde.  
  
## <a name="event-wait-handles-that-reset-automatically"></a>Ereignis-Wait-Handles mit automatischer Rücksetzung  
 Sie können ein Ereignis mit automatischer Rücksetzung erstellen, indem Sie <xref:System.Threading.EventResetMode.AutoReset?displayProperty=nameWithType> angeben, wenn Sie das <xref:System.Threading.EventWaitHandle>-Objekt erstellen. Wie der Name schon sagt, wird dieses Synchronisierungsereignis nach der Verwendung als Signal automatisch zurückgesetzt, nachdem ein einzelner wartender Thread freigegeben wurde. Verwenden Sie das Ereignis als Signal, indem Sie seine <xref:System.Threading.EventWaitHandle.Set%2A>-Methode aufrufen.  
  
 Um den exklusiven Zugriff auf eine Ressource für einen einzelnen Thread zu einem bestimmten Zeitpunkt sicherzustellen, werden Ereignisse mit automatischer Rücksetzung verwendet. Ein Thread fordert die Ressource durch Aufrufen der <xref:System.Threading.WaitHandle.WaitOne%2A>-Methode an. Wenn kein anderer Thread das Wait-Handle enthält, gibt die Methode `true` zurück, und der aufrufende Thread erhält die Steuerung über die Ressource.  
  
> [!IMPORTANT]
> Wie bei allen Synchronisierungsmechanismen müssen Sie sicherstellen, dass alle Codepfade vor dem Zugriff auf eine geschützte Ressource auf das entsprechende Wait-Handle warten. Die Threadsynchronisierung ist kooperativ.  
  
 Wenn ein Ereignis mit automatischer Rücksetzung als Signal verwendet wird und zu diesem Zeitpunkt keine Threads warten, bleibt es ein Signal, bis ein Thread versucht, darauf zu warten. Das Ereignis gibt den Thread frei und wird sofort zurückgesetzt, sodass nachfolgende Threads blockiert werden.  
  
## <a name="event-wait-handles-that-reset-manually"></a>Ereignis-Wait-Handles mit manueller Rücksetzung  
 Sie können ein Ereignis mit manueller Rücksetzung erstellen, indem Sie <xref:System.Threading.EventResetMode.ManualReset?displayProperty=nameWithType> angeben, wenn Sie das <xref:System.Threading.EventWaitHandle>-Objekt erstellen. Wie der Name schon sagt, muss dieses Synchronisierungsereignis nach der Verwendung als Signal manuell zurückgesetzt werden. Bis das Ereignis durch Aufrufen der <xref:System.Threading.EventWaitHandle.Reset%2A>-Methode zurückgesetzt wird, können Threads, die auf das Ereignishandle warten, sofort fortgesetzt werden, ohne blockiert zu werden.  
  
 Ein Ereignis mit manueller Rücksetzung funktioniert wie das Gatter einer Pferdekoppel. Wenn das Ereignis nicht als Signal verwendet wird, sind Threads, die darauf warten, blockiert, also sozusagen wie Pferde auf einer Koppel eingesperrt. Wenn das Ereignis durch Aufrufen der <xref:System.Threading.EventWaitHandle.Set%2A>-Methode als Signal verwendet wird, werden alle Threads befreit und können fortgesetzt werden. Das Ereignis bleibt so lange ein Signal, bis seine <xref:System.Threading.EventWaitHandle.Reset%2A>-Methode aufgerufen wird. Daher ist das Ereignis mit manueller Rücksetzung eine ideale Möglichkeit, Threads zu verzögern, die warten müssen, bis ein bestimmter Thread einen Task abgeschlossen hat.  
  
 Wie bei Pferden auf einer Koppel dauert es eine Zeitlang, bis die freigegebenen Threads vom Betriebssystem geplant werden und die Ausführung fortgesetzt wird. Wenn die <xref:System.Threading.EventWaitHandle.Reset%2A>-Methode aufgerufen wird, bevor die Ausführung aller Threads fortgesetzt wird, werden die verbleibenden Threads erneut blockiert. Welche Threads fortgesetzt und welche blockiert werden, hängt von zufälligen Faktoren ab, wie z.B. der Auslastung des Systems, der Anzahl von Threads, die auf den Planer warten, usw. Dies ist kein Problem, wenn der Thread, der ein Ereignis als Signal verwendet, danach beendet wird. Dies ist das häufigste Verwendungsmuster. Wenn Sie möchten, dass der Thread, der das Ereignis als Signal verwendet hat, nach dem Fortsetzen aller wartenden Threads einen neuen Task beginnt, müssen Sie den Thread blockieren, bis alle wartenden Threads fortgesetzt wurden. Andernfalls liegt eine Racebedingung vor, und das Verhalten des Codes ist unvorhersehbar.  
  
## <a name="features-common-to-automatic-and-manual-events"></a>Gemeinsame Features für automatische und manuelle Ereignisse  
 In der Regel ist mindestens ein Thread in einem <xref:System.Threading.EventWaitHandle> blockiert, bis ein nicht blockierter Thread die <xref:System.Threading.EventWaitHandle.Set%2A>-Methode aufruft, die (bei Ereignissen mit automatischer Rücksetzung) einen wartenden Thread oder (bei Ereignissen mit manueller Rücksetzung) alle wartenden Threads freigibt. Ein Thread kann ein <xref:System.Threading.EventWaitHandle> als Signal verwenden und dann durch Aufrufen der statischen <xref:System.Threading.WaitHandle.SignalAndWait%2A?displayProperty=nameWithType>-Methode als atomischer Vorgang blockiert werden.  
  
 <xref:System.Threading.EventWaitHandle>-Objekte können mit den statischen Methoden <xref:System.Threading.WaitHandle.WaitAll%2A?displayProperty=nameWithType> und <xref:System.Threading.WaitHandle.WaitAny%2A?displayProperty=nameWithType> verwendet werden. Da die Klassen <xref:System.Threading.EventWaitHandle> und <xref:System.Threading.Mutex> von <xref:System.Threading.WaitHandle> abgeleitet werden, können Sie beide Klassen mit diesen Methoden verwenden.  
  
### <a name="named-events"></a>Benannte Ereignisse  
 Das Windows-Betriebssystem ermöglicht es, Event-Wait-Handles zu benennen. Ein benanntes Ereignis ist systemweit sichtbar. Das heißt, sobald das benannte Ereignis erstellt wurde, ist es für alle Threads in allen Prozessen sichtbar. Folglich können benannte Ereignisse zum Synchronisieren der Aktivitäten von Prozessen und Threads verwendet werden.  
  
 Sie können ein <xref:System.Threading.EventWaitHandle>-Objekt erstellen, das ein benanntes Systemereignis darstellt, indem Sie einen der Konstruktoren verwenden, die einen Ereignisnamen angeben.  
  
> [!NOTE]
> Da benannte Ereignisse systemweit sichtbar sind, ist es möglich, über mehrere <xref:System.Threading.EventWaitHandle>-Objekte zu verfügen, die dasselbe benannte Ereignis darstellen. Bei jedem Aufruf eines Konstruktors oder der <xref:System.Threading.EventWaitHandle.OpenExisting%2A>-Methode wird ein neues <xref:System.Threading.EventWaitHandle>-Objekt erstellt. Wenn Sie wiederholt denselben Namen angeben, werden mehrere Objekte erstellt, die dasselbe benannte Ereignis darstellen.  
  
 Bei der Verwendung von benannten Ereignissen ist Vorsicht geboten. Da sie systemweit sichtbar sind, kann ein anderer Prozess, der den gleichen Namen verwendet, Ihre Threads unerwartet blockieren. Böswilliger Code, der auf demselben Computer ausgeführt wird, könnte dies als Grundlage für einen Denial-of-Service-Angriff verwenden.  
  
 Verwenden Sie die Zugriffssteuerungssicherheit zum Schutz eines <xref:System.Threading.EventWaitHandle>-Objekts, das ein benanntes Ereignis darstellt, vorzugsweise durch Verwendung eines Konstruktors, der ein <xref:System.Security.AccessControl.EventWaitHandleSecurity>-Objekt angibt. Sie können die Zugriffssteuerungssicherheit auch mithilfe der <xref:System.Threading.EventWaitHandle.SetAccessControl%2A>-Methode anwenden, allerdings entsteht dann zwischen der Erstellung und dem Schutz des Ereignis-Wait-Handles ein Zeitraum, in dem ein Sicherheitsrisiko besteht. Der Schutz von Ereignissen mit Zugriffssteuerungssicherheit hilft dabei, böswillige Angriffe zu verhindern, das Problem unbeabsichtigter Namenskonflikte wird dadurch aber nicht gelöst.  
  
> [!NOTE]
> Im Gegensatz zur <xref:System.Threading.EventWaitHandle>-Klasse können die abgeleiteten Klassen <xref:System.Threading.AutoResetEvent> und <xref:System.Threading.ManualResetEvent> nur lokale Wait-Handles darstellen. Sie können keine benannten Systemereignisse darstellen.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Threading.EventWaitHandle>
- <xref:System.Threading.WaitHandle>
- <xref:System.Threading.AutoResetEvent>
- <xref:System.Threading.ManualResetEvent>
