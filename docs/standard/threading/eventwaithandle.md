---
title: "EventWaitHandle | Microsoft Docs"
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
  - "threading [.NET Framework], EventWaitHandle class"
  - "EventWaitHandle class"
  - "event wait handles [.NET Framework]"
  - "threading [.NET Framework], cross-process synchronization"
ms.assetid: 11ee0b38-d663-4617-b793-35eb6c64e9fc
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# EventWaitHandle
Die <xref:System.Threading.EventWaitHandle>\-Klasse gibt Threads durch das Signalisieren und das Warten auf Signale die Möglichkeit, miteinander zu kommunizieren.  Bei den Ereignis\-Wait\-Handles \(auch Ereignisse genannt\) handelt es sich um Wait\-Handles, die signalisiert werden können, um einen oder mehrere Threads freizugeben.  Nachdem ein Ereignis\-Wait\-Handle signalisiert worden ist, wird es entweder manuell oder automatisch zurückgesetzt.  Die <xref:System.Threading.EventWaitHandle>\-Klasse stellt entweder ein lokales Ereignis\-Wait\-Handle \(lokales Ereignis\) oder ein namentlich durch das System benanntes Ereignis\-Wait\-Handle \(benanntes Ereignis oder benanntes Systemereignis\) dar, das für alle Prozesse sichtbar ist.  
  
> [!NOTE]
>  Ereignis\-Wait\-Handles sind keine Ereignisse im Sinne des Worts, wie es in .NET Framework verwendet wird.  Denn es sind weder Delegaten noch Ereignishandler beteiligt.  Das Wort "Ereignis" wurde deshalb gewählt, weil die Handles gewöhnlich zu den Betriebssystemereignissen gezählt werden. Darüber hinaus teilt das Wait\-Handle durch den Vorgang des Signalisierens wartenden Threads mit, dass ein Ereignis aufgetreten ist.  
  
 Sowohl lokale als auch benannte Wait\-Handles verwenden Synchronisierungsobjekte des Systems, die von <xref:Microsoft.Win32.SafeHandles.SafeWaitHandle>\-Wrappern geschützt werden, um die Freigabe der Ressourcen zu gewährleisten.  Wenn Sie das Objekt nicht mehr verwenden, können Sie die <xref:System.Threading.WaitHandle.System%23IDisposable%23Dispose%2A>\-Methode nutzen, um die Ressourcen sofort freizugeben.  
  
## Ereignis\-Wait\-Handles mit automatischer Zurücksetzung  
 Sie erstellen ein automatisches Zurücksetzungsereignis, indem Sie <xref:System.Threading.EventResetMode?displayProperty=fullName> angeben, wenn Sie das <xref:System.Threading.EventWaitHandle>\-Objekt erstellen.  Wie der Name bereits verrät, wird ein solches Synchronisierungsereignis automatisch zurückgesetzt, wenn ein einzelner wartender Thread freigegeben und dies signalisiert wurde.  Das Ereignis wird signalisiert, indem dessen <xref:System.Threading.EventWaitHandle.Set%2A>\-Methode aufgerufen wird.  
  
 Automatische Zurücksetzungsereignisse werden gewöhnlich verwendet, um einzelnen Threads jeweils exklusiven Zugriff auf eine Ressource zu gewähren.  Ein Thread fordert die Ressource an, indem er die <xref:System.Threading.WaitHandle.WaitOne%2A>\-Methode aufruft.  Wenn das Wait\-Handle nicht im Besitz eines anderen Threads ist, gibt die Methode `true` zurück, und der aufrufende Thread hat die Steuerung über die Ressource inne.  
  
> [!IMPORTANT]
>  Sie müssen wie bei allen Synchronisierungsvorgängen sicherstellen, dass alle Codepfade auf das entsprechende Wait\-Handle warten, bevor sie auf eine geschützte Ressource zugreifen.  Die Synchronisierung von Threads ist kooperativ.  
  
 Wird ein automatisches Zurücksetzungsereignis signalisiert, und es sind keine wartenden Threads vorhanden, dann bleibt das Ereignis signalisiert, bis ein wartender Thread vorhanden ist.  Das Ereignis gibt den Thread frei und setzt sofort zurück, sodass nachfolgende Threads blockiert werden.  
  
## Ereignis\-Wait\-Handles mit manueller Zurücksetzung  
 Sie erzeugen ein manuelles Zurücksetzungsereignis, indem Sie <xref:System.Threading.EventResetMode?displayProperty=fullName> angeben, wenn Sie das <xref:System.Threading.EventWaitHandle>\-Objekt erstellen.  Wie der Name bereits angibt, muss dieses Synchronisierungsereignis manuell zurückgesetzt werden, nachdem es signalisiert worden ist.  Wenn das Ereignis noch nicht zurückgesetzt ist und die <xref:System.Threading.EventWaitHandle.Reset%2A>\-Methode aufgerufen wird, dann fahren die auf das Ereignis\-Handle wartenden Ereignisse ohne zeitliche Verzögerung fort, da sie nicht blockiert werden.  
  
 Ein manuelles Zurücksetzungsereignis ist in seiner Funktion mit dem Gatter eines Tiergeheges vergleichbar.  Wenn das Ereignis nicht signalisiert wird, dann wird es von den wartenden Threads blockiert, wie Pferde das Gatter ihres Geheges blockieren würden.  Wenn das Ereignis durch Aufrufen seiner <xref:System.Threading.EventWaitHandle.Set%2A>\-Methode signalisiert wird, können alle wartenden Threads fortfahren.  Das Ereignis bleibt auf den Status signalisiert festgelegt, bis dessen <xref:System.Threading.EventWaitHandle.Reset%2A>\-Methode aufgerufen wird.  Insofern eignet sich das manuelle Zurücksetzungsereignis besonders für das Blockieren von Threads, die darauf warten müssen, dass ein anderer Thread eine Aufgabe beendet.  
  
 Das Freilassen der Pferde nimmt wie das Einplanen freigegebener Threads durch das Betriebssystem \(zur Wiederaufnahme der Ausführung\) eine gewisse Zeit in Anspruch.  Wird die <xref:System.Threading.EventWaitHandle.Reset%2A>\-Methode aufgerufen, bevor alle Threads erneut ausgeführt werden, dann werden die verbleibenden Threads erneut blockiert.  Welche Threads wieder ausgeführt und welche blockiert werden, hängt von Zufallsfaktoren wie der Auslastung des Systems, der Zahl der auf den Planer wartenden Threads usw. ab.  Dies ist nicht weiter problematisch, wenn der Thread, der das Ereignis signalisiert, nach der Signalisierung beendet wird. Hierbei handelt es sich um das gängigste Verwendungsschema.  Wenn Sie möchten, dass der das Ereignis signalisierende Thread eine neue Aufgabe beginnen soll, nachdem alle wartenden Threads wieder ausgeführt werden, dann müssen Sie den Thread bis zu diesem Zeitpunkt blockieren.  Andernfalls liegt eine Racebedingung vor, und das Verhalten des Codes ist unvorhersehbar.  
  
## Gemeinsame Merkmale automatischer und manueller Ereignisse  
 Normalerweise wird ein <xref:System.Threading.EventWaitHandle> von einem oder mehreren Threads blockiert, bis ein nicht blockierter Thread die <xref:System.Threading.EventWaitHandle.Set%2A>\-Methode aufruft, wodurch entweder einer der wartenden Threads \(bei automatischen Zurücksetzungsereignissen\) oder alle Threads \(bei manuellen Zurücksetzungsereignissen\) freigegeben werden.  Ein Thread kann einen <xref:System.Threading.EventWaitHandle> signalisieren und diesen dann in einem automatisch ablaufenden Prozess blockieren, indem er die statische <xref:System.Threading.WaitHandle.SignalAndWait%2A?displayProperty=fullName>\-Methode aufruft.  
  
 Auf <xref:System.Threading.EventWaitHandle>\-Objekte sind die statische <xref:System.Threading.WaitHandle.WaitAll%2A?displayProperty=fullName>\-Methode und die statische <xref:System.Threading.WaitHandle.WaitAny%2A?displayProperty=fullName>\-Methode anwendbar.  Da sowohl die <xref:System.Threading.EventWaitHandle>\-Klasse als auch die <xref:System.Threading.Mutex>\-Klasse vom <xref:System.Threading.WaitHandle> abgeleitet werden können, sind diese Methoden auf beide Klassen anwendbar.  
  
### Benannte Ereignisse  
 Im Windows\-Betriebssystem können Wait\-Handles Namen tragen.  Ein Ereignis, das mit einem Namen versehen wurde, ist systemweit sichtbar.  Das heißt, sobald das benannte Ereignis erzeugt wird, ist es für alle Threads in allen Prozessen sichtbar.  Auf diese Weise können benannte Ereignisse verwendet werden, um die Aktivitäten von Prozessen und von Threads zu synchronisieren.  
  
 Sie können zur Darstellung eines benannten Systemereignisses ein <xref:System.Threading.EventWaitHandle>\-Objekt erstellen, indem Sie einen der Konstruktoren verwenden, die einen Ereignisnamen angeben.  
  
> [!NOTE]
>  Da benannte Ereignisse systemweit sichtbar sind, besteht die Möglichkeit, zur Darstellung eines benannten Ereignisses mehrere <xref:System.Threading.EventWaitHandle>\-Objekte zu verwenden.  Bei jedem Aufruf eines Konstruktors oder der <xref:System.Threading.EventWaitHandle.OpenExisting%2A>\-Methode wird ein neues <xref:System.Threading.EventWaitHandle>\-Objekt erstellt.  Wenn Sie wiederholt denselben Namen verwenden, werden zur Darstellung eines benannten Ereignisses mehrere Objekte erstellt.  
  
 Die Verwendung benannter Ereignisse sollte genau überlegt sein.  Da sie systemweit sichtbar sind, kann ein anderer Prozess, der den gleichen Namen verwendet, die Threads unerwartet blockieren.  Bösartiger Code, der auf demselben Computer ausgeführt wird, könnte dies als Ausgangsbasis für einen Denial\-of\-Service\-Angriff nutzen.  
  
 Verwenden Sie zum Schützen eines <xref:System.Threading.EventWaitHandle>\-Objekts, das ein benanntes Ereignis darstellt, die Sicherheitseinstellungen der Zugriffssteuerung, vorzugsweise unter Verwendung eines Konstruktors, der ein <xref:System.Security.AccessControl.EventWaitHandleSecurity>\-Objekt angibt.  Sie können die Sicherheitseinstellungen der Zugriffssteuerung auch bei der Verwendung der <xref:System.Threading.EventWaitHandle.SetAccessControl%2A>\-Methode nutzen. Allerdings kann hierbei die Sicherheitslücke zwischen Erstellung des Ereignis\-Wait\-Handles und dem Beginn des Schutzes nicht geschlossen werden.  Das Schützen von Ereignissen mit den Sicherheitseinstellungen der Zugriffssteuerung ist bei der Abwehr bösartiger Angriffe hilfreich, löst aber das Problem unbeabsichtigter Namenskonflikte nicht.  
  
> [!NOTE]
>  Im Gegensatz zur <xref:System.Threading.EventWaitHandle>\-Klasse können von der abgeleiteten <xref:System.Threading.AutoResetEvent>\-Klasse und der abgeleiteten <xref:System.Threading.ManualResetEvent>\-Klasse nur lokale Wait\-Handles dargestellt werden.  Benannte Systemereignisse können von ihnen nicht dargestellt werden.  
  
## Siehe auch  
 <xref:System.Threading.EventWaitHandle>   
 <xref:System.Threading.WaitHandle>   
 <xref:System.Threading.AutoResetEvent>   
 <xref:System.Threading.ManualResetEvent>   
 [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)