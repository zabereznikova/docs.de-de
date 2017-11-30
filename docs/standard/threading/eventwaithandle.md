---
title: EventWaitHandle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], EventWaitHandle class
- EventWaitHandle class
- event wait handles [.NET Framework]
- threading [.NET Framework], cross-process synchronization
ms.assetid: 11ee0b38-d663-4617-b793-35eb6c64e9fc
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1bd248133bd95ff05246eb36a8e250247fd7ed61
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="eventwaithandle"></a>EventWaitHandle
Die <xref:System.Threading.EventWaitHandle> Klasse kann Threads durch das signalisieren und Signale warten miteinander zu kommunizieren. Ereignis-Wait-Handles (auch einfach als Ereignisse bezeichnet) werden Wait-Handles, die signalisiert werden können, um eine oder mehrere wartende Threads zurückzugeben. Nach es signalisiert wird, wird einem Ereignis-Wait-Handle entweder manuell oder automatisch zurückgesetzt. Die <xref:System.Threading.EventWaitHandle> Klasse kann entweder ein lokales Ereignis Wait-Handle (lokales Ereignis) darstellen, oder ein benanntes Systemereignis-wait-Handle (benannten Ereignis oder Systemereignis für alle Prozesse sichtbar).  
  
> [!NOTE]
>  Ereignis-Wait-Handles sind keine Ereignisse in dem Sinne, die in der Regel durch das Wort in .NET Framework vorgesehen. Es gibt keine Delegaten oder einen Ereignishandler beteiligt. Das Wort "Ereignis" dient zum sie beschreiben, da sie normalerweise als Betriebssystem-Ereignisse bezeichnet wurden haben und die Act anzeigenden das Wait-Handle zu wartenden Threads angibt, die ein Ereignis aufgetreten ist.  
  
 Sowohl lokale als auch benannte Ereignis-Wait-Handles verwenden Synchronisierungsobjekte des Systems, die durch geschützt sind <xref:Microsoft.Win32.SafeHandles.SafeWaitHandle> Wrapper um sicherzustellen, dass die Ressourcen freigegeben werden. Sie können die <xref:System.Threading.WaitHandle.Dispose%2A> Methode, um die Ressourcen freizugeben, sofort nach Beendigung unter Verwendung des Objekts.  
  
## <a name="event-wait-handles-that-reset-automatically"></a>Ereignis-Wait-Handles, die automatisch zurückgesetzt.  
 Erstellen Sie ein Automatisches Rücksetzen-Ereignis, durch Angabe <xref:System.Threading.EventResetMode.AutoReset?displayProperty=nameWithType> beim Erstellen der <xref:System.Threading.EventWaitHandle> Objekt. Wie der Name schon sagt, wird dieses Synchronisierungsereignis automatisch zurückgesetzt, wenn nach der Freigabe eines einzelnen wartenden Threads signalisiert. Signalisiert das Ereignis durch Aufrufen seiner <xref:System.Threading.EventWaitHandle.Set%2A> Methode.  
  
 Automatisches Rücksetzen Ereignisse werden normalerweise verwendet, um exklusiven Zugriff auf eine Ressource für einen einzelnen Thread zu einem Zeitpunkt bereitzustellen. Ein Thread die Ressource anfordert, durch Aufrufen der <xref:System.Threading.WaitHandle.WaitOne%2A> Methode. Wenn kein anderer Thread das Wait-Handle enthalten kann, gibt die Methode `true` und der aufrufende Thread hat die Steuerung der Ressource.  
  
> [!IMPORTANT]
>  Wie bei allen Synchronisierungsmechanismen, müssen Sie sicherstellen, dass alle Codepfade in der entsprechenden Wait-Handle warten, bevor Sie den Zugriff auf eine geschützte Ressource. Threadsynchronisierung ist kooperativ.  
  
 Wenn ein Automatisches Rücksetzen Ereignis signalisiert wird, wenn keine Threads warten, bleibt es signalisiert, bis ein Thread versucht, darauf zu warten. Das Ereignis den Thread freigibt und sofort zurückgesetzt werden, sodass nachfolgende Threads blockiert.  
  
## <a name="event-wait-handles-that-reset-manually"></a>Ereignis-Wait-Handles, die das manuelle Zurücksetzen  
 Erstellen Sie ein Ereignis für manuelles Zurücksetzen, indem <xref:System.Threading.EventResetMode.ManualReset?displayProperty=nameWithType> beim Erstellen der <xref:System.Threading.EventWaitHandle> Objekt. Wie der Name schon sagt, wird dieses Synchronisierungsereignis muss manuell zurückgesetzt werden, nachdem es signalisiert worden ist. Bis zum Zurücksetzen, durch Aufrufen seiner <xref:System.Threading.EventWaitHandle.Reset%2A> -Methode, Threads, die auf das Ereignis-Handle zu warten fortsetzen sofort ohne zu blockieren.  
  
 Ein manuelles Zurücksetzen Ereignis verhält sich wie das Gate eines Tiergeheges. Wenn das Ereignis signalisiert wird, Threads, die darauf warten zu blockieren, z. B. Pferde Geheges. Wenn das Ereignis signalisiert wurde, durch Aufrufen seiner <xref:System.Threading.EventWaitHandle.Set%2A> -Methode, alle wartenden Threads sind frei, um den Vorgang fortzusetzen. Das Ereignis bleibt signalisiert, bis seine <xref:System.Threading.EventWaitHandle.Reset%2A> -Methode aufgerufen wird. Dadurch wird dem Zurücksetzungsereignis für manuelles auf eine ideale Möglichkeit, um Threads zu speichern, die müssen warten, bis ein Thread eine Aufgabe abgeschlossen hat.  
  
 Wie Pferde Tiergeheges verlassen dauert es Zeit für die freigegebene Threads, die vom Betriebssystem geplant werden und die Ausführung fortzusetzen. Wenn die <xref:System.Threading.EventWaitHandle.Reset%2A> Methode wird aufgerufen, bevor alle Threads, die verbleibenden Threads wieder zu blockieren. Welche Threads wieder und welche Threads blockieren hängt zufällige Faktoren wie die Last auf dem System, die Anzahl der Threads wartet für den Planer und So weiter. Dies ist kein Problem, wenn der Thread, der das Ereignis signalisiert endet, nachdem hat, also die gängigsten Verwendungsmuster. Gegebenenfalls den Thread, der dem Ereignis, um eine neue Aufgabe beginnen, nachdem alle Waiting signalisiert Threads wieder ausgeführt, müssen Sie sie blockieren, bis alle wartenden Threads wieder aufgenommen haben. Andernfalls stehen Ihnen eine Racebedingung, und das Verhalten des Codes ist unvorhersehbar.  
  
## <a name="features-common-to-automatic-and-manual-events"></a>Funktionen, die automatische und manuelle Ereignisse gemeinsam sind  
 In der Regel eine oder mehrere Threads blockiert ein <xref:System.Threading.EventWaitHandle> erst ein Blockierung Thread aufruft, die <xref:System.Threading.EventWaitHandle.Set%2A> -Methode, die einem der wartenden Threads (im Fall von Ereignissen für automatisches Zurücksetzen) oder alle von ihnen frei (im Fall von manuell zurücksetzen Ereignisse). Ein Thread kann darauf hinweisen ein <xref:System.Threading.EventWaitHandle> und dann blockieren, die davon einer atomaren Operation durch Aufrufen der statischen <xref:System.Threading.WaitHandle.SignalAndWait%2A?displayProperty=nameWithType> Methode.  
  
 <xref:System.Threading.EventWaitHandle>Objekte können verwendet werden, mit der statischen <xref:System.Threading.WaitHandle.WaitAll%2A?displayProperty=nameWithType> und <xref:System.Threading.WaitHandle.WaitAny%2A?displayProperty=nameWithType> Methoden. Da die <xref:System.Threading.EventWaitHandle> und <xref:System.Threading.Mutex> beide Klassen ableiten <xref:System.Threading.WaitHandle>, können Sie beide Klassen mit diesen Methoden.  
  
### <a name="named-events"></a>Benannte Ereignisse  
 Windows-Betriebssystem ermöglicht, Ereignis-Wait-Handles zu Namen aufweisen. Ein benanntes Ereignis ist systemweit sichtbar. D. h., sobald das benannte Ereignis erstellt wurde, ist es für alle Threads in allen Prozessen sichtbar. Daher können benannte Ereignisse zum Synchronisieren der Aktivitäten von Prozessen und Threads verwendet werden.  
  
 Sie erstellen ein <xref:System.Threading.EventWaitHandle> Objekt, das ein benanntes Systemereignis darstellt, mit einer der Konstruktoren, die den Namen eines Ereignisses angibt.  
  
> [!NOTE]
>  Da benannte Ereignisse systemweit sichtbar sind, ist es möglich, mehrere <xref:System.Threading.EventWaitHandle> benannte Ereignis Objekte, die die gleiche darstellen. Bei jedem eines Konstruktors Aufruf oder der <xref:System.Threading.EventWaitHandle.OpenExisting%2A> -Methode, wird ein neuer <xref:System.Threading.EventWaitHandle> Objekt erstellt wird. Wiederholt den gleichen Namen angeben, erstellt mehrere Objekte, die dasselbe benannte Ereignis darstellen.  
  
 Vorsicht wird empfohlen, in die Verwendung von benannten Ereignisse. Da sie systemweit sichtbar sind, kann ein anderer Prozess, der den gleichen Namen verwendet unerwartet Ihre Threads blockiert. Böswilliger Code, der auf demselben Computer ausgeführt wird, könnte dies als Grundlage für einen Denial-of-Service-Angriff verwenden.  
  
 Verwenden Sie die zugriffssteuerungssicherheit zum Schutz einer <xref:System.Threading.EventWaitHandle> Objekt, das ein benanntes Ereignis vorzugsweise darstellt, über einen Konstruktor, der angibt, ein <xref:System.Security.AccessControl.EventWaitHandleSecurity> Objekt. Sie können auch anwenden, mittels der Sicherheit der <xref:System.Threading.EventWaitHandle.SetAccessControl%2A> -Methode, aber dies bleibt so ein verwundbarkeitszeitfenster zwischen der Erstellung der Ereignis-Wait-Handle und die Zeit, die sie geschützt ist. Schützen von Ereignissen mit der Zugriffssteuerung Sicherheit schützt böswillige Angriffe zu verhindern, aber dieser Mechanismus löst nicht des Problems unbeabsichtigter Namenskonflikte.  
  
> [!NOTE]
>  Im Gegensatz zu den <xref:System.Threading.EventWaitHandle> -Klasse, die abgeleiteten Klassen <xref:System.Threading.AutoResetEvent> und <xref:System.Threading.ManualResetEvent> kann darstellen, die nur lokale wait-Handles. Sie können keine benanntes Systemereignisse darstellen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Threading.EventWaitHandle>  
 <xref:System.Threading.WaitHandle>  
 <xref:System.Threading.AutoResetEvent>  
 <xref:System.Threading.ManualResetEvent>  
 [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)
