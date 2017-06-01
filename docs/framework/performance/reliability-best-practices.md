---
title: "Reliability Best Practices | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "marking locks"
  - "rebooting databases"
  - "denial of service attacks"
  - "back-out code"
  - "SQL Server [.NET Framework], reliability"
  - "synchronization, reliability"
  - "single-threaded COM components"
  - "slow leaks"
  - "suspending threads"
  - "asynchronous exception handling"
  - "leaked resources [.NET Framework]"
  - "unmanaged memory"
  - "memory, reliability"
  - "threading [.NET Framework], reliability"
  - "process-wide domain shared states"
  - "shared states"
  - "SafeHandle class, reliability"
  - "reliability contracts [.NET Framework]"
  - "cleanup operations"
  - "constrained execution regions"
  - "CERs"
  - "finalizers, reliability"
  - "reliability [.NET Framework]"
  - "blocks, reliability"
  - "finally clauses"
  - "cross-application domain shared states"
  - "catch blocks"
  - "identifying locks"
  - "writing reliable code"
  - "impersonation"
  - "GC.KeepAlive method"
  - "managed threading"
  - "locks, reliability"
  - "STA-dependent features"
  - "fibers"
ms.assetid: cf624c1f-c160-46a1-bb2b-213587688da7
caps.latest.revision: 11
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 11
---
# Reliability Best Practices
Die folgenden Regeln zur Zuverlässigkeit sind auf SQL Server ausgerichtet, gelten aber ebenso für jede andere hostbasierte Serveranwendungen.  Bei Servern wie SQL Server ist es von höchster Bedeutung, dass keine Ressourcenverluste oder Betriebsunterbrechungen auftreten.  Dies lässt sich jedoch nicht erreichen, indem für jede Methode, die den Zustand eines Objekts ändert, Abbruchcode verfasst wird.  Das Ziel ist nicht, 100\-prozentig zuverlässigen verwalteten Code zu schreiben, der mit Abbruchcode zu jedem Zeitpunkt jeden Fehler behebt.  Dies wäre eine überwältigende Aufgabe ohne große Aussicht auf Erfolg.  Die CLR \(Common Language Runtime\) kann nicht ohne weiteres Garantien für verwalteten Code geben, die ein Verfassen von perfektem Code in den Bereich des Möglichen rücken.  Ähnlich wie ASP.NET verwendet SQL Server nur einen einzigen Prozess, der nicht wiederverwendet werden kann, ohne eine Datenbank für einen inakzeptabel langen Zeitraum außer Betrieb zu nehmen.  
  
 Angesichts dieser abgeschwächten Garantien und der Ausführung in einem einzigen Prozess heißt Zuverlässigkeit, Threads zu beenden und Anwendungsdomänen wieder zu verwenden, wenn dies erforderlich ist, und Vorkehrungen dafür zu treffen, dass keine Verluste von Betriebssystemressourcen wie Handles und Arbeitsspeicher auftreten.  Auch bei dieser einfacheren Zuverlässigkeitseinschränkung gibt es immer noch eine bedeutende Anforderung an die Zuverlässigkeit:  
  
-   Es dürfen keine Verluste von Betriebssystemressourcen auftreten.  
  
-   Alle verwalteten Sperren in jeder Form müssen der CLR mitgeteilt werden.  
  
-   Der über Anwendungsdomänen hinweg verwendete Freigabezustand darf nie beschädigt werden, damit die <xref:System.AppDomain>\-Wiederverwendung reibungslos ablaufen kann.  
  
 Auch wenn es theoretisch möglich ist, verwalteten Code zu schreiben, der die Ausnahmen <xref:System.Threading.ThreadAbortException>, <xref:System.StackOverflowException> und <xref:System.OutOfMemoryException> behandelt, wäre es überzogen, von Entwicklern zu verlangen, für eine gesamte Anwendung solchen robusten Code zu schreiben.  Aus diesem Grund führen Out\-of\-Band\-Ausnahmen dazu, dass der ausführende Thread beendet wird und die <xref:System.AppDomain> entladen wird, sofern der beendete Thread dabei war, den Freigabezustand zu bearbeiten, was sich daran erkennen lässt, dass für den Thread eine Sperre vorliegt.  Wenn eine Methode beim Bearbeiten des Freigabezustands beendet wird, wird der Zustand beschädigt, da es nicht möglich ist, zuverlässigen Abbruchcode für Aktualisierungen des Freigabezustands zu schreiben.  
  
 In .NET Framework, Version 2.0, ist SQL Server der einzige Host, der Zuverlässigkeit verlangt.  Wenn die Assembly auf SQL Server ausgeführt wird, sollten Sie Vorkehrungen für die Zuverlässigkeit jedes Teils dieser Assembly treffen, selbst wenn bestimmte Features bei der Ausführung in der Datenbank deaktiviert sind.  Diese Anforderung besteht, weil das Codeanalysemodul Code auf Assemblyebene untersucht und nicht zwischen deaktiviertem und aktiviertem Code unterscheiden kann.  Des Weiteren ist bei der Programmierung für SQL Server zu berücksichtigen, dass SQL Server sämtlichen Code in einem einzigen Prozess ausführt und die <xref:System.AppDomain>\-Wiederverwendung zum Bereinigen aller Ressourcen wie Arbeitsspeicher und Betriebssystemhandles verwendet wird.  
  
 Sie können sich nicht auf den Abbruchcode in Finalizern, Destruktoren oder `try/finally`\-Blöcken verlassen.  Möglicherweise werden diese unterbrochen oder gar nicht aufgerufen.  
  
 Asynchrone Ausnahmen können an unerwarteten Stellen ausgelöst werden, theoretisch in jeder Computeranweisung: <xref:System.Threading.ThreadAbortException>, <xref:System.StackOverflowException> und <xref:System.OutOfMemoryException>.  
  
 Verwaltete Threads sind nicht notwendigerweise Win32\-Threads in SQL, sondern können auch Fibers sein.  
  
 Der prozessweite oder anwendungsdomänenübergreifende veränderliche Freigabezustand kann nur sehr schwer auf sichere Weise geändert werden, was daher möglichst vermieden werden sollte.  
  
 Fehler aufgrund ungenügenden Arbeitsspeichers sind bei SQL Server nicht selten.  
  
 Wenn die auf SQL Server gehosteten Bibliotheken ihren Freigabezustand nicht ordnungsgemäß aktualisieren, ist es sehr wahrscheinlich, dass Code Fehler nicht beheben kann, bevor nicht die Datenbank neu gestartet wurde.  Außerdem ist es in extremen Fällen möglich, dass ein Fehler im SQL Server\-Prozess auftritt und die Datenbank daraufhin neu gestartet wird.  Ein Neustart der Datenbank kann dazu führen, dass auf eine Website nicht mehr zugegriffen werden kann oder der Betriebsablauf beeinträchtigt wird, was sich negativ auf die Verfügbarkeit auswirkt.  Ein langsamer Verlust von Betriebssystemressourcen wie Arbeitsspeicher oder Handles kann dazu führen, dass schließlich beim Zuordnen von Handles ein Fehler auftritt, der nicht behoben werden kann, oder die Leistung des Servers möglicherweise langsam abnimmt und somit die Verfügbarkeit einer Anwendung für den Kunden verringert wird.  Natürlich sollen solche Szenarien vermieden werden.  
  
## Regeln für empfohlene Vorgehensweisen  
 In der Einführung wurde in erster Linie behandelt, worauf bei der Codeprüfung von verwaltetem Code, der auf dem Server ausgeführt wird, zu achten ist, damit die Stabilität und Zuverlässigkeit des Frameworks gesteigert werden kann.  All diese Prüfungen stellen allgemeine empfohlene Vorgehensweisen dar und sind im Fall von Servern unabdingbar.  
  
 Bei einem Deadlock oder einer Ressourceneinschränkung bricht SQL Server einen Thread ab oder beendet eine <xref:System.AppDomain>.  Wenn dies passiert, ist nur sichergestellt, dass Abbruchcode in einem eingeschränkten Ausführungsbereich \(CER\) ausgeführt wird.  
  
### Verwenden von SafeHandle zum Vermeiden von Ressourcenverlusten  
 Wenn eine <xref:System.AppDomain> entladen wird, können Sie sich nicht darauf verlassen, dass `finally`\-Blöcke oder Finalizer ausgeführt werden. Daher müssen alle Zugriffe auf Betriebssystemressourcen mithilfe der <xref:System.Runtime.InteropServices.SafeHandle>\-Klasse und nicht über <xref:System.IntPtr>, <xref:System.Runtime.InteropServices.HandleRef> oder eine ähnliche Klasse abstrahiert werden.  Dies ermöglicht es der CLR, die verwendeten Handles nachzuverfolgen und zu schließen, die Sie auch im <xref:System.AppDomain> Zerlegungsfall verwenden. <xref:System.Runtime.InteropServices.SafeHandle> verwendet einen kritischen Finalizer, der CLR in jedem Fall ausgeführt wird.  
  
 Das Betriebssystemhandle wird vom Zeitpunkt der Erstellung bis zum Zeitpunkt der Freigabe im sicheren Handle gespeichert.  Es gibt keinen Zeitpunkt, zu dem eine <xref:System.Threading.ThreadAbortException> auftreten und den Verlust des Handles verursachen kann.  Außerdem werden bei einem Plattformaufruf die Verweise auf das Handle gezählt. Dies ermöglicht es, die Lebensdauer des Handles genau nachzuverfolgen und dadurch ein Sicherheitsproblem in Bezug auf eine Racebedingung zwischen `Dispose` und einer Methode zu vermeiden, die das Handle gegenwärtig verwendet.  
  
 Für die meisten Klassen, die derzeit einen Finalizer nur deshalb benötigen, um ein Betriebssystemhandle zu bereinigen, wird kein Finalizer mehr erforderlich sein.  Stattdessen befindet sich der Finalizer in der von <xref:System.Runtime.InteropServices.SafeHandle> abgeleiteten Klasse.  
  
 Beachten Sie, dass <xref:System.Runtime.InteropServices.SafeHandle> kein Ersatz für <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> ist.  Das explizite Freigeben von Betriebssystemressourcen kann weiterhin Vorteile hinsichtlich Ressourcenkonflikten und Leistungssteigerung mit sich bringen.  Es muss Ihnen nur bewusst sein, dass `finally`\-Blöcke, die Ressourcen explizit löschen, möglicherweise nicht vollständig ausgeführt werden.  
  
 Mit <xref:System.Runtime.InteropServices.SafeHandle> können Sie eine eigene <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A>\-Methode implementieren, die die Aufgabe übernimmt, das Handle freizugeben, indem beispielsweise der Zustand an eine Routine zum Freigeben eines Betriebssystemhandles übergeben wird oder eine Reihe von Handles in einer Schleife freigegeben werden können.  Die CLR garantiert, dass diese Methode ausgeführt wird.  Der Autor der <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A>\-Implementierung muss selbst sicherstellen, dass das Handle unter allen Umständen freigegeben wird.  Andernfalls wird ein Verlust des Handles verursacht, was häufig dazu führt, das dem Handle zugeordnete systemeigene Ressourcen ebenfalls verloren gehen.  Von <xref:System.Runtime.InteropServices.SafeHandle> abgeleitete Klassen müssen daher so strukturiert werden, dass für die <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A>\-Implementierung keine Zuordnung von Ressourcen erforderlich ist, die zum Zeitpunkt des Aufrufs möglicherweise nicht verfügbar sind.  Beachten Sie, dass es zulässig ist, in der Implementierung von <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> Methoden aufzurufen, die möglicherweise fehlschlagen, vorausgesetzt, dass der Code solche Fehler behandelt und den Vertrag zum Freigeben des systemeigenen Handles erfüllt.  Für das Debuggen besitzt <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> einen <xref:System.Boolean>\-Rückgabewert, der möglicherweise auf `false` festgelegt wird, wenn ein katastrophaler Fehler auftritt, der die Freigabe der Ressource verhindert.  Dies führt den [releaseHandleFailed](../../../docs/framework/debug-trace-profile/releasehandlefailed-mda.md)\-MDA aus, sofern dieser aktiviert ist, um die Identifizierung des Problems zu erleichtern.  Ansonsten hat es keine Auswirkungen auf die Runtime. <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> wird kein weiteres Mal für die gleiche Ressource aufgerufen, sodass das Handle verloren geht.  
  
 <xref:System.Runtime.InteropServices.SafeHandle> ist für bestimmte Kontexte nicht geeignet.  Da die <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A>\-Methode für einen <xref:System.GC>\-Finalizerthread ausgeführt werden kann, dürfen alle Handles, die für einen bestimmten Thread freigegeben werden müssen, nicht mit einem <xref:System.Runtime.InteropServices.SafeHandle> umschlossen werden.  
  
 Von der Laufzeit aufrufbare Wrapper \(Runtime Callable Wrappers, RCW\) können von der CLR ohne zusätzlichen Code bereinigt werden.  Bei Code, der Plattformaufrufe verwendet und COM\-Objekte als `IUnknown*` oder <xref:System.IntPtr> behandelt, sollte neu geschrieben werden, sodass er RCW verwendet. <xref:System.Runtime.InteropServices.SafeHandle> ist für dieses Szenario möglicherweise nicht aufgrund der Möglichkeit eine nicht verwaltete Freigabemethode wieder den, die zurück in verwalteten Code aufruft.  
  
#### Codeanalyseregel  
 Verwenden Sie <xref:System.Runtime.InteropServices.SafeHandle>, um Betriebssystemressourcen zu kapseln.  Verwenden Sie weder <xref:System.Runtime.InteropServices.HandleRef> noch Felder vom Typ <xref:System.IntPtr>.  
  
### Stellen Sie sicher, dass Finalizer nicht ausgeführt werden müssen, um Verluste von Betriebssystemressourcen zu verhindern  
 Überprüfen Sie die Finalizer sorgfältig, um sicherzustellen, dass kein Verlust einer Betriebssystemressource auftritt, auch wenn diese nicht ausgeführt werden.  Im Gegensatz zu einem normalen Entladen einer <xref:System.AppDomain> beim Ausführen der Anwendung in einem stabilen Zustand oder beim Herunterfahren von SQL Server, werden bei einem abrupten Entladen der <xref:System.AppDomain> keine Objekte finalisiert.  Stellen Sie sicher, dass im Fall eines abrupten Entladens keine Ressourcenverluste auftreten, da die korrekte Ausführung einer Anwendung nicht garantiert werden kann, die Integrität des Servers aber durch Verhindern von Ressourcenverlusten aufrechterhalten werden muss.  Verwenden Sie <xref:System.Runtime.InteropServices.SafeHandle>, um alle Betriebssystemressourcen freizugeben.  
  
### Stellen Sie sicher, dass finally\-Klauseln nicht ausgeführt werden müssen, um Verluste von Betriebssystemressourcen zu verhindern  
 Die Ausführung von `finally`\-Klauseln außerhalb von CERs wird nicht garantiert, daher dürfen Bibliotheksentwickler sich nicht darauf verlassen, dass Code in einem `finally`\-Block nicht verwaltete Ressourcen freigibt.  Als Lösung wird die Verwendung von <xref:System.Runtime.InteropServices.SafeHandle> empfohlen.  
  
#### Codeanalyseregel  
 Verwenden Sie <xref:System.Runtime.InteropServices.SafeHandle> anstelle von `Finalize` zum Bereinigen von Betriebssystemressourcen.  Verwenden Sie <xref:System.Runtime.InteropServices.SafeHandle> anstelle von <xref:System.IntPtr> zum Kapseln von Ressourcen.  Wenn die finally\-Klausel ausgeführt werden muss, fügen Sie sie in eine CER ein.  
  
### Alle Sperren sollten durch vorhandenen verwalteten Sperrcode erfolgen  
 Der CLR muss bekannt sein, wenn Code sich in einer Sperre befindet, damit sie die <xref:System.AppDomain> beendet und nicht einfach den Thread abbricht.  Ein Abbrechen des Threads bringt Risiken mit sich, da die im Thread verarbeiteten Daten in einem inkonsistenten Zustand verbleiben können.  Deshalb muss die gesamte <xref:System.AppDomain> wiederverwendet werden.  Die Folgen daraus, eine Sperre nicht zu identifizieren, können entweder Deadlocks oder falsche Ergebnisse sein.  Verwenden Sie die <xref:System.Threading.Thread.BeginCriticalRegion%2A>\-Methode und die <xref:System.Threading.Thread.EndCriticalRegion%2A>\-Methode, um Sperrbereiche zu identifizieren.  Dabei handelt es sich um statische Methode aus der <xref:System.Threading.Thread>\-Klasse, die sich nur auf den aktuellen Thread beziehen und dabei behilflich sind, die Bearbeitung des Sperrzählers eines Threads durch einen anderen Thread zu verhindern.  
  
 In <xref:System.Threading.Monitor.Enter%2A> und <xref:System.Threading.Monitor.Exit%2A> ist diese Benachrichtigung der CLR integriert, sodass deren Verwendung ebenso wie die der diese Methoden verwendenden [lock\-Anweisung](../Topic/lock%20Statement%20\(C%23%20Reference\).md) empfohlen wird.  
  
 Andere Sperrmechanismen wie Spinlocks und <xref:System.Threading.AutoResetEvent> müssen diese Methoden aufrufen, um die CLR zu benachrichtigen, dass ein kritischer Abschnitt betreten wird.  Diese Methoden nehmen keine Sperren an, sondern benachrichtigen die CLR, dass Code in einem kritischen Abschnitt ausgeführt wird, und dass ein Threadabbruch zu einem inkonsistenten Freigabezustand führen kann.  Wenn Sie eigene Sperrtypen definiert haben, z. B. eine benutzerdefinierte <xref:System.Threading.ReaderWriterLock>\-Klasse, verwenden Sie diese Sperrzählermethoden.  
  
#### Codeanalyseregel  
 Markieren und bezeichnen Sie alle Sperren mit <xref:System.Threading.Thread.BeginCriticalRegion%2A> und <xref:System.Threading.Thread.EndCriticalRegion%2A>.  Verwenden Sie <xref:System.Threading.Interlocked.CompareExchange%2A>, <xref:System.Threading.Interlocked.Increment%2A> und <xref:System.Threading.Interlocked.Decrement%2A> nicht in einer Schleife.  Nehmen Sie keinen Plattformaufruf der Win32\-Varianten dieser Methoden vor.  Verwenden Sie <xref:System.Threading.Thread.Sleep%2A> nicht in einer Schleife.  Verwenden Sie keine flüchtigen Felder.  
  
### Bereinigungscode muss in finally\- oder catch\-Block sein und nicht auf catch\-Block folgen  
 Der Bereinigungscode muss sich in einem `finally`\-Block oder `catch`\-Block befinden und darf auf keinen Fall auf einen `catch`\-Block folgen.  Diese Regel sollte grundsätzlich eingehalten werden.  Üblicherweise wird ein `finally`\-Block bevorzugt, da er sowohl beim Auslösen einer Ausnahme als auch beim normalen Erreichen des Endes des `try`\-Blocks den gleichen Code ausführt.  Wenn eine unerwartete Ausnahme ausgelöst wird, z. B. eine <xref:System.Threading.ThreadAbortException>, wird der Bereinigungscode nicht ausgeführt.  Nicht verwaltete Ressourcen, die normalerweise in einem `finally`\-Block bereinigt würden, sollten im Idealfall mit einem <xref:System.Runtime.InteropServices.SafeHandle> umschlossen werden, um Verluste zu vermeiden.  Beachten Sie, dass Objekte, einschließlich Handles, wirksam mit dem `using`\-Schlüsselwort \(C\#\) entfernt werden können.  
  
 Beim <xref:System.AppDomain>\-Recycling können zwar Ressourcen für den Finalizerthread bereinigt werden, dennoch muss der Bereinigungscode an der richtigen Position eingefügt werden.  Beachten Sie Folgendes: Wenn ein Thread eine asynchrone Ausnahme empfängt, ohne dass für ihn eine Sperre vorliegt, versucht die CLR, den Thread zu beenden, ohne die <xref:System.AppDomain> wiederverwenden zu müssen.  Wenn Sie dafür sorgen, dass die Ressourcen so schnell wie möglich bereinigt werden, sind mehr Ressourcen verfügbar und die Verwaltung der Lebensdauer wird vereinfacht.  Wenn Sie ein Handle für eine Datei in einem Fehlercodepfad nicht explizit schließen und dann durch den <xref:System.Runtime.InteropServices.SafeHandle>\-Finalizer bereinigen lassen, kann der Code bei der nächsten Ausführung fehlschlagen, da er versucht, auf genau diese Datei zuzugreifen, sofern der Finalizer nicht bereits ausgeführt wurde.  Achten Sie daher darauf, dass Bereinigungscode vorhanden ist und ordnungsgemäß funktioniert \(auch wenn dies nicht zwingend erforderlich ist\), um die Wiederherstellung nach einem Ausfall zu erleichtern.  
  
#### Codeanalyseregel  
 Bereinigungscode, der auf `catch` folgt, muss sich in einem `finally`\-Block befinden.  In einem finally\-Block Platzaufrufe. Blöcke `catch` sollten in einem oder rethrow enden.  Es gibt Ausnahmen, z. B. Code, der erkennen soll, ob eine Netzwerkverbindung hergestellt werden kann, bei denen eine große Anzahl von Ausnahmen auftreten kann. Code, der üblicherweise zahlreiche Ausnahmen abfangen muss, sollte angeben, dass der Code auf die ordnungsgemäße Funktion überprüft werden sollte.  
  
### Entfernen des prozessweit veränderlichen Freigabezustands zwischen Anwendungsdomänen oder Verwenden eines eingeschränkten Ausführungsbereichs  
 Wie bereits in der Einführung dargestellt, kann das Schreiben von verwaltetem Code, der den prozessweiten Freigabezustand über Anwendungsdomänen hinweg zuverlässig überwacht, erhebliche Schwierigkeiten bereiten.  Als prozessweiter Freigabezustand werden Datenstrukturen bezeichnet, die in Win32\-Code, in der CLR oder in verwaltetem Code über Remoting von mehreren Anwendungsdomänen gemeinsam verwendet werden.  Es ist äußerst schwierig, einen veränderlichen Freigabezustand ordnungsgemäß in verwaltetem Code zu schreiben, und auch bei einem statischen Freigabezustand müssen Sie sehr umsichtig vorgehen.  Bei einem prozessweiten oder computerweiten Freigabezustand müssen Sie ein Verfahren finden, diesen zu entfernen oder den Freigabezustand mit einem eingeschränkter Ausführungsbereich \(Constrained Execution Region, CER\) zu schützen.  Jede Bibliothek mit einem Freigabezustand, der nicht erkannt und berichtigt wird, kann bei einem Host wie SQL Server, für den ordnungsgemäße <xref:System.AppDomain>\-Entladung erforderlich ist, zu einem Absturz führen.  
  
 Wenn in Code ein COM\-Objekt verwendet wird, vermeiden Sie, dieses COM\-Objekt für verschiedene Anwendungsdomänen freizugeben.  
  
### Sperren funktionieren nicht prozessweit oder zwischen Anwendungsdomänen  
 Globale Prozesssperren wurden früher mit <xref:System.Threading.Monitor.Enter%2A> und der [lock\-Anweisung](../Topic/lock%20Statement%20\(C%23%20Reference\).md) erstellt.  Dies erfolgt z. B. beim Sperren von agilen <xref:System.AppDomain>\-Klassen, beispielsweise <xref:System.Type>\-Instanzen von nicht freigegebenen Assemblys, <xref:System.Threading.Thread>\-Objekten, intern gespeicherten Zeichenfolgen und einigen Zeichenfolgen, die mithilfe von Remoting für verschiedene Anwendungsdomänen freigegeben sind.  Diese Sperren sind nicht mehr prozessweit.  Um eine prozessweite anwendungsübergreifende Domänensperre zu erkennen, müssen Sie ermitteln, ob der Code innerhalb der Sperre externe beibehaltene Ressourcen verwendet, z. B. eine Datei auf dem Datenträger oder eine Datenbank.  
  
 Das Verhängen einer Sperre innerhalb einer <xref:System.AppDomain> kann zu Problemen führen, wenn der geschützte Code eine externe Ressource verwendet, da der Code gleichzeitig in mehreren Anwendungsdomänen ausgeführt werden könnte.  Probleme treten dann auf, wenn für den ganzen Prozess in eine Protokolldatei geschrieben wird oder eine Bindung an einen Socket erfolgt.  Bei Verwendung von verwaltetem Code gibt es daher zum Erhalten einer Sperre für einen ganzen Prozess keinen anderen einfachen Weg als die Verwendung einer <xref:System.Threading.Mutex>\-Instanz oder einer <xref:System.Threading.Semaphore>\-Instanz.  Erstellen Sie Code, der nicht gleichzeitig in zwei Anwendungsdomänen ausgeführt werden kann, oder verwenden Sie die <xref:System.Threading.Mutex>\-Klasse bzw. die <xref:System.Threading.Semaphore>\-Klasse.  Wenn der vorhandene Code nicht geändert werden kann, führen Sie die Synchronisierung nicht über ein benanntes Win32\-Mutex aus, da bei der Ausführung im Fiber\-Modus nicht garantiert werden kann, dass das Mutex von demselben Betriebssystemthread abgerufen und freigegeben wird.  Die Codesperre muss mit der verwalteten <xref:System.Threading.Mutex>\-Klasse, einem benannten <xref:System.Threading.ManualResetEvent>, <xref:System.Threading.AutoResetEvent> oder <xref:System.Threading.Semaphore> auf eine Weise synchronisiert werden, dass die CLR nicht die Sperre synchronisiert, sondern nicht verwalteten Code verwendet.  
  
#### Vermeiden von lock\(typeof\(MyType\)\)  
 Private und öffentliche <xref:System.Type>\-Objekte in freigegebenen Assemblys mit nur eine Kopie des von allen Anwendungsdomänen gemeinsam verwendeten Codes stellen ebenfalls ein Problem dar.  Bei freigegebenen Assemblys gibt es nur eine Instanz eines <xref:System.Type> pro Prozess, d. h., mehrere Anwendungsdomänen verwenden dieselbe <xref:System.Type>\-Instanz gemeinsam.  Wenn eine <xref:System.Type>\-Instanz gesperrt wird, wirkt sich diese Sperre auf den gesamten Prozess und nicht nur die <xref:System.AppDomain> aus.  Wenn eine <xref:System.AppDomain> ein <xref:System.Type>\-Objekt sperrt, wird dieser Thread abrupt abgebrochen und die Sperre nicht freigegeben.  Diese Sperre verursacht dann möglicherweise einen Deadlock in anderen Anwendungsdomänen.  
  
 Es empfiehlt sich beim Ausführen von Sperren in statischen Methoden dem Code ein statisches internes Synchronisierungsobjekt hinzuzufügen.  Dieses kann im Klassenkonstruktor initialisiert werden, sofern vorhanden, es kann aber nicht wie folgt initialisiert werden:  
  
```  
private static Object s_InternalSyncObject;  
private static Object InternalSyncObject   
{  
    get   
    {  
        if (s_InternalSyncObject == null)   
        {  
            Object o = new Object();  
            Interlocked.CompareExchange(  
                ref s_InternalSyncObject, o, null);  
        }  
        return s_InternalSyncObject;  
    }  
}  
```  
  
 Verwenden Sie dann beim Ausführen der Sperre die `InternalSyncObject`\-Eigenschaft, um ein zu sperrendes Objekt abzurufen.  Sie müssen die Eigenschaft nicht verwenden, wenn Sie das interne Synchronisierungsobjekt im Klassenkonstruktor initialisiert haben.  Die Sicherheitsprüfung im Sperreninitialisierungscode sollte wie in diesem Beispiel lauten:  
  
```  
public static MyClass SingletonProperty   
{  
    get   
    {  
        if (s_SingletonProperty == null)   
        {  
            lock(InternalSyncObject)   
            {  
                // Do not use lock(typeof(MyClass))   
                if (s_SingletonProperty == null)   
                {  
                    MyClass tmp = new MyClass(…);     
                    // Do all initialization before publishing  
                    s_SingletonProperty = tmp;  
                }  
            }  
        }  
        return s_SingletonProperty;  
    }  
}  
```  
  
#### Hinweis zu Lock\(this\)  
 Es ist im Allgemeinen akzeptabel, ein einzelnes Objekt zu sperren, auf das öffentlich zugegriffen werden kann.  Wenn das Objekt jedoch ein Singleton\-Objekt ist, das einen Deadlock in einem gesamten Teilsystem verursachen kann, sollten Sie auch das oben stehende Entwurfsmuster in Betracht ziehen.  Beispielsweise kann eine Sperre für ein <xref:System.Security.SecurityManager>\-Objekt zu einem Deadlock in der <xref:System.AppDomain> führen, sodass die gesamte <xref:System.AppDomain> nicht mehr verwendet werden kann.  Es ist empfehlenswert, ein Objekt mit öffentlichem Zugriff von diesem Typ nicht zu sperren.  Eine Sperre für eine einzelne Auflistung oder ein einzelnes Array sollte jedoch im Allgemeinen kein Problem darstellen.  
  
#### Codeanalyseregel  
 Führen Sie keine Sperren für Typen aus, die möglicherweise über mehrere Anwendungsdomänen hinweg verwendet werden oder keine stark ausgeprägte Identität besitzen.  Rufen Sie <xref:System.Threading.Monitor.Enter%2A> nicht für <xref:System.Type>, <xref:System.Reflection.MethodInfo>, <xref:System.Reflection.PropertyInfo>, <xref:System.String>, <xref:System.ValueType>, <xref:System.Threading.Thread> oder ein beliebiges Objekt auf, das von <xref:System.MarshalByRefObject> abgeleitet wird.  
  
### Entfernen von GC.KeepAlive\-Aufrufen  
 Ein beträchtlicher Anteil am vorhandenen Code verwendet <xref:System.GC.KeepAlive%2A> nicht dort, wo es angebracht ist.  Nach dem Konvertieren in <xref:System.Runtime.InteropServices.SafeHandle> müssen Klassen <xref:System.GC.KeepAlive%2A> nicht aufrufen, vorausgesetzt, sie besitzen keinen Finalizer, sondern überlassen das Finalisieren der Betriebssystemhandles <xref:System.Runtime.InteropServices.SafeHandle>.  Wenn die Leistungseinbußen, die durch Beibehalten eines Aufrufs von <xref:System.GC.KeepAlive%2A>entstehen, möglicherweise zu vernachlässigen sind, erschwert die Auffassung, ein Aufruf von <xref:System.GC.KeepAlive%2A> ist erforderlich oder ausreichend, um ein Lebensdauerproblem zu beheben, das möglicherweise gar nicht mehr besteht, die Verwaltung von Code.  Bei der Verwendung von aufrufbaren Wrappern der COM\-Interop\-CLR \(RCWs\) ist <xref:System.GC.KeepAlive%2A> jedoch immer noch für den Code erforderlich.  
  
#### Codeanalyseregel  
 Entfernen Sie <xref:System.GC.KeepAlive%2A>.  
  
### Verwenden des Hostschutzattributs  
 Das <xref:System.Security.Permissions.HostProtectionAttribute> \(HPA\) erlaubt die Verwendung deklarativer Sicherheitsaktionen zum Bestimmen der Hostschutzanforderungen, die es dem Host ermöglichen, vollständig vertrauenswürdigen Code am Aufrufen bestimmter Methoden zu hindern, die für diesen Host nicht geeignet sind, z. B. <xref:System.Environment.Exit%2A> oder <xref:System.Windows.Forms.MessageBox.Show%2A> für SQL Server.  
  
 Das HPA betrifft nur nicht verwaltete Anwendungen, die die Common Language Runtime hosten und Hostschutz implementieren, z. B. SQL Server.  Wenn dieses angewendet wird, führt die Sicherheitsaktion zum Erstellen eines Linkaufrufs auf Grundlage der von der Klasse oder Methode offen gelegten Hostressourcen.  Wenn der Code in einer Clientanwendung oder auf einem Server ausgeführt wird, der über keinen Hostschutz verfügt, "verpufft" das Attribut. Es wird nicht erkannt und folglich nicht angewendet.  
  
> [!IMPORTANT]
>  Der Zweck dieses Attributs ist, hostspezifische Programmiermodellrichtlinien durchzusetzen, jedoch nicht das Sicherheitsverhalten.  Obwohl ein Linkaufruf zum Überprüfen auf Konformität mit den Programmiermodellanforderungen verwendet wird, stellt das <xref:System.Security.Permissions.HostProtectionAttribute> keine Sicherheitsberechtigung dar.  
  
 Wenn der Host nicht über Programmiermodellanforderungen verfügt, treten keine Linkaufrufe auf.  
  
 Dieses Attribut bezeichnet Folgendes:  
  
-   Methoden oder Klassen, die nicht mit dem Hostprogrammiermodell übereinstimmen, aber keine anderen Auswirkungen haben.  
  
-   Methoden oder Klassen, die nicht mit dem Hostprogrammiermodell übereinstimmen, und möglicherweise zur Destabilisierung des vom Server verwalteten Benutzercodes führen.  
  
-   Methoden oder Klassen, die nicht mit dem Hostprogrammiermodell übereinstimmen, und möglicherweise zur Destabilisierung des Serverprozesses selbst führen.  
  
> [!NOTE]
>  Wenn Sie eine Klassenbibliothek erstellen, die von Anwendungen aufgerufen wird, die möglicherweise in einer Umgebung mit Hostsicherheit ausgeführt werden, muss dieses Attribut auf die Member angewendet werden, die <xref:System.Security.Permissions.HostProtectionResource>\-Ressourcenkategorien verfügbar machen.  Bei .NET Framework\-Klassenbibliotheksmembern mit diesem Attribut wird nur der unmittelbare Aufrufer überprüft.  Der Bibliotheksmember muss auf die gleiche Weise auch eine Prüfung seines unmittelbaren Aufrufers verursachen.  
  
 Weitere Informationen über HPA finden Sie unter <xref:System.Security.Permissions.HostProtectionAttribute>.  
  
#### Codeanalyseregel  
 Für SQL Server müssen alle Methoden mit dem HPA identifiziert werden, die zum Einführen der Synchronisierung oder des Threadings verwendet werden.  Dies schließt Methoden ein, die den Freigabezustand verwenden, synchronisiert sind oder externe Prozesse verwalten.  Die <xref:System.Security.Permissions.HostProtectionResource>\-Werte, die sich auf SQL Server auswirken, sind <xref:System.Security.Permissions.HostProtectionResource>, <xref:System.Security.Permissions.HostProtectionResource> und <xref:System.Security.Permissions.HostProtectionResource>.  Allerdings sollten alle Methoden, die eine <xref:System.Security.Permissions.HostProtectionResource> offen legen, durch ein HPA identifiziert werden, nicht nur solche Ressourcen, die sich auf SQL auswirken.  
  
### Kein unbeschränktes Blockieren in nicht verwaltetem Code  
 Blockieren in nicht verwaltetem Code statt in verwaltetem Code kann zu Denial\-of\-Service\-Angriffen führen, da die CLR den Thread nicht abbrechen kann.  Ein blockierter Thread verhindert, dass die CLR die <xref:System.AppDomain> entlädt, zumindest wenn auf die Verwendung bestimmter äußerst unsicherer Operationen verzichtet wird.  Ein Blockieren mit einem Win32\-Synchronisierungsprimitiven ist ein deutliches Beispiel für einen unzulässigen Vorgang.  Das Blockieren in einem Aufruf von `ReadFile` für einen Socket sollte möglichst vermieden werden. Im Idealfall sollte die Win32\-API einen Mechanismus für Timeouts für solche Operationen bereitstellen.  
  
 Jede Methode, die systemeigenen Code aufruft, sollte einen Win32\-Aufruf mit einem angemessenen endlichen Timeout verwenden.  Wenn der Benutzer den Timeout angeben darf, sollte der Benutzer nur mit bestimmten Sicherheitsberechtigungen in der Lage sein, einen unendlichen Timeout anzugeben.  Als Richtlinie gilt, dass bei einer Methode, die länger als etwa 10 Sekunden blockiert, eine Version verwendet werden muss, die Timeouts unterstützt. Andernfalls wird zusätzliche CLR\-Unterstützung benötigt.  
  
 Im Folgenden finden Sie einige Beispiele für problematische APIs:  Pipes \(anonyme wie benannte\) können ohne Timeout erstellt werden. Code muss jedoch sicherstellen, dass `CreateNamedPipe` und `WaitNamedPipe` niemals mit NMPWAIT\_WAIT\_FOREVER aufgerufen werden.  Außerdem kann es zu einer unerwarteten Blockierung kommen, selbst wenn ein Timeout angegeben wird.  Durch einen Aufruf von `WriteFile` für eine anonyme Pipe wird so lange blockiert, bis alle Bytes geschrieben sind, d. h., wenn der Puffer nicht gelesene Daten enthält, blockiert der `WriteFile`\-Aufruf, bis der Reader Speicherplatz im Pipepuffer freigegeben hat.  Sockets sollten immer eine API verwenden, die einen Timeoutmechanismus unterstützt.  
  
#### Codeanalyseregel  
 Ohne Timeout in nicht verwaltetem Code zu blockieren, stellt einen Denial\-of\-Service\-Angriff dar.  Führen Sie keine Plattformaufrufe von `WaitForSingleObject`, `WaitForSingleObjectEx`, `WaitForMultipleObjects`, `MsgWaitForMultipleObjects` und `MsgWaitForMultipleObjectsEx` aus.  Verwenden Sie NMPWAIT\_WAIT\_FOREVER nicht.  
  
### Identifizieren aller STA\-abhängigen Features.  
 Identifizieren Sie allen Code, der COM\-Singlethreadapartments \(STAs\) verwendet.  STAs sind im SQL Server\-Prozess deaktiviert.  Features, die auf `CoInitialize` beruhen, z. B. Leistungsindikatoren oder die Zwischenablage, müssen in SQL Server deaktiviert werden.  
  
### Stellen Sie sicher, dass Finalizer keine Synchronisierungsprobleme aufweisen  
 In zukünftigen Versionen von .NET Framework werden möglicherweise mehrere Finalizerthreads unterstützt, d. h., die Finalizer für unterschiedliche Instanzen des gleichen Typs werden gleichzeitig ausgeführt.  Diese müssen nicht völlig threadsicher sein. Der Garbage Collector stellt sicher, dass nur ein Thread den Finalizer für eine bestimmte Objektinstanz ausführt.  Der Finalizercode muss allerdings so verfasst werden, dass Racebedingungen und Deadlocks bei gleichzeitiger Ausführung für mehrere unterschiedliche Objektinstanzen vermieden werden.  Bei der Verwendung eines externen Zustands in einem Finalizer, z. B. dem Schreiben in eine Protokolldatei, müssen Threadingprobleme behandelt werden.  Verlassen Sie sich bei der Threadsicherheit nicht auf die Finalisierung.  Verwenden Sie keinen verwalteten oder systemeigenen lokalen Threadspeicher, um den Zustand für den Finalizerthread zu speichern.  
  
#### Codeanalyseregel  
 Finalizer dürfen keine Synchronisierungsprobleme aufweisen.  Verwenden Sie in einem Finalizer keinen statischen veränderlichen Zustand.  
  
### Vermeiden Sie möglichst nicht verwalteten Arbeitsspeicher  
 Bei nicht verwaltetem Speicher können wie bei Betriebssystemhandles Verluste auftreten.  Versuchen Sie möglichst, Speicher auf dem Stapel mit [stackalloc](../Topic/stackalloc%20\(C%23%20Reference\).md) oder einem fixierten verwalteten Objekt wie [fixed\-Anweisung](../Topic/fixed%20Statement%20\(C%23%20Reference\).md) oder <xref:System.Runtime.InteropServices.GCHandle> mit einem byte\[\] zu verwenden.  <xref:System.GC> bereinigt diese letztendlich.  Wenn Sie jedoch nicht verwalteten Arbeitsspeicher belegen müssen, empfiehlt sich möglicherweise die Verwendung einer von <xref:System.Runtime.InteropServices.SafeHandle> abgeleiteten Klasse, die die Speicherbelegung umschließt.  
  
 Beachten Sie, dass es mindestens eine Situation gibt, in der <xref:System.Runtime.InteropServices.SafeHandle> ungeeignet ist.  Bei COM\-Methodenaufrufen, die Speicher belegen oder freigeben, kommt es häufig vor, dass eine DLL Speicher mit `CoTaskMemAlloc` belegt und eine andere DLL diesen Speicher mit `CoTaskMemFree` freigibt.  <xref:System.Runtime.InteropServices.SafeHandle> ist an diesen Stellen ungeeignet, weil hierbei versucht wird, die Lebensdauer des nicht verwalteten Speichers an die Lebensdauer des <xref:System.Runtime.InteropServices.SafeHandle> zu knüpfen, statt zuzulassen, dass die andere DLL die Lebensdauer des Speichers bestimmt.  
  
### Überprüfen aller Verwendungen von Catch\(Exception\)  
 In catch\-Blöcken, in denen nicht nur eine spezifische Ausnahme, sondern alle Ausnahmen abgefangen werden, werden jetzt auch die asynchronen Ausnahmen abgefangen.  Untersuchen Sie jeden catch\(Exception\)\-Block. Suchen Sie dabei, ob eine wichtige Ressource freigegeben oder Back\-out\-Code übersprungen wird. Prüfen Sie außerdem, ob potenziell falsches Verhalten im catch\-Block selbst vorliegt, weil eine <xref:System.Threading.ThreadAbortException>, <xref:System.StackOverflowException> oder <xref:System.OutOfMemoryException> behandelt wird.  Beachten Sie folgende Möglichkeiten: Dieser Code zeichnet möglicherweise ein Protokoll auf, es wurden Annahmen gemacht, dass der Code nur bei bestimmten Ausnahmen ausgeführt wird, oder es wurden Annahmen gemacht, dass beim Auftreten einer Ausnahme nur eine bestimmte Fehlerursache in Frage kommt.  Diese Annahmen müssen u. U. revidiert werden, um <xref:System.Threading.ThreadAbortException> zu berücksichtigen.  
  
 Möglicherweise empfiehlt es sich, alle Stellen im Code, in denen alle Ausnahmen abgefangen werden, dahingehend zu ändern, dass nur ein bestimmter und erwarteter Typ von Ausnahme abgefangen wird, z. B: <xref:System.FormatException> bei Methoden zum Formatieren von Zeichenfolgen.  Dies verhindert, dass der catch\-Block bei unerwarteten Ausnahmen ausgeführt wird, und trägt dazu bei, dass der Code keine Fehler verdeckt, indem unerwartete Ausnahmen abgefangen werden.  Als allgemeine Regel sollten Ausnahmen nie in Bibliothekscode behandelt werden. \(Code, bei dem Sie eine Ausnahme behandeln müssen, kann ein Anzeichen eines konzeptionellen Fehlers im aufgerufenen Code sein.\)  In einigen Situationen möchten Sie vielleicht eine Ausnahme abfangen und eine andere Art von Ausnahme auslösen, um mehr Daten bereitzustellen.  Verwenden Sie hierbei geschachtelte Ausnahmen, und speichern Sie die wirkliche Fehlerursache in der <xref:System.Exception.InnerException%2A>\-Eigenschaft der neuen Ausnahme.  
  
#### Codeanalyseregel  
 Überprüfen Sie alle catch\-Blöcke in verwaltetem Code, die alle Objekte oder Ausnahmen abfangen.  In C\# bedeutet dies, sowohl `catch` {} als auch `catch(Exception)` {} zu kennzeichnen.  Möglicherweise empfiehlt es sich, den Ausnahmetyp stark einzuengen oder den Code zu prüfen, um sicherzustellen, dass er beim Abfangen eines unerwarteten Ausnahmetyps immer noch ordnungsgemäß ausgeführt wird.  
  
### Nehmen Sie nicht an, dass ein verwalteter Thread ein Win32\-Thread ist \- er ist eine Fiber  
 Sie können verwalteten lokalen Threadspeicher, nicht aber nicht verwalteten lokalen Threadspeicher verwenden, und Sie können auch nicht annehmen, dass der Code nochmals im selben Betriebssystemthread ausgeführt wird.  Ändern Sie keine Einstellungen wie das Gebietsschema eines Threads.  Rufen Sie `InitializeCriticalSection` oder `CreateMutex` nicht mithilfe eines Plattformaufrufs auf, weil hierbei erforderlich ist, dass der Betriebssystemthread, der in eine Sperre eintritt, die Sperre auch wieder verlässt.  Da dies bei der Verwendung von Fibers nicht der Fall ist, können kritische Win32\-Abschnitte und Mutexe nicht direkt in SQL verwendet werden.  Beachten Sie, dass die verwaltete <xref:System.Threading.Mutex>\-Klasse diese Threadaffinitätsaspekte nicht behandelt.  
  
 Es ist sicher, einen Großteil des Zustands für ein verwaltetes <xref:System.Threading.Thread>\-Objekt zu verwenden. Dies schließt verwalteten lokalen Threadspeicher und die aktuelle Benutzeroberflächenkultur des Threads ein.  Sie können auch das <xref:System.ThreadStaticAttribute> verwenden, das nur dem aktuellen verwalteten Thread den Zugriff auf den Wert einer vorhandenen statischen Variablen gewährt \(dies stellt eine andere Methode dar, lokalen Fiberspeicher in der CLR zu verwenden\).  Aufgrund des Programmiermodells können Sie die aktuelle Kultur eines Threads bei der Ausführung in SQL nicht ändern.  
  
#### Codeanalyseregel  
 SQL Server wird im Fibermodus ausgeführt. Verwenden Sie keinen lokalen Threadspeicher.  Vermeiden Sie Plattformaufrufe von `TlsAlloc`, `TlsFree`, `TlsGetValue` und `TlsSetValue.`.  
  
### Lassen Sie SQL Server den Identitätswechsel vornehmen  
 Da der Identitätswechsel auf Threadebene abläuft und SQL im Fibermodus ausgeführt werden kann, sollte verwalteter Code nicht die Identität von Benutzern annehmen, und es sollten keine Aufrufe von `RevertToSelf` erfolgen.  
  
#### Codeanalyseregel  
 Lassen Sie SQL Server den Identitätswechsel vornehmen.  Verwenden Sie nicht `RevertToSelf`, `ImpersonateAnonymousToken`, `DdeImpersonateClient`, `ImpersonateDdeClientWindow`, `ImpersonateLoggedOnUser`, `ImpersonateNamedPipeClient`, `ImpersonateSelf`, `RpcImpersonateClient`, `RpcRevertToSelf`, `RpcRevertToSelfEx` oder `SetThreadToken`.  
  
### Rufen Sie nicht Thread::Suspend auf  
 Das Unterbrechen eines Threads sieht möglicherweise wie ein einfacher Vorgang aus. Dies kann jedoch zu Deadlocks führen.  Wenn ein Thread, der eine Sperre hält, von einem zweiten Thread unterbrochen und der zweite Thread anschließend versucht, dieselbe Sperre zu erhalten, tritt ein Deadlock auf. <xref:System.Threading.Thread.Suspend%2A> kann Sicherheit, beim Laden von Klassen, beim Remoting und Reflektion gerade beeinträchtigen.  
  
#### Codeanalyseregel  
 Rufen Sie <xref:System.Threading.Thread.Suspend%2A> nicht auf.  Erwägen Sie stattdessen, ein echtes Synchronisierungsgrundelement wie <xref:System.Threading.Semaphore> oder <xref:System.Threading.ManualResetEvent> zu verwenden.  
  
### Schützen von kritischen Vorgängen mit eingeschränkten Ausführungsbereichen und Zuverlässigkeitsverträgen  
 Vergewissern Sie sich bei komplexen Vorgängen, bei denen ein gemeinsam genutzter Status aktualisiert wird oder die deterministisch entweder vollständig erfolgreich abschließen oder vollständig fehlschlagen müssen, dass sie durch CERs \(eingeschränkte Ausführungsbereiche\) geschützt sind.  Hierdurch wird sichergestellt, dass der Code in jeder Situation ausgeführt wird, sogar bei einem plötzlichen Threadabbruch oder einem plötzlichen Entladen der <xref:System.AppDomain>.  
  
 Ein CER ist ein besonderer `try/finally`\-Block, der unmittelbar auf einen Aufruf von <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> folgt.  
  
 Hiermit weisen Sie den Just\-In\-Time\-Compiler an, den Code im finally\-Block vorzubereiten, bevor der `try`\-Block ausgeführt wird.  Dies stellt sicher, dass der Code im finally\-Block erstellt und in allen Situationen ausgeführt wird.  Ein leerer `try`\-Block in einem CER ist nicht ungewöhnlich.  Ein CER schützt vor asynchronen Threadabbrüchen und Ausnahmen aufgrund von mangelndem Arbeitsspeicher.  Unter <xref:System.Runtime.CompilerServices.RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup%2A> finden Sie eine Form von CER, die außerdem Stapelüberläufe bei Code mit äußerst tiefen Aufrufhierarchien behandeln kann.  
  
## Siehe auch  
 <xref:System.Runtime.ConstrainedExecution>   
 [SQL Server Programming and Host Protection Attributes](../../../docs/framework/performance/sql-server-programming-and-host-protection-attributes.md)